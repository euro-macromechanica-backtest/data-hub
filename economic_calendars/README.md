## 📅 Economic Calendars for M5 EMM Backtest

### 2001-01-01 → 2025-08-31 — 24 years 8 months — UTC+00:00 🕒

---

> Economic calendars tailored to the **EUR/USD macro context**.  
> All timestamps are normalized to **UTC+00:00** with source-specific DST handling. (`prepared/...`) 🌐

---

## 📋 Overview

This calendar set is tuned for the **EUR/USD** macro context and covers **January 1, 2001** → **August 31, 2025**.  
Events are compiled from **official sources** 🏛️.

> Calendars were compiled manually (including via ChatGPT, Thinking/Pro modes) from official sites, which typically throttle automated scraping 🧩.

---

## 🧭 Time Standardization

All events are converted to **UTC+00:00**. DST transitions are accounted for per **original source**, using the [`economic calendar normalizer`](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit/tree/main/economic_calendar_normalizer) in **data-preparation-toolkit**, providing transparent and reproducible timestamps ✅.

---

## 🎯 Purpose

The macro context (**news filtering** 📰, **importance levels** 🔎, **country list** 🌍) is tailored for the **EMM M5 trading strategy backtests**.  
The strategy is sensitive **only to high-impact events** ⚠️.

---

## 📁 Structure

### 🗂️ Raw calendars

`raw/...` — calendars assembled in parts; event times remain in each source’s local time 🕰️.

### 🧰 Prepared calendars

`prepared/...` — merged and normalized to **UTC+00:00** 🌐. Split **by year** (for **2025**: January–August at the time the calendars were built).

See the **[integrity folder](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/integrity/economic_calendars)**:
- **SHA-256 manifest of all prepared calendar CSVs, GPG signature, and OTS anchor** 🔒✍️⛓️

Yearly CSVs include backtest-critical fields — **UTC datetime** 🗓️ and **importance** ⭐ — for window-based logic.

---

## 🧩 Coverage

The set includes all **high-importance** macro releases required for **M5 EMM** backtest ✅.

---

## 🌍 Countries

**🇺🇸 United States (US)** · **🇪🇺 Euro Area (EU)**

---

## 📰 Included events (author’s filter)

### 🇺🇸 United States

- FOMC rate decisions 🏛️💵; press conferences 🎙️; unscheduled high-importance events ⚠️  
- Jackson Hole ⛰️  
- Semiannual Monetary Policy testimony (Humphrey–Hawkins) 🏛️  
- FOMC Statements 📝  
- NFP 👷‍♂️📊  
- ISM PMI (Services/Manufacturing) 🏭📈  
- PPI 🏷️📈  
- GDP 📊  
- CPI 🧾📈  
- PCE 🧺📈  
- Retail Sales 🛍️📈  

### 🇪🇺 Euro Area

- ECB rate decisions 🏛️💶; press conferences 🎙️; unscheduled high-importance events ⚠️