# 🔗 Inputs — Provenance & Binding — How Inputs Map to Euro Macromechanica (EMM) Backtest Results

This note documents **exactly how** inputs from the **data-hub** repository (`raw/`, `prepared/`, `economic_calendars/`)
are mapped to their usage in the public **results** backtest repository. It explains the **binding logic** end-to-end.  
For step-by-step hash-verification commands, see [results/docs/INTEGRITY.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md) — covering RAW HistData, PREPARED, and economic calendars.

---

## 🎯 Purpose
- Specify **which inputs** (raw minute data, prepared minute data, calendars) were used.
- Show **where to find hashes/signatures/OTS** that attest to the **timestamp** and **integrity** of the inputs.
- Provide a **simple correspondence map** between **data-hub** and **results**.

## 📦 Scope (what counts as “inputs”)
- **RAW minute data** (*HistData*): `source_data/raw/**`
- **PREPARED minute data** (normalized/deduplicated, UTC): `source_data/prepared/**`
- **Economic calendars** (aggregated metadata, UTC): `economic_calendars/prepared/**`

> ⚠️ Rights to **RAW** and **PREPARED** data remain with the original providers. This repository does **not** relicense them.

---

## 🧩 Binding Logic

### 1) RAW → PREPARED in **data-hub**
- PREPARED files are produced **deterministically** from RAW by the normalizer.  
  With the **minute data normalizer** and pinned Python/dependency versions (see `requirements.lock`), identical inputs yield **identical SHA-256** outputs — **across operating systems**.
- Therefore, PREPARED data are **cryptographically bound** to a specific RAW set.
- ▶️ Refer to the normalizer’s **README** and **`requirements.lock`** for exact versions and run parameters.

> 📌 The normalizer uses a deterministic workflow. When the Python version (e.g., 3.13.x) and packages from `requirements.lock` are respected, input/output CSV hashes are stable and reproducible.

### 2) **data-hub** (PREPARED) → **results** (annual runs)
- In **results**, each yearly run has its own `artifacts_YYYY.sha256` (plus `.asc`, `.ots` for BASELINE), enumerating **all input files** used (including PREPARED minutes and economic calendars).
- How to verify the link:
  1. Compare SHA-256 of PREPARED files listed in `results/**/artifacts_YYYY.sha256`
     with SHA-256 of the corresponding files in `source_data/prepared/YYYY/...csv` (in **data-hub**).
     In other words: **download the PREPARED CSVs, compute the hash locally, and match it to the `artifacts_YYYY.sha256` manifest**.
  2. Do the same for calendar files: match hashes from `results/**/artifacts_YYYY.sha256`
     to files under `economic_calendars/**` (in **data-hub**).

### 3) Roll-up manifests (OTS timestamping)
- To support audits, roll-up manifests (`.sha256`, with **GPG** and **OTS**) are provided for key input sets (e.g., "all PREPARED", "all calendars").
- Corresponding GPG signatures and OTS proofs are available under **data-hub** `integrity/**`, providing **timestamped proof of the dataset’s state** (via OpenTimestamps/Bitcoin).
- Auditor checklist:
  - verify that hashes in the roll-up manifest match current files in `source_data/raw/YYYY/`, `source_data/prepared/YYYY/`, and `economic_calendars/`;
  - verify that the **yearly manifests in results** reference the **same files** (see Step 2).

> 🧠 Bottom line: the **RAW → PREPARED → Results** chain is attested by **component manifests** and by **roll-up manifests with GPG signatures and OTS proofs**.

---

## 📝 Notes
- This file describes the **binding logic**.
- ▶️ Also see the minute-data normalizer **README** and **`requirements.lock`** (exact Python/package versions).
- Third-party data remain under their providers’ terms; see `LICENSES.md` and `NOTICE-THIRD-PARTY*`.

---

## 🔗 Quick links
- Audit guide: [results/docs/AUDIT.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.md)
- Verification guide: [results/docs/INTEGRITY.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md)
- RAW data: [`source_data/raw`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data/raw)
- PREPARED minutes: [`source_data/prepared/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data/prepared)
- Calendars: [`economic_calendars/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/economic_calendars)
- Results (yearly manifests): **results** repo (`artifacts_YYYY.sha256` + `.asc` + `.ots` for BASELINE)
- Minute data normalizer [data-preparation-toolkit/minute_data_normalizer](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit/tree/main/minute_data_normalizer)