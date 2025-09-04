# 📈 Minute Data (1m) Analysis for EUR/USD Backtesting

> 📅 **Coverage:** 2001-01-01 → 2025-07-31 (24 years 7 months)  
> 🕒 **Source TZ:** UTC-5 **FIXED** (no DST) → converted to **UTC+0**  
> 🌐 **Data source:** HistData.com  
> 🎯 **Purpose:** Backtesting (for trading strategy **EMM**)

---

## 🧭 Overview

Prepared and analyzed minute data for EUR/USD are available from **January 1, 2001** to **July 31, 2025**. The original quotes are standardized in **UTC-5 FIXED** and fully converted to **UTC+0**.

---

## 🛠️ Goal & Process

The data are prepared specifically **for backtesting the EMM trading strategy**. The pipeline includes:
- 🧹 removing duplicates and corrupted records;  
- 🧱 strict time sorting;  
- 🔁 converting all timestamps to **UTC+0**;  
- 🔎 gap analysis.

---

## ⚠️ Important

**HistData source specifics and limitations:**
- 🏷️ The official primary quote source is undisclosed (the exact broker/liquidity provider is unknown).  
- 🔁 The change frequency of the underlying source is unknown: over 24 years and 7 months, different providers might have been used.  
- 🧩 Historical non-homogeneity is possible: small quote discrepancies may occur when the provider changes.  
- ⛔ Periods with missing quotes (anomalous time gaps) do occur — all such cases are recorded in separate reports and accounted for in the analysis.

**Impact on backtest results:**  
due to the factors above, positive results will be **more conservative** (lower), because the strategy is tested under stricter conditions than perfectly clean data from a single provider.

**✅ Suitability for backtesting**  
The data are suitable for historical backtesting with the following caveats:
- **History non-homogeneity** — small discrepancies are possible due to provider changes.  
- **Presence of anomalous gaps** — missing data in certain periods (excluding weekends and official holidays).

**Conclusion:** a backtest on this dataset will likely produce **conservative** results compared to idealized market conditions. This increases the credibility of any recorded profitability.

---

## 🗂️ Structure

The prepared data and reports are organized by year (for **2025** — January–July at project start). Each `YYYY/` folder contains the main artifacts:

- 📥 **input data:** minute CSVs from HistData, the accompanying TXT report, and the corresponding `calendar_YYYY.csv`;  
- 🧪 **analyzed data:** quarterly archives `*.csv.gz` and, if needed, their decompressed CSV copies;  
- 🔐 **folders with SHA-256 and GPG signatures.**

```text
├─ prepared/
│  ├─ 2001/
│  │   ├─ EURUSD_M1_2001_Q1.csv.gz
│  │   ├─ EURUSD_M1_2001_Q2.csv.gz
│  │   ├─ EURUSD_M1_2001_Q3.csv.gz
│  │   ├─ EURUSD_M1_2001_Q4.csv.gz
│  │   ├─ EURUSD_M1_2001_Q1.csv       
│  │   └─ …
├─ analysis/                       
│  ├─ 2001/
│  │   ├─ annual_report_2001.md
│  │   ├─ EURUSD_2001_anomalies_M5.svg    
│  │   ├─ gaps_summary_2001.md 
│  │   ├─ EURUSD_M1_2001_Q4.csv.gz
│  │   └─ output_bundle_report/        
│  │      ├─ annual_report_2001.md
│  |      ├─ artifacts_2001.sha256
│  |      └─ …
└─ integrity/  
    ├─  prepared/                         
    |  └─ …
    └─   analysis/  
       └─ …
```

---

## 📊 Analysis & Reports

**Reports include:**  
- `annual_report_YYYY.md` — annual report;  
- `EURUSD_YYYY_anomalies_M5.svg.gz` — chart of anomalous M5 gaps (SVG, gzipped);  
- `gaps_summary_YYYY.md.gz` — complete list of anomalous gaps (deterministic gzip);  
- `artifacts_YYYY.sha256` — consolidated SHA-256 manifest.

