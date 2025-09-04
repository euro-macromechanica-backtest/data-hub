# Euro Macromechanica (EMM) Backtest — Data Hub  
**⚠️ Heads‑up: this repository contains third‑party datasets.**

This repository is part of the **Euro Macromechanica (EMM) Backtest** ecosystem. It serves as a data hub for **transparency and reproducibility** of the EMM backtest: raw minute feeds (e.g., HistData), prepared files, compiled calendars, and analysis aggregates live here.

---

## ‼️ Read the **Euro Macromechanica (EMM) Backtest** ecosystem’s main [results/`README.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/README.md)!

---

## 🔗 Related ecosystem

- **Backtest results, strategy‑proofs, data quality policy, integrity artifacts** – [*results*](https://github.com/euro-macromechanica-backtest/results)
- **Minute-data analysis and normalization toolkit** – [*minute-data-analyzer*](https://github.com/euro-macromechanica-backtest/minute-data-analyzer)
- **Economic calendar builder** – [*economic-calendar-builder*](https://github.com/euro-macromechanica-backtest/economic-calendar-builder)

---

## 🧭 Purpose

- Collect, normalize, and store source data used in the EMM backtest.
- Publish analysis aggregates (gaps/continuity, etc.) and integrity materials so anyone can verify the released results.
- For detailed preparation processes, see [`economic_calendars/README.md`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/economic_calendars/README.md) (calendar collection & normalization)
  and [`analysis/README.md`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/analysis/README.md) (gap/continuity metrics and summaries).

The final data‑quality verdict and the **headline/stress** inclusion rules are published in the results repository:  
**`results` → [`data_quality_policy/…`](https://github.com/euro-macromechanica-backtest/results/blob/main/data_quality_policy)**

---

## 🔐 Integrity artifacts

- All EUR/USD minute data **(Jan‑2001 — end of Jul‑2025)** under `source_data/` is accompanied by an archive signed with **SHA‑256**, **GPG**, and **OpenTimestamps (OTS)** to anchor the acquisition moment.
- Compiled economic calendars are treated the same way (SHA‑256 / GPG / OTS).
- Analysis reports are released as bundles with an `artifacts.sha256` manifest listing **hashes of every input and output file**. This lets you verify that the released result matches the declared inputs (without modifying file contents).

Read [**results/docs/`AUDIT.md`**](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.md) for detailed verification steps.

**Note:** SHA-256 hashes may include absolute file paths; this does not affect hash validity. For verification with absolute paths, see [**results/docs/`INTEGRITY.md`**](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.md) (“Absolute paths” section).

Public GPG key see in the repo:  
**`results` → [`keys/emm_public_key.asc`](https://github.com/euro-macromechanica-backtest/results/tree/main/keys/emm_pub_key.asc)**

---

## 📁 Layout

```
source_data/               # raw third‑party datasets (original providers' terms apply)
prepared/                  # normalized/cleaned files derived from source_data
economic_calendars/        # compiled calendar metadata (UTC), where the source permits it
                           # details: economic_calendars/README.md
analysis/                  # aggregates: gaps, continuity metrics, summary tables
                           # details: analysis/README.md
integrity/                 # artifacts.sha256 (+ .asc, .ots) for verification
SOURCES.md                 # provenance (URLs, SHA‑256)
LICENSES.md                # license map by folders
NOTICE-THIRD-PARTY.md      # third‑party rights notice
DATA-USAGE.md              # how materials in this repo may be used

```

---

## ⚖️ Licenses & rights

- Rights in **third‑party datasets** remain with their original providers. This repository does **not** re‑license them.  
  See `LICENSES.md`, `NOTICE-THIRD-PARTY.md`, and `SOURCES.md`.
- Our own aggregates/reports are licensed as specified in `LICENSES.md`.
- **Takedown:** upon a valid request from a third‑party rightsholder, the relevant files will be removed within **5 business days**.

---

## ✉️ Contact
GitHub: **@rleydev (thelaziestcat)** · Email: **thelaziestcat@proton.me** / **thelazyazzcat@gmail.com**

---

> TL;DR: this is a **data & aggregates hub** with verifiable integrity artifacts (SHA‑256/GPG/OTS) for EMM backtest reproducibility.
