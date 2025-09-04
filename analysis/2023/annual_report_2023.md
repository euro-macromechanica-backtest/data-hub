# EURUSD 1m — Annual Report 2023

## Inputs used (hashes)
- DAT_ASCII CSV: 7f4bb88af747a61dce9ba21dd99f4585f3163e66a06d3f0df4c2343ecb1e9687
- HistData TXT: 49c6ee4f13495d5c53655329f27607efc5a74b1dde931465c604de7dd387deed
- Calendar CSV: be8b218671e9e886158f9f0e55e41728de2ab9cee381d91df4c0f09289bb33af
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: f8f64dce5b77fd59295f63b7b74c20219af0d737291fee8d0ee44b6122e0761d

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2023.csv | `7f4bb88af747a61dce9ba21dd99f4585f3163e66a06d3f0df4c2343ecb1e9687` |
| DAT_ASCII_EURUSD_M1_2023.txt | `49c6ee4f13495d5c53655329f27607efc5a74b1dde931465c604de7dd387deed` |
| calendar_2023.csv | `be8b218671e9e886158f9f0e55e41728de2ab9cee381d91df4c0f09289bb33af` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 6.7% | 2498h 35m |
| holiday | 7 | 0.9% | 15h 25m |
| event | 36 | 4.8% | 44h 00m |
| anomaly | 663 | 87.6% | 727h 45m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 19 |
| 30–59m | 2 |
| 60–179m | 641 |
| 180–359m | 1 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 43 |
| London | 236 |
| New York | 239 |
| Off-hours | 145 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 2 | 70 |
| 02 | 48 | 2790 |
| 03 | 130 | 8860 |
| 04 | 101 | 6910 |
| 05 | 135 | 8920 |
| 06 | 128 | 8310 |
| 07 | 113 | 7680 |
| 08 | 0 | 0 |
| 09 | 2 | 65 |
| 10 | 0 | 0 |
| 11 | 1 | 10 |
| 12 | 3 | 50 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2023-03-23 20:00:00 | 2023-03-23 23:00:00 | 180 |
| 2 | 2023-05-11 20:00:00 | 2023-05-11 22:00:00 | 120 |
| 3 | 2023-07-03 16:00:00 | 2023-07-03 18:00:00 | 120 |
| 4 | 2023-07-04 16:00:00 | 2023-07-04 18:00:00 | 120 |
| 5 | 2023-07-04 20:00:00 | 2023-07-04 22:00:00 | 120 |
| 6 | 2023-03-16 18:00:00 | 2023-03-16 20:00:00 | 120 |
| 7 | 2023-07-05 16:00:00 | 2023-07-05 18:00:00 | 120 |
| 8 | 2023-04-10 18:00:00 | 2023-04-10 20:00:00 | 120 |
| 9 | 2023-03-14 14:00:00 | 2023-03-14 16:00:00 | 120 |
| 10 | 2023-03-13 21:00:00 | 2023-03-13 23:00:00 | 120 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2023_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 66 |
| Gaps total | 757 |
| ❗ Anomalies | 663 |
| High events coverage (Economic Calendar) | 43/171 (25.1%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2023.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2023_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: b6c5f9c4c56c0d18d64e257329c41d6823087bce34d7ea837b977e67776de7e7 Report generated with the help of ChatGPT (GPT-5 Thinking).
