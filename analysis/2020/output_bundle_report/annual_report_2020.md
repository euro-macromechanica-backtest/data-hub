# EURUSD 1m — Annual Report 2020

## Inputs used (hashes)
- DAT_ASCII CSV: 5230a240dd76344a50c90980fc7594dd29751e602eb778c8c3710626cf9cd662
- HistData TXT: 806bbe1b59085c117f57dcca39f54c5ab142d90793120f76d635d93b8cb726d0
- Calendar CSV: f8e473c0bf7d6381b16464a1fced6fb01a9685fddf825a4339c9ecd239904220
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 8e2b42e56db40cc3e58ab0f5d3fa8b78b14bdaf5a6fb1260e9fbdfee1a0f8d15

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2020.csv | `5230a240dd76344a50c90980fc7594dd29751e602eb778c8c3710626cf9cd662` |
| DAT_ASCII_EURUSD_M1_2020.txt | `806bbe1b59085c117f57dcca39f54c5ab142d90793120f76d635d93b8cb726d0` |
| calendar_2020.csv | `f8e473c0bf7d6381b16464a1fced6fb01a9685fddf825a4339c9ecd239904220` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 80.0% | 2510h 55m |
| holiday | 0 | 0.0% | 0h 00m |
| event | 1 | 1.5% | 19h 00m |
| anomaly | 12 | 18.5% | 3h 20m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 10 |
| 30–59m | 1 |
| 60–179m | 1 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1 |
| London | 0 |
| New York | 0 |
| Off-hours | 11 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 0 | 0 |
| 02 | 1 | 15 |
| 03 | 2 | 70 |
| 04 | 0 | 0 |
| 05 | 0 | 0 |
| 06 | 0 | 0 |
| 07 | 0 | 0 |
| 08 | 2 | 20 |
| 09 | 3 | 35 |
| 10 | 1 | 10 |
| 11 | 0 | 0 |
| 12 | 3 | 50 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2020-03-30 00:00:00 | 2020-03-30 01:00:00 | 60 |
| 2 | 2020-12-24 22:15:00 | 2020-12-24 22:45:00 | 30 |
| 3 | 2020-02-11 21:00:00 | 2020-02-11 21:15:00 | 15 |
| 4 | 2020-09-09 22:35:00 | 2020-09-09 22:50:00 | 15 |
| 5 | 2020-03-30 22:00:00 | 2020-03-30 22:10:00 | 10 |
| 6 | 2020-08-11 22:50:00 | 2020-08-11 23:00:00 | 10 |
| 7 | 2020-08-25 22:05:00 | 2020-08-25 22:15:00 | 10 |
| 8 | 2020-09-03 22:50:00 | 2020-09-03 23:00:00 | 10 |
| 9 | 2020-09-10 22:05:00 | 2020-09-10 22:15:00 | 10 |
| 10 | 2020-10-19 22:30:00 | 2020-10-19 22:40:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2020_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 65 |
| ❗ Anomalies | 12 |
| High events coverage (Economic Calendar) | 3/173 (1.7%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2020.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2020_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 4a82765957aa4ead5b69b815e0b225a7a4d155f01090d4980cc9617cca82b908 Report generated with the help of ChatGPT (GPT-5 Thinking).
