# EURUSD 1m — Annual Report 2021

## Inputs used (hashes)
- DAT_ASCII CSV: 6e342873e2c7d6aafe820a01577ccd2d4b243f96badd9b4b3a95f6cfb80593f8
- HistData TXT: 4e8a51018795c2cf68bee288d2b051f5c7ddc2de84e4c5d9071c73f68423df40
- Calendar CSV: be3f8bef14697c7abfe04f502825bfe13721d1b67654367cdeaee7fab6442bb4
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 791a6d965e67398a1144412d998fa4ad3b5640c0c7b04365bf833cc065fbe18b

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2021.csv | `6e342873e2c7d6aafe820a01577ccd2d4b243f96badd9b4b3a95f6cfb80593f8` |
| DAT_ASCII_EURUSD_M1_2021.txt | `4e8a51018795c2cf68bee288d2b051f5c7ddc2de84e4c5d9071c73f68423df40` |
| calendar_2021.csv | `be3f8bef14697c7abfe04f502825bfe13721d1b67654367cdeaee7fab6442bb4` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 77.3% | 2448h 50m |
| holiday | 0 | 0.0% | 0h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 15 | 22.7% | 23h 20m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 13 |
| 30–59m | 0 |
| 60–179m | 1 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 1 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 3 |
| London | 0 |
| New York | 0 |
| Off-hours | 12 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 1 | 10 |
| 02 | 1 | 10 |
| 03 | 1 | 60 |
| 04 | 4 | 50 |
| 05 | 4 | 1230 |
| 06 | 0 | 0 |
| 07 | 0 | 0 |
| 08 | 1 | 10 |
| 09 | 1 | 10 |
| 10 | 1 | 10 |
| 11 | 0 | 0 |
| 12 | 1 | 10 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2021-05-31 05:00:00 | 2021-06-01 01:00:00 | 1200 |
| 2 | 2021-03-29 00:00:00 | 2021-03-29 01:00:00 | 60 |
| 3 | 2021-04-20 22:15:00 | 2021-04-20 22:30:00 | 15 |
| 4 | 2021-04-26 22:25:00 | 2021-04-26 22:40:00 | 15 |
| 5 | 2021-01-18 22:20:00 | 2021-01-18 22:30:00 | 10 |
| 6 | 2021-02-08 22:45:00 | 2021-02-08 22:55:00 | 10 |
| 7 | 2021-04-15 22:15:00 | 2021-04-15 22:25:00 | 10 |
| 8 | 2021-04-20 22:05:00 | 2021-04-20 22:15:00 | 10 |
| 9 | 2021-05-03 22:20:00 | 2021-05-03 22:30:00 | 10 |
| 10 | 2021-05-13 22:15:00 | 2021-05-13 22:25:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2021_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 98 |
| Gaps total | 66 |
| ❗ Anomalies | 15 |
| High events coverage (Economic Calendar) | 0/167 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2021.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2021_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 3b220417f82498d4a7943874132289df24c645b2c6d7deb5c10f65e34a6b11d5 Report generated with the help of ChatGPT (GPT-5 Thinking).
