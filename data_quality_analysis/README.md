# 📈 Analysis of EUR/USD M1 Gap Reports

> 📅 **Coverage:** 2001-01-01 → 2025-08-31 (24 years, 8 months)  
> 🕒 **Original minute-data time zone:** **UTC−05:00 (fixed, no DST)**  
> 🌐 **Minute-data source:** HistData.com  
> 🎯 **Purpose:** backtesting (EMM trading strategy)

---

## 🧭 Overview

This analysis covers **annual gap/status reports** generated from EUR/USD minute data (HistData) for **January 1, 2001** through **August 31, 2025**.  
The underlying minute quotes are in **fixed UTC−05:00 (no DST)**. Prepared outputs and analysis results are organized by year (for **2025** — January–August).  
📥 **Inputs:** yearly text gap reports obtained from HistData (`source_data/raw/...txt`).

---

## 📊 Analysis Artifacts

- Bucketed gap counts (5-minute multiples):  
  `DAT_ASCII_EURUSD_M1_YYYY.txt_gap_bucket_counts.csv`
- By-date gap summary:  
  `DAT_ASCII_EURUSD_M1_YYYY.txt_gap_buckets_by_date.csv`
- Gap scatter SVG:  
  `DAT_ASCII_EURUSD_M1_YYYY.txt_gaps_scatter.svg`
- **Manifest** including SHA-256 for all input and output files.

**Analytical basis:** calculations are performed on an **M5** grid (gaps ≥ 5 minutes), since the strategy operates on the **M5 timeframe**.

---

## 🔍 Transparency & Reproducibility

The report analysis is produced with the **minute-data analyzer** module in the [`data-preparation-toolkit`](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit/tree/main/minute_data_analyzer).  
A **unified SHA-256 manifest of the yearly manifests** is available at `/integrity/data_quality_analysis` and is accompanied by a **GPG signature** and an **OpenTimestamps (OTS) anchor**.