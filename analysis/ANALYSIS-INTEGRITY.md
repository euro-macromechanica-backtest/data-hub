# Integrity Verification — Hashes, GPG, OpenTimestamps (with absolute-path support)

This guide explains **how to verify a yearly snapshot** (backtest inputs/outputs) using the hash manifest,
a GPG signature, and an OpenTimestamps anchor — **even if `artifacts_YYYY.sha256` contains absolute paths**.

## 📦 Snapshot contents (typical)
- **Integrity artifacts:**  
  `integrity/artifacts_YYYY.sha256`, `integrity/artifacts_YYYY.sha256.asc` (GPG), `integrity/artifacts_YYYY.sha256.ots` (OpenTimestamps).
- **Report:** `analysis/output_bundle_report/annual_report_YYYY.md`  
  The report prints `— Manifest SHA-256: <…>` — this is the **SHA‑256 of the manifest file**.
- **Inputs:** `source_data/**`, `economic_calendars/**`  
- **Outputs:** `prepared/**`, `analysis/output_bundle_report/**`

> Folder names may differ per project — follow your layout and the manifest.

---

## TL;DR
1. **Verify the GPG signature** and (optionally) **OTS** for `artifacts_YYYY.sha256`.
2. **Check that the report prints the manifest’s SHA‑256.**
3. **Compare the normalized report’s SHA** (line `— Manifest SHA-256:` *without* a value) with the entry stored in the manifest.
4. For convenient file checks, **create a local copy of the manifest with basenames** (absolute → basename) and verify against it.

> Absolute paths **do not affect** hash correctness; they only confuse tools that expect relative paths.

---

## 🧪 Verify hashes for inputs/outputs against the manifest

Inputs live under **`/source_data`** and **`/economic_calendars`**; outputs under **`/prepared`** and **`/analysis/output_bundle_report`**.

### 🐧 macOS / Linux (bash/zsh)

> If `sha256sum` is unavailable, use `shasum -a 256`. The `HASH` variable will select the right one.

```bash
# 0) select hash command
if command -v sha256sum >/dev/null 2>&1; then HASH='sha256sum'; else HASH='shasum -a 256'; fi
echo "Using: $HASH"
```

**0) Normalize manifest paths (absolute → basename)**  
Create a local copy of the manifest in which absolute paths are replaced with basenames:
```bash
YEAR=YYYY
sed -E 's#^([0-9a-f]{64})  (.+[/\\])?([^/\\]+)$#\1  \3#' artifacts_${YEAR}.sha256 > artifacts_${YEAR}.local.sha256
```
> Hashes stay the same — only the path label changes. Ensure **filenames are unique**. If duplicates exist, rename them or verify per-subfolder with separate local manifests.

**1) The report must print the manifest’s hash (external label)**
```bash
MAN_SHA=$($HASH artifacts_${YEAR}.sha256 | awk '{print $1}')
grep -F "— Manifest SHA-256: $MAN_SHA" annual_report_${YEAR}.md >/dev/null \
  && echo "OK: report contains manifest hash" \
  || echo "BAD: report does not include manifest hash"
```

**2) Compare the report’s normalized SHA with the manifest entry**  
Extract the report’s hash from the **original** manifest, even if the path there is absolute:
```bash
MAN_REP_SHA=$(grep -E '^([0-9a-f]{64})  (.+[/\\])?annual_report_'${YEAR}'\.md$' artifacts_${YEAR}.sha256 | head -n1 | awk '{print $1}')

# Normalize the report (remove the value after "Manifest SHA-256:") and hash it
REP_NORM_SHA=$(sed "s/— Manifest SHA-256: $MAN_SHA/— Manifest SHA-256:/" annual_report_${YEAR}.md \
  | tr -d '\r' \
  | $HASH | awk '{print $1}')

[ "$MAN_REP_SHA" = "$REP_NORM_SHA" ] \
  && echo "OK: normalized report SHA matches manifest" \
  || echo "BAD: normalized report SHA does not match"
```

**3) Verify all other files from the manifest (excluding the report)**  
Use the **local** (basename) manifest so `-c` can locate files:
```bash
# recalc locally
awk '$2!="annual_report_'${YEAR}'.md"{print $2}' artifacts_${YEAR}.local.sha256 \
  | xargs -I{} $HASH "{}" \
  | awk '{print $1"  "$2}' | sort -k2 > /tmp/recalc.txt

# bring manifest to the same shape and sort
awk '$2!="annual_report_'${YEAR}'.md"{print}' artifacts_${YEAR}.local.sha256 \
  | sort -k2 > /tmp/manifest_no_report.txt

diff -u /tmp/manifest_no_report.txt /tmp/recalc.txt \
  && echo "OK: all files match" \
  || echo "BAD: mismatches found"
```

