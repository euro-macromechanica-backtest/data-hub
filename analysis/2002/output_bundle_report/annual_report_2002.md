# EURUSD 1m — Annual Report 2002

## Inputs used (hashes)
- DAT_ASCII CSV: 7005bc49535bffb4a4dee3e8fb189cc44f9ac12c04bb1f327f5b512ea46a7b85
- HistData TXT: 914d58534731d6f6d6c9800c6fb103b2e4907247f7a44be29077b197e3ce3bb1
- Calendar CSV: b171b9f1be57812951eb795528684b0392c20eea8e0589ae3791fb0529514f8d
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 2d34679122da2732132fc4da7837735c4b02d6076268597926e87eb41536966a

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2002.csv | `7005bc49535bffb4a4dee3e8fb189cc44f9ac12c04bb1f327f5b512ea46a7b85` |
| DAT_ASCII_EURUSD_M1_2002.txt | `914d58534731d6f6d6c9800c6fb103b2e4907247f7a44be29077b197e3ce3bb1` |
| calendar_2002.csv | `b171b9f1be57812951eb795528684b0392c20eea8e0589ae3791fb0529514f8d` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 3.1% | 3836h 50m |
| holiday | 1 | 0.1% | 42h 05m |
| event | 3 | 0.2% | 0h 30m |
| anomaly | 1608 | 96.7% | 412h 20m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 1544 |
| 30–59m | 46 |
| 60–179m | 8 |
| 180–359m | 4 |
| 360–719m | 6 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 915 |
| London | 134 |
| New York | 112 |
| Off-hours | 447 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 77 | 3000 |
| 02 | 67 | 1315 |
| 03 | 88 | 1065 |
| 04 | 158 | 2075 |
| 05 | 359 | 5030 |
| 06 | 203 | 2425 |
| 07 | 80 | 1625 |
| 08 | 93 | 1215 |
| 09 | 82 | 1485 |
| 10 | 140 | 1670 |
| 11 | 130 | 2150 |
| 12 | 131 | 1685 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2002-11-28 15:00:00 | 2002-11-29 00:00:00 | 540 |
| 2 | 2002-01-28 05:25:00 | 2002-01-28 13:35:00 | 490 |
| 3 | 2002-09-02 16:00:00 | 2002-09-03 00:05:00 | 485 |
| 4 | 2002-05-27 16:00:00 | 2002-05-28 00:00:00 | 480 |
| 5 | 2002-01-21 17:00:00 | 2002-01-22 00:10:00 | 430 |
| 6 | 2002-02-18 17:00:00 | 2002-02-19 00:00:00 | 420 |
| 7 | 2002-07-18 22:00:00 | 2002-07-19 03:35:00 | 335 |
| 8 | 2002-01-29 06:40:00 | 2002-01-29 12:05:00 | 325 |
| 9 | 2002-07-03 19:05:00 | 2002-07-04 00:00:00 | 295 |
| 10 | 2002-01-28 16:20:00 | 2002-01-28 19:30:00 | 190 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2002_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 81 |
| Gaps total | 1663 |
| ❗ Anomalies | 1608 |
| High events coverage (Economic Calendar) | 53/171 (31.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2002.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2002_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: fad458cd6f98c8071277e34e47625a57de8e08e373925de457ac5d1cfb8a32b5 Report generated with the help of ChatGPT (GPT-5 Thinking).
