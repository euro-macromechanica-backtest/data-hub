# Euro Macromechanica (EMM) Backtest — Data Hub  
**⚠️ Heads‑up: this repository contains third‑party datasets.**

> This repository is part of the **Euro Macromechanica (EMM) Backtest** ecosystem and serves as the data hub for **transparency and reproducibility** of the EMM strategy backtest. It hosts raw minute series (e.g., HistData), prepared files, compiled economic calendars, and analysis aggregates.

---

## ‼️ Please read the [Euro Macromechanica (EMM) Backtest — Overview & Methodology](https://github.com/euro-macromechanica-backtest/results/blob/main/README.md)

---

## 🔗 Related repositories

- **Backtest results, strategy validation and evidence, data‑quality policy (core baseline/extended baseline/stress), integrity materials** — *[results](https://github.com/euro-macromechanica-backtest/results)*  
- **Minute‑data and economic‑calendar normalizers; gap‑report analyzer** — *[data-preparation-toolkit](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit)*
- **Metric‑computation methodology and metrics calculator** for EMM backtest results — *[metrics-toolkit](https://github.com/euro-macromechanica-backtest/metrics-toolkit)*

---

## 🧭 Purpose

- Collect, normalize, and store source data for the EMM backtest.  
- Publish gap‑analysis aggregates and materials for independent verification.

The final data‑quality verdict and the rules for including years in **baseline/stress** are in the results repository:  
**`results` → [`data_quality_policy/`](https://github.com/euro-macromechanica-backtest/results/tree/main/data_quality_policy)**

---

## 🔐 Integrity artifacts

- All **RAW minute data** and gap **text reports** for **EUR/USD (Jan 2001 — Aug 2025)** under `source_data/raw/**` are accompanied by roll‑up `.sha256` manifests (SHA‑256 of all yearly files), a **GPG signature**, and an **OpenTimestamps (OTS)** anchor — attesting to the acquisition time.  
- All **PREPARED minute data** under `source_data/prepared/` — likewise: roll‑up `.sha256` / GPG / OTS.  
- Compiled **economic calendars** under `economic_calendars/` — likewise: roll‑up `.sha256` / GPG / OTS.  
- CSV files for the M5 gap assessment are accompanied by an `artifacts.sha256` manifest listing the **SHA-256 hashes of all input and output files**, enabling verification that outputs match the declared inputs without content changes. Additionally, a roll-up manifest aggregating all **.sha256 manifests, a GPG signature, and an OpenTimestamps (OTS) anchor** are provided.

Audit instructions: **[results/docs/AUDIT.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.md)**
Verification instructions for SHA-256, GPG signatures, and OpenTimestamps (OTS) anchors are available in **[results/docs/INTEGRITY.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md)**
Public GPG key (results repo):  
**`results` → [`keys/emm_pub_key.asc`](https://github.com/euro-macromechanica-backtest/results/tree/main/keys/emm_pub_key.asc)**

---

## 📁 Layout

```
source_data/raw            # raw third‑party datasets (original providers’ terms apply)
source_data/prepared/      # normalized/deduplicated files derived from source_data
economic_calendars/        # compiled calendar metadata (UTC and raw)
data_quality_analysis/     # aggregates: gaps, summary tables
integrity/                 # artifacts.sha256 (+ .asc, .ots) for verification
SOURCES.md                 # provenance (URLs)
LICENSES.md                # license map by folders
NOTICE-THIRD-PARTY.md      # third‑party rights notice
DATA-USAGE.md              # rules for using materials in this repository
INPUTS-PROVENANCE.md       # how inputs map to backtest results (RU version available)
```

---

## ⚖️ Licenses & rights

- Rights to **third‑party datasets** remain with their providers. This repository does **not** relicense external data.  
  See `LICENSES.md`, `NOTICE-THIRD-PARTY.md`, and `SOURCES.md`.
- Original aggregates/reports are covered by the licenses stated in `LICENSES.md`.
- **Takedown:** upon request by a third‑party rightsholder, the author will remove the relevant files within **five business days**.

---

## ✉️ Contacts

GitHub: **@rleydev (thelaziestcat)** · Email: **thelazyazzcat@gmail.com** / **thelaziestcat@proton.me**

---

> TL;DR: this repository is a **data and aggregates hub** equipped with verifiable integrity artifacts (SHA‑256 / GPG / OTS) to support reproducible EMM backtests.
