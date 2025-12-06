# 📂 EUR/USD & GBP/USD Minute Data — Raw, Prepared, and Gap Reports. Source: [HistData](https://www.histdata.com)

**EUR/USD minute data (January 2001 through August 31, 2025) & GBP/USD (January 2008 through August 31, 2025)**

## 📌 Source & Format

The history comes from **[HistData](https://www.histdata.com)** in **Generic ASCII M1** format:  
<http://www.histdata.com/download-free-forex-historical-data/?/ascii/1-minute-bar-quotes/EURUSD>

<http://www.histdata.com/download-free-forex-historical-data/?/ascii/1-minute-bar-quotes/GBPUSD>

---

**Raw M1 data** — timestamps in **fixed EST (UTC−05:00, no DST)**. See the FAQ: <http://www.histdata.com/f-a-q/>  
Paths: `raw/...csv`

**Gap reports** — plain-text companions to each yearly raw M1 dataset.  
Paths: `raw/...txt`

**Prepared M1 data** — backtest-ready minute series in **UTC+00:00**, with **no artificial gap filling**; delimiter: semicolon `;`.  
Paths: `/prepared/...csv`
*(Minute-level data were prepared using the [minute data normalizer](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit/tree/main/minute_data_normalizer) in the `data-preparation-toolkit` repository.)*


**Reference tick data from HistData** — for quality cross-checks.  
Paths: `tick_data_reference/...`

---

## 📜 Transparency

To provide transparency and prove the authenticity of the source data, we publish:

1. **Unified SHA-256 manifest `eurusd_raw_2001-2025-08.sha256`** — includes all raw yearly M1 files obtained from HistData.  
2. **Unified SHA-256 manifests `eurusd_prepared_2001-2025-08.sha256` & `gbpusd_prepared_2008-2025-08.sha256`** — include all prepared yearly M1 files.  
3. **Unified SHA-256 manifest `status_reports_2001-2025-08.sha256`** — includes all gap-report text files that accompany the raw yearly M1 data from HistData.  
4. **Unified SHA-256 manifest ``gbpusd_raw_status_reports_2008-2025-08.sha256`** - includes all raw yearly M1 files and all gap-report text files that accompany the raw yearly M1 data from HistData
4. **SHA-256 hashes, GPG signatures, and OTS anchors for a random sample of monthly tick data** from HistData — as a reference illustrating known limitations in tick feeds.

Each manifest is itself published with a **SHA-256 hash**, a **GPG signature**, and an **OpenTimestamps (OTS) anchor** recorded on-chain.

**Link:**  
[/integrity/source_data/...](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/integrity/source_data)

---

## 🔍 What these attest

- **SHA-256 hash** — verifies file integrity.  
- **GPG signature** — verifies authorship and authenticity.  
- **OTS anchor** — provides a blockchain timestamp proving the data existed at a specific point in time.

---

## ⚠️ Important
- The datasets were pulled from **[HistData](https://www.histdata.com)** when they were available in their original form.  
- **HistData** may revise their archives over time (including removing gaps).  
- The hashes, signatures, and OTS anchors prove the backtest was run on **exactly these files**, not on a later-modified set.  
- **License / Terms:** the original provider’s terms apply; re-licensing via this repository is **not** permitted.