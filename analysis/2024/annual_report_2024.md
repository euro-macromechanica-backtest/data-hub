# EURUSD 1m — Annual Report 2024

## Inputs used (hashes)
- DAT_ASCII CSV: 0f2412690abe983064f665f3273bd24553e2f4f7bfe96a606b30f65fd74b231d
- HistData TXT: 81a82c6cadf4069e7be4c68530dec73c7672b2a934a8e6c3f6487c43b8b72758
- Calendar CSV: a0dd0b8863f7e7159f1e7fd5978000d03f0ba88e05321bc78379532777fb81ca
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 0ce5bac482f103e56daf44989fa82c627036f8a22e39304292a56d87b4e871ca

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2024.csv | `0f2412690abe983064f665f3273bd24553e2f4f7bfe96a606b30f65fd74b231d` |
| DAT_ASCII_EURUSD_M1_2024.txt | `81a82c6cadf4069e7be4c68530dec73c7672b2a934a8e6c3f6487c43b8b72758` |
| calendar_2024.csv | `a0dd0b8863f7e7159f1e7fd5978000d03f0ba88e05321bc78379532777fb81ca` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 67.5% | 2497h 25m |
| holiday | 11 | 14.3% | 16h 10m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 14 | 18.2% | 7h 50m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 10 |
| 30–59m | 0 |
| 60–179m | 3 |
| 180–359m | 1 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1 |
| London | 0 |
| New York | 3 |
| Off-hours | 10 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 3 | 300 |
| 02 | 0 | 0 |
| 03 | 0 | 0 |
| 04 | 2 | 70 |
| 05 | 1 | 10 |
| 06 | 2 | 20 |
| 07 | 0 | 0 |
| 08 | 0 | 0 |
| 09 | 0 | 0 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 6 | 70 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2024-01-16 21:00:00 | 2024-01-17 00:00:00 | 180 |
| 2 | 2024-01-15 19:00:00 | 2024-01-15 20:00:00 | 60 |
| 3 | 2024-01-16 17:00:00 | 2024-01-16 18:00:00 | 60 |
| 4 | 2024-04-01 00:00:00 | 2024-04-01 01:00:00 | 60 |
| 5 | 2024-12-24 23:15:00 | 2024-12-24 23:30:00 | 15 |
| 6 | 2024-12-24 23:35:00 | 2024-12-24 23:50:00 | 15 |
| 7 | 2024-04-28 22:15:00 | 2024-04-28 22:25:00 | 10 |
| 8 | 2024-05-26 22:20:00 | 2024-05-26 22:30:00 | 10 |
| 9 | 2024-06-19 19:25:00 | 2024-06-19 19:35:00 | 10 |
| 10 | 2024-06-24 23:50:00 | 2024-06-25 00:00:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2024_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 77 |
| ❗ Anomalies | 14 |
| High events coverage (Economic Calendar) | 0/171 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2024.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2024_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: d4e042284f8dc931c32ce8703fc2e3a8bf07b2b3563cec608298c655abaa7c52 Report generated with the help of ChatGPT (GPT-5 Thinking).