**Analytical basis:** gap presence and duration are evaluated on **M5** (gaps > 5 minutes), because the strategy operates on **M5 and higher**. **Anomalous gaps** are gaps not falling into weekends and official holidays.

**The annual report contains:**  
- 📥 information about the input files;  
- 🧭 gap classification by cause (weekends, holidays, high-importance economic calendar events, anomalies);  
- ⏱️ gap-duration summary;  
- 🕓 distribution by sessions (for illustration; no DST applied);  
- 🗓️ monthly statistics;  
- 🚨 list of extreme gaps;  
- 📝 note: **CME/EBS** maintenance windows are not included as a cause because the strategy does not trade during these windows;  
- 🗺️ **SVG visualization** of anomalous gaps;  
- 📄 a separate file with the full list of anomalous gaps;  
- 🔔 the coverage percent of gaps by important economic-news releases (narrow window around the release);  
- 🎛️ **Continuity Score** for the period — a suitability metric for trading from M5 and higher.

**Important.** Unexpected global events (e.g., **CHF 2015**) are not treated as a separate cause. Gaps covered by the economic calendar are formally classified as anomalies but **do not reduce** the Continuity Score because the strategy **does not trade at the moment of the release**.

---

## 🧾 Prepared Data Periods (UTC+0)

```
2001-01-02 09:17:00 — 2001-12-31 08:27:00
2002-01-02 06:26:00 — 2002-12-31 17:58:00
2003-01-02 00:00:00 — 2003-12-31 19:58:00
2004-01-02 00:00:00 — 2004-12-31 21:28:00
2005-01-03 06:48:00 — 2005-12-29 21:58:00
2006-01-03 00:00:00 — 2006-12-29 21:28:00
2007-01-02 01:00:00 — 2007-12-31 21:57:00
2008-01-02 00:00:00 — 2008-12-31 20:58:00
2009-01-01 23:59:00 — 2009-12-31 21:57:00
2010-01-03 22:00:00 — 2010-12-31 19:58:00
2011-01-02 22:00:00 — 2011-12-30 21:58:00
2012-01-02 07:00:00 — 2012-12-31 21:58:00
2013-01-01 22:00:00 — 2013-12-31 20:59:00
2014-01-01 22:00:00 — 2014-12-31 21:59:00
2015-01-01 18:00:00 — 2015-12-31 21:58:00
2016-01-03 22:00:00 — 2016-12-30 21:58:00
2017-01-02 07:00:00 — 2017-12-29 21:57:00
2018-01-01 22:00:00 — 2018-12-31 21:59:00
2019-01-01 22:02:00 — 2019-12-31 21:59:00
2020-01-01 22:00:00 — 2020-12-31 21:58:00
2021-01-03 22:00:00 — 2021-12-31 21:58:00
2022-01-02 22:03:00 — 2022-12-30 21:58:00
2023-01-01 22:04:00 — 2023-12-29 21:58:00
2024-01-01 22:00:00 — 2024-12-31 21:58:00
2025-01-01 22:00:00 — 2025-07-25 05:00:00
```

---

## 🔍 Transparency & Compilation

Preparation and analysis were performed with **[minute_data_analyzer/](https://github.com/euro-macromechanica-backtest/minute-data-analyzer)**. For flexibility and efficiency, compilation was done in ChatGPT (Thinking & Pro). The detailed process is described in **[.../COMPILATION-GUIDE.md](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/analysis/COMPILATION-GUIDE.md)**.  
Use the analyzer to verify the transparency of the minute-data preparation and analysis by following the documented process.

---

## 🧪 Verifying Input/Output Hashes Against the Manifest - see [/ANALYSIS-INTEGRITY.md](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/analysis/ANALYSIS-INTEGRITY.md)

---

## 🛡️ Process Integrity

Integrity is ensured via **SHA-256** hashes of final files, **GPG signatures**, **Git history**, and **OTS anchore** of the archive of all backtest-ready CSVs from January 2001 through end of July 2025. Together, this guarantees the data has **not been curve‑fitted** to backtest results.
