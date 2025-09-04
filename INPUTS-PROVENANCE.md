# 🔗 Inputs — Provenance & Binding — Mapping Data‑Hub Inputs to Euro Macromechanica (EMM) Backtest Results
# 🔗 Inputs — Provenance & Binding — Mapping Data‑Hub Inputs to Euro Macromechanica (EMM) Backtest Results

This document explains **how** inputs from the **data‑hub** repository — (raw / prepared / calendars) — are mapped to the public **results** of the backtest. It documents the **binding logic** and provides **anchor tables** (SHA‑256, txid, block height, UTC time) for OTS.  
For concrete hash‑verification commands, see [results/docs/`INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md) — for raw HistData, prepared minute files, and economic calendars — and `analysis/ANALYSIS-INTEGRITY.md` (normalization nuance) for reconciling the analysis manifest with its reports, SVGs, and input data (raw HistData, calendars).

---

## 🎯 Purpose
- Identify **exactly which inputs** (raw minute data, prepared minute data, calendars) were used.
- Show **where hashes/signatures/OTS** are published to prove **time** and **integrity** of inputs.
- Provide a **simple mapping** from **data‑hub** to **results**.

## 📦 Scope (what counts as “inputs”)
- **RAW minute data** (*HistData*): `source_data/**`
- **PREPARED minute data** (normalized/deduped, UTC): `prepared/**`
- **Economic calendars** (aggregated meta‑info, UTC): `economic_calendars/**`

> ⚠️ Rights for **RAW** and **PREPARED** data remain with the original providers. This repository does **not** re‑license them.

---

## 🧩 Binding Logic

### 1) RAW → PREPARED in the *data‑hub*
- PREPARED files are produced from RAW by the analyzer and come with **analysis manifests** `analysis/YYYY/output_bundle_report/artifacts_YYYY.sha256` (mapping *source → output*).  
- The binding check is described in [`/analysis/ANALYSIS-INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/analysis/ANALYSIS-INTEGRITY.md).
- Therefore, PREPARED data are **cryptographically tied** to a specific RAW set.  
> 📌 **The analyzer has two major stages: minute‑data preparation and gap analysis. Economic calendars are also tied to the analysis manifest because they are used in gap analysis. Verifying against the analysis manifest confirms a complete, time‑bound linkage of all components.**

### 2) data‑hub — PREPARED → results — annual backtest outputs
- In *results*, each annual run has its own `artifacts_YYYY.sha256` (and `.asc`, `.ots` for HEADLINE), listing **all input files used** (including PREPARED minutes and calendars).  
- Binding check:
  1. Compare SHA‑256 of PREPARED files listed in **results** — `results/**/artifacts_YYYY.sha256` — with the SHA‑256 of the corresponding files in `prepared/YYYY/**` in the **data‑hub**.
  2. Do the same for calendar files: compare hashes from **results** with files in `economic_calendars/YYYY/**` in the **data‑hub**.

### 3) Roll‑up archives (OTS time anchors)
- Audit workflows are simplified by publishing **roll-up archives** (tar.gz/tar.xz) with corresponding **SHA-256, GPG, and OTS** for key input sets (“all PREPARED”, “all calendars”).
- These are published under **data‑hub** `integrity/**`. Roll‑ups **do not replace** per‑component manifests; they provide a **state‑at‑time proof** (anchored to Bitcoin).  
- An auditor can:
  - confirm that files unpacked from the archives match the hashes in the active folders (`source_data/`, `prepared/`, `economic_calendars/`), and  
  - confirm that **annual manifests in results** reference exactly those files (see step 2).

> 🧠 In short: the chain **RAW → PREPARED → Results** is validated by a combination of **per‑component manifests** and **roll‑up archives with OTS**.

---

## Anchor Tables

### A) RAW minute data (roll‑up archive)

| Field | Value |
|---|---|
| Archive | `eurusd_raw_2001-2025-07.tar.xz` |
| Contents | Raw 1‑minute data (M1) from HistData; unmodified |
| Hash function | `SHA-256` |
| Archive SHA‑256 | `7654b325da63fb415ad0a1aef17daf1a9f1ea721d0bf50413eacdd3d5c5bab7d` |
| GPG signature (.asc) | `integrity/source_data/eurusd_raw_2001-2025-07.tar.xz.sha256.asc` |
| OTS (.ots) | `integrity/source_data/eurusd_raw_2001-2025-07.tar.xz.sha256.ots` |
| Bitcoin txid | `d883cb3a197d8ed47a184b4dcd305047cedae9a0ad948bd7993737af571ce088` |
| Block height | `909599` |
| Block time (UTC) | `2025-08-11T19:21:02Z` |
| Link (data‑hub) | [`source_data/eurusd_raw_2001-2025-07.tar.xz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/source_data/eurusd_raw_2001-2025-07.tar.xz) |

---

### B) PREPARED minute data (roll‑up archive)

| Field | Value |
|---|---|
| Archive | `eurusd_prepared_2001-2025-07.tar.gz` |
| Contents | Prepared minute data (UTC±00:00) after normalization/filters |
| Hash function | `SHA-256` |
| Archive SHA‑256 | `e81f26072b48e62eb37dcd4da9919608e05da871b7264d3718e01244a2658d5f` |
| GPG signature (.asc) | `integrity/prepared/eurusd_prepared_2001-2025-07.tar.gz.sha256.asc` |
| OTS (.ots) | `integrity/prepared/eurusd_prepared_2001-2025-07.tar.gz.sha256.ots` |
| Bitcoin txid | `3646771ecc29d275b1b80ead9d5866a3b8867e6488df8d42145e2824a06e2a71` |
| Block height | `910536` |
| Block time (UTC) | `2025-08-18T02:06:26Z` |
| Link (data‑hub) | [`prepared/eurusd_prepared_2001-2025-07.tar.gz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/prepared/eurusd_prepared_2001-2025-07.tar.gz) |

---

### C) Economic calendars (roll‑up archive)

| Field | Value |
|---|---|
| Archive | `calendars_2001-2025-07.tar.gz` |
| Contents | Calendar metadata (central banks/stat agencies), release times in UTC |
| Hash function | `SHA-256` |
| Archive SHA‑256 | `0bd28458c49affc3b052116279827a8c840edf2dc4295d57a0b7e2a7b0b2e045` |
| GPG signature (.asc) | `integrity/economic_calendars/calendars_2001-2025-07.tar.gz.sha256.asc` |
| OTS (.ots) | `integrity/economic_calendars/calendars_2001-2025-07.tar.gz.sha256.ots` |
| Bitcoin txid | `a95e00f437575dad58c5e074352b6f4c9637ace705eccb05aa936e1cb99c6ffb` |
| Block height | `910177` |
| Block time (UTC) | `2025-08-15T16:31:10Z` |
| Link (data‑hub) | [`economic_calendars/calendars_2001-2025-07.tar.gz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/economic_calendars/calendars_2001-2025-07.tar.gz) |

---

## 🔍 Verification How‑To

- **[results/docs/`INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md)** — commands for verifying SHA‑256/GPG/OTS, including a note about **absolute paths** in manifests (how to “rebase” to relative for `sha256sum -c`).  
- **`analysis/ANALYSIS-INTEGRITY.md`** — a special note about **normalizing a line** in the annual report before hashing (to match the manifest).

---

## 📝 Notes

- Manifests may contain **absolute paths** — that does not affect hash correctness. For local checks, **rebase to relative paths** (see [results/docs/`INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md)).  
- This file documents the **binding logic**.
- Third‑party data remain under their providers’ terms; see `LICENSES.md` and `NOTICE-THIRD-PARTY*`.

---

## 🔗 Quick Links

- Detailed audit instructions: [results/docs/AUDIT.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.md)
- Verification guide: [results/docs/`INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md)  
- Analysis‑report verification nuance: [`analysis/ANALYSIS-INTEGRITY.md`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/analysis/ANALYSIS-INTEGRITY.md)  
- Raw data: [`source_data/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data)  
- Prepared minutes: [`prepared/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/prepared)  
- Calendars: [`economic_calendars/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/economic_calendars)  
- Results (annual manifests): see the **results** repository — (`artifacts_YYYY.sha256` + `.asc` + `.ots` for HEADLINE)
