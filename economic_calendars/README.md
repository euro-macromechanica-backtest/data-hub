<h1 align="center">📅 Economic Calendar for EUR/USD Backtest</h1>
<p align="center"><strong>2001-01-01 → 2025-07-31</strong> · <em>24 years, 7 months</em> · <code>UTC+0</code></p>
<p align="center">
  <img alt="Coverage" src="https://img.shields.io/badge/Coverage-2001%E2%80%932025-blue">
  <img alt="Time Zone" src="https://img.shields.io/badge/Time%20Zone-UTC%2B0-black">
  <img alt="Sources" src="https://img.shields.io/badge/Sources-Official%20only-brightgreen">
  <img alt="Use case" src="https://img.shields.io/badge/Use%20case-Backtesting-orange">
</p>

---

> A compact, source-verified economic calendar for the **EUR/USD** macro context.  
> Times are normalized to **UTC+0**, with daylight saving/standard time transitions accounted for per each original source.

## Overview

The calendar is adapted to the macroeconomic context of the **EUR/USD** pair and covers **January 1, 2001** → **July 31, 2025**.  
The database is compiled from **official sources**.

---

## Time Standardization

All events are converted to **UTC+0**. Transitions between daylight saving and standard time are handled according to each **original source**, ensuring transparent and reproducible timestamps.

> **Note**  
> Converted timestamps are intended for backtests and data alignment; they remain consistent with official publication schedules.

---

## Purpose

The macro context (**news filtering**, **importance levels**, **country list**) was adapted by the author specifically for **strategy backtesting**.  
The strategy is primarily sensitive to **high-importance** events; some **medium-importance** events are included to support future session logic.

---

## Structure

The calendar is split by **years** (for **2025** — January–July at the project start).  
Each `calendar_YYYY/` folder contains the main artifacts:

- **`.csv.gz` archive**  
- **CSV** (extracted/plain)  

See **[integrity folder](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/integrity/economic_calendars)**:

- **SHA-256 hashes** for `.csv.gz` and `.csv`  
- **GPG signatures** of the SHA-256 files
- *OTS anchoring** of the archive of all CSVs from 2001 through the end of July 2025


```text
economic_calendar/
├─ bundles_2001-2025/        # step-by-step build artifacts
├─ calendar_2001/
│  ├─ calendar_2001.csv.gz
│  └─ calendar_2001.csv
├─ calendar_2002/
│  └─ ...
└─ calendar_2025/            # Jan–Jul 2025
```

Annual CSVs include the key fields for backtests — **UTC date-time** and **importance** — for windowing logic and **EUR/USD minute-data** analysis. The strategy does **not** trade at the release moment; therefore indicator values (previous/actual) are out of scope.

> **Tip**  
> To verify integrity, compare annual `.csv.gz` and extracted `.csv` files against the published **SHA‑256** hashes.

---

## Data Coverage

The dataset contains all necessary **important** macroeconomic releases for **historical EUR/USD minute-data analysis** and **backtests**.

---

## Reports

- **Authenticity** — determined by whether the URL belongs to an **official domain**.  
- **Backtest suitability** — a function of (1) the source’s official status and (2) the availability of an **exact publication time**.

These grades are **auxiliary** for developing the **calendar builder** and are **not final**. Emphasis is on extracting **exact publication times** from official sources; some links may be generic or blank to speed up compilation.

> **Important**  
> During compilation of the economic calendar, conversion to **UTC+0** was performed correctly with daylight saving/time changes taken into account, without a rigid code implementation, thanks to compiling in **ChatGPT‑5 (Thinking & Pro)** modes.

**All events were gathered from official sources.**

---

## Countries

**United States (US)** · **Euro Area (EU)** · **United Kingdom (UK)** · **Switzerland (CH)**

---

## News Scope (Author’s Filter)

### 🇺🇸 United States (US)

- Fed rate decision; press conferences; unscheduled events  
- FOMC statements and minutes  
- NFP  
- ISM PMI  
- PPI  
- GDP  
- CPI  
- PCE  
- Retail Sales

### 🇪🇺 Euro Area (EU)

- ECB rate decision; press conferences; unscheduled events  
- Unemployment rate  
- HICP (final)  
- HICP (flash, since 2002)  
- GDP (final)  
- GDP (flash, since 2009)  
- **All PMI: final; flash (since 2014)**

### 🇬🇧 United Kingdom (UK)

- Bank of England rate decision; press conferences; unscheduled events  
- **All PMI: final; flash (since 2021)**

### 🇨🇭 Switzerland (CH)

- SNB rate decision; press conferences; unscheduled events

---

## ✏️ Author’s Adjustments to Importance

- **FOMC statements and minutes** — always **medium** (exception: **unscheduled** releases). Other **US economic events** — **high**.  
- **Euro Area** — **all PMI** → **medium**; other EU economic events — **high**.  
- **UK** and **CH** — all listed events → **medium**.

---

## ❓ FAQ — Why are some countries/indicators missing?

At the builder development stage, all EU countries were kept as options for future use.

The calendar is tuned to the **strategy’s requirements**: it does not trade during the narrow European session windows when most releases occur, and implementing that efficiently in code is impractical. Major **Euro Area** releases are included as exceptions. **PMIs** (EU, UK) are collected as **control points** for future use. Overall, these additional releases are **not required** for the current strategy.

---

## ⚠️ Exclusions

Unpredictable politico‑economic headlines are **not included**, since their exact publication times cannot be known in advance.  
The strategy already contains minimal logic (feasible to implement in code) for reacting to sudden news.

---

## 🛠 Compilation & Transparency

The calendar was compiled using **[economic_calendar_builder](https://github.com/euro-macromechanica-backtest/economic-calendar-builder)** and **ChatGPT‑5 (Thinking & Pro modes)** to improve efficiency. The builder implements the core data‑gathering logic; some parts are intentionally left lightweight to preserve flexibility in the research‑mode environment without excessive code in ChatGPT‑5 (Thinking & Pro) modes.

Use the builder for your own needs or to verify the transparency of this calendar, following the sections **Countries**, **News Scope**, **Author’s Adjustments to Importance**, and the correct conversion to **UTC+0** with daylight saving/time changes taken into account.

---

## 🔒 Process Integrity

Integrity is ensured via **SHA‑256** hashes of final files, **GPG signatures**, as well as **OTS anchoring** of the archive of all CSVs from 2001 through the end of July 2025. Taken together, this guarantees the calendar has **not** been curve‑fitted to backtest results.
