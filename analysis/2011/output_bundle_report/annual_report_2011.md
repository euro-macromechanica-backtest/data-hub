# EURUSD 1m — Annual Report 2011

## Inputs used (hashes)
- DAT_ASCII CSV: de51dd1d9404ebf2dd8cbc091cf1f66427f8a51b9e786f87cc237f39e554259a
- HistData TXT: 9146b619d6005854d8d93996efa832aea6850fb27779475e54eb177171d21d31
- Calendar CSV: 82614323a75f57df87e3bdcfd0332c0bba7864590a7171fe1612f11ef078692e
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 266b60df1744a87dad88ff6689a296701f39c8a3238bc37877b883f7035805b6

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2011.csv | `de51dd1d9404ebf2dd8cbc091cf1f66427f8a51b9e786f87cc237f39e554259a` |
| DAT_ASCII_EURUSD_M1_2011.txt | `9146b619d6005854d8d93996efa832aea6850fb27779475e54eb177171d21d31` |
| calendar_2011.csv | `82614323a75f57df87e3bdcfd0332c0bba7864590a7171fe1612f11ef078692e` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 45.5% | 2457h 00m |
| holiday | 9 | 8.0% | 1h 45m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 52 | 46.4% | 8h 45m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 52 |
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
| Asia | 14 |
| London | 0 |
| New York | 5 |
| Off-hours | 33 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 5 | 50 |
| 02 | 6 | 60 |
| 03 | 10 | 105 |
| 04 | 11 | 110 |
| 05 | 1 | 10 |
| 06 | 2 | 20 |
| 07 | 5 | 50 |
| 08 | 2 | 20 |
| 09 | 3 | 30 |
| 10 | 2 | 20 |
| 11 | 3 | 30 |
| 12 | 2 | 20 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2011-03-29 05:10:00 | 2011-03-29 05:25:00 | 15 |
| 2 | 2011-01-03 04:50:00 | 2011-01-03 05:00:00 | 10 |
| 3 | 2011-04-14 23:50:00 | 2011-04-15 00:00:00 | 10 |
| 4 | 2011-04-21 22:30:00 | 2011-04-21 22:40:00 | 10 |
| 5 | 2011-04-25 00:25:00 | 2011-04-25 00:35:00 | 10 |
| 6 | 2011-04-25 23:15:00 | 2011-04-25 23:25:00 | 10 |
| 7 | 2011-05-04 23:10:00 | 2011-05-04 23:20:00 | 10 |
| 8 | 2011-06-02 23:10:00 | 2011-06-02 23:20:00 | 10 |
| 9 | 2011-06-05 22:20:00 | 2011-06-05 22:30:00 | 10 |
| 10 | 2011-07-01 21:20:00 | 2011-07-01 21:30:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2011_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 112 |
| ❗ Anomalies | 52 |
| High events coverage (Economic Calendar) | 1/172 (0.6%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2011.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2011_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 3b4302d1b3ca28e5753e21059c9d3d9597103367fce5454c9c0ccd2477a85708 Report generated with the help of ChatGPT (GPT-5 Thinking).
