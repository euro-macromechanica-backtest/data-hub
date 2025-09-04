# EURUSD 1m — Annual Report 2013

## Inputs used (hashes)
- DAT_ASCII CSV: 293ec3e7f1f9a863e14d1be58aca5d5ca716b9c67eb4c33cbe58890eaf916787
- HistData TXT: 334e0e3f749c3edda0f466665a8c2aa5e6fbfecb3e6adfd1690b19c707355c3d
- Calendar CSV: 6056efd18410823e02e91e8bbf53de7dde7cf4dd0d166cd3c0e54ba600a98f93
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: dbd1b1fe1d1be8cd94ca66372ac42a62abe66af91a0817e73bd4c5ab1197c477

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2013.csv | `293ec3e7f1f9a863e14d1be58aca5d5ca716b9c67eb4c33cbe58890eaf916787` |
| DAT_ASCII_EURUSD_M1_2013.txt | `334e0e3f749c3edda0f466665a8c2aa5e6fbfecb3e6adfd1690b19c707355c3d` |
| calendar_2013.csv | `6056efd18410823e02e91e8bbf53de7dde7cf4dd0d166cd3c0e54ba600a98f93` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 91.2% | 2496h 00m |
| holiday | 1 | 1.8% | 39h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 4 | 7.0% | 1h 10m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 3 |
| 30–59m | 1 |
| 60–179m | 0 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1 |
| London | 1 |
| New York | 2 |
| Off-hours | 0 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 0 | 0 |
| 02 | 0 | 0 |
| 03 | 1 | 10 |
| 04 | 1 | 35 |
| 05 | 1 | 10 |
| 06 | 0 | 0 |
| 07 | 0 | 0 |
| 08 | 0 | 0 |
| 09 | 0 | 0 |
| 10 | 0 | 0 |
| 11 | 1 | 15 |
| 12 | 0 | 0 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2013-04-12 00:15:00 | 2013-04-12 00:50:00 | 35 |
| 2 | 2013-11-07 13:55:00 | 2013-11-07 14:10:00 | 15 |
| 3 | 2013-03-13 17:20:00 | 2013-03-13 17:30:00 | 10 |
| 4 | 2013-05-27 19:30:00 | 2013-05-27 19:40:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2013_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 57 |
| ❗ Anomalies | 4 |
| High events coverage (Economic Calendar) | 0/174 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2013.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2013_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 1fab46d4d4e40a4ebb6e636613d31305f638d06ed1c1bb796f686f1ad5552aa3 Report generated with the help of ChatGPT (GPT-5 Thinking).
