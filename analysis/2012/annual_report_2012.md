# EURUSD 1m — Annual Report 2012

## Inputs used (hashes)
- DAT_ASCII CSV: 7985d67946bad41b1cd0f2fc110538d19adf5a4ae6dffcdffee8a0d294605c9d
- HistData TXT: a81d39694bc01f24bd0c9c74dcef4ca4ada97f4675ee9ab114862191749e7eb9
- Calendar CSV: e31ed4c1b7187a4c0c866bf6ee95e65d18d69a2c8087f7a1527e4aedde2696ef
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 47211449e63a087d090a175be62e8edb500ec529d861e3f2773cb72bc3dcd4d6

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2012.csv | `7985d67946bad41b1cd0f2fc110538d19adf5a4ae6dffcdffee8a0d294605c9d` |
| DAT_ASCII_EURUSD_M1_2012.txt | `a81d39694bc01f24bd0c9c74dcef4ca4ada97f4675ee9ab114862191749e7eb9` |
| calendar_2012.csv | `e31ed4c1b7187a4c0c866bf6ee95e65d18d69a2c8087f7a1527e4aedde2696ef` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 96.3% | 2496h 00m |
| holiday | 1 | 1.9% | 38h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 1 | 1.9% | 0h 10m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 1 |
| 30–59m | 0 |
| 60–179m | 0 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 0 |
| London | 0 |
| New York | 0 |
| Off-hours | 1 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 0 | 0 |
| 02 | 0 | 0 |
| 03 | 0 | 0 |
| 04 | 0 | 0 |
| 05 | 0 | 0 |
| 06 | 0 | 0 |
| 07 | 0 | 0 |
| 08 | 0 | 0 |
| 09 | 1 | 10 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 0 | 0 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2012-09-10 22:05:00 | 2012-09-10 22:15:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2012_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 54 |
| ❗ Anomalies | 1 |
| High events coverage (Economic Calendar) | 0/177 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2012.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2012_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 25f8830a742e76f938fa1f402507e2cf7175566b03be38047f419127e129b921 Report generated with the help of ChatGPT (GPT-5 Thinking).
