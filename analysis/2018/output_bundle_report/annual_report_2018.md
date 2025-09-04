# EURUSD 1m — Annual Report 2018

## Inputs used (hashes)
- DAT_ASCII CSV: f32278dfac1cd7d0098144e31247435db197ef6ff491ab144b93d4cff3e985b0
- HistData TXT: d762a5fce34fa3e9f16a7c9e6616cc0e9e23500fcab97275ab1ea6d2958ba8bf
- Calendar CSV: 548faeb92db09973d4ea8186f99133b26a30be1ac1313879ded73ea349098209
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: d4462bc61f37808e035f908c42eb2ddc2cb83f62fccf543d846dbb032d2ff495

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2018.csv | `f32278dfac1cd7d0098144e31247435db197ef6ff491ab144b93d4cff3e985b0` |
| DAT_ASCII_EURUSD_M1_2018.txt | `d762a5fce34fa3e9f16a7c9e6616cc0e9e23500fcab97275ab1ea6d2958ba8bf` |
| calendar_2018.csv | `548faeb92db09973d4ea8186f99133b26a30be1ac1313879ded73ea349098209` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 88.1% | 2496h 00m |
| holiday | 1 | 1.7% | 14h 05m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 6 | 10.2% | 1h 00m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 6 |
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
| Off-hours | 6 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 0 | 0 |
| 02 | 0 | 0 |
| 03 | 0 | 0 |
| 04 | 2 | 20 |
| 05 | 0 | 0 |
| 06 | 1 | 10 |
| 07 | 0 | 0 |
| 08 | 1 | 10 |
| 09 | 1 | 10 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 1 | 10 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2018-04-01 22:35:00 | 2018-04-01 22:45:00 | 10 |
| 2 | 2018-04-01 22:45:00 | 2018-04-01 22:55:00 | 10 |
| 3 | 2018-06-03 22:45:00 | 2018-06-03 22:55:00 | 10 |
| 4 | 2018-08-26 22:20:00 | 2018-08-26 22:30:00 | 10 |
| 5 | 2018-09-02 22:10:00 | 2018-09-02 22:20:00 | 10 |
| 6 | 2018-12-24 22:00:00 | 2018-12-24 22:10:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2018_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 59 |
| ❗ Anomalies | 6 |
| High events coverage (Economic Calendar) | 0/174 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2018.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2018_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 2f5e3231c5271d1529f84abe1866f50eb2c1cc0d2aa0abdde9b3ea6628ca9043 Report generated with the help of ChatGPT (GPT-5 Thinking).