> Alternative: verify “in one go” against the local manifest:  
> ```bash
> $HASH -c artifacts_${YEAR}.local.sha256
> ```
> (remove the report’s line from `.local.sha256` if needed).

---

### 🪟 Windows PowerShell

**0) Create a local manifest copy with basenames**
```powershell
$YEAR = "YYYY"
Get-Content "artifacts_$YEAR.sha256" | % {
  if ($_ -match '^([0-9a-f]{64})\s\s(.+)$') {
    "$($matches[1])  $(Split-Path $matches[2] -Leaf)"
  }
} | Set-Content "artifacts_$YEAR.local.sha256"
```

**1) The report must print the manifest’s hash**
```powershell
$manHash = (Get-FileHash ".\artifacts_$YEAR.sha256" -Algorithm SHA256).Hash.ToLower()
if ((Get-Content ".\annual_report_$YEAR.md" -Raw) -match "— Manifest SHA-256:\s*$manHash") {
  "OK: report contains manifest hash"
} else {
  "BAD: report does not include manifest hash"
}
```

**2) Compare the normalized report’s SHA with the manifest entry (path may be absolute)**
```powershell
# extract SHA for annual_report_* from the ORIGINAL manifest (path can be absolute)
$line = Select-String -Path ".\artifacts_$YEAR.sha256" -Pattern '^([0-9a-f]{64})\s\s(.+\\)?annual_report_' + $YEAR + '\.md$' | Select-Object -First 1
$manRepHash = $line.Matches.Groups[1].Value.ToLower()

# normalize the report and compute SHA-256
$report = Get-Content ".\annual_report_$YEAR.md" -Raw
$norm   = [regex]::Replace($report, "— Manifest SHA-256:\s*[0-9A-Fa-f]{64}", "— Manifest SHA-256:")
$sha256 = [System.Security.Cryptography.SHA256]::Create()
$bytes  = [System.Text.Encoding]::UTF8.GetBytes($norm)
$repHash = ($sha256.ComputeHash($bytes) | ForEach-Object ToString x2) -join "" | ForEach-Object ToLower

if ($repHash -eq $manRepHash) { "OK: normalized report SHA matches" } else { "BAD: normalized report SHA mismatch" }
```

**3) Verify all other files from the local manifest (excluding the report)**
```powershell
$errors = @()
Get-Content ".\artifacts_$YEAR.local.sha256" | ForEach-Object {
  if ($_ -match '^\s*$') { return }
  $parts = $_ -split '\s{2}',2
  $hashRef = $parts[0].ToLower()
  $name    = $parts[1]
  if ($name -eq "annual_report_$YEAR.md") { return }
  if (-not (Test-Path $name)) { $errors += "MISSING: $name"; return }
  $hashAct = (Get-FileHash $name -Algorithm SHA256).Hash.ToLower()
  if ($hashAct -ne $hashRef) { $errors += "MISMATCH: $name`n  manifest=$hashRef`n  actual  =$hashAct" }
}
if ($errors.Count -eq 0) { "OK: all files match" } else { $errors -join "`n" }
```

---

## 🔐 GPG signature & OpenTimestamps

GPG public key in the repo **euro-macromechanica-results**: [`keys/emm_pub_key.asc`](https://github.com/rleydev/euro-macromechanica-results/tree/main/keys/emm_pub_key.asc) 

```bash
# verify the GPG signature of the manifest
gpg --import keys/emm_pub_key.asc
gpg --verify integrity/artifacts_YYYY.sha256.asc integrity/artifacts_YYYY.sha256

# verify OpenTimestamps
ots verify integrity/artifacts_YYYY.sha256    # or: ots verify integrity/artifacts_YYYY.sha256.ots
```

> Keep **both** the **original** manifest (with absolute paths) and a **local** copy (`*.local.sha256`) side by side — the former is the signed record; the latter is convenient for `-c` checks.

---

## 🧠 FAQ

- **Do absolute paths break verification?**  
  No. SHA‑256 is computed **only from file contents**. Paths are just labels used by `-c` to open files. Use a local basename copy to avoid path issues.

- **CRLF/LF differences?**  
  In the examples we remove `\r` (`tr -d '\r'`) to make the normalized report’s SHA platform‑independent.

- **Duplicate basenames?**  
  If two different files share the same basename, create **separate local manifests** per subfolder, or rename files to avoid collisions.

- **What’s printed in the report?**  
  The **manifest’s** SHA‑256. Conversely, the manifest stores the **normalized report’s** SHA‑256 (the line `— Manifest SHA-256:` left without a value).

- **Does order of lines matter?**  
  Not for `-c`. For diffing in this guide we sort by filename for clarity.

---

**Done.** With these steps, anyone can reproduce verification on their machine — regardless of absolute paths in the manifest.
