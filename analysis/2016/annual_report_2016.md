# EURUSD 1m — Annual Report 2016

## Inputs used (hashes)
- DAT_ASCII CSV: 9f1567957a0203f44c7e995a96fc0a7eca2bc0d0d2a4dee0a2c153a133aee2e6
- HistData TXT: b1fc44175190b4e34e0d8e378baf51c9afc70a305feb843c78761dbc0a6cb971
- Calendar CSV: 14c55f2ea43d47b7bd0b844728e1c666b8f528ae557aed27e6c17cc955f20056
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 55387a1890cf7624bef0627fd406b6e78ea0d92906c283ea7f83ced6aec0f13c

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2016.csv | `9f1567957a0203f44c7e995a96fc0a7eca2bc0d0d2a4dee0a2c153a133aee2e6` |
| DAT_ASCII_EURUSD_M1_2016.txt | `b1fc44175190b4e34e0d8e378baf51c9afc70a305feb843c78761dbc0a6cb971` |
| calendar_2016.csv | `14c55f2ea43d47b7bd0b844728e1c666b8f528ae557aed27e6c17cc955f20056` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 94.4% | 2448h 40m |
| holiday | 2 | 3.7% | 0h 20m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 1 | 1.9% | 16h 00m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 0 |
| 30–59m | 0 |
| 60–179m | 0 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 1 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1 |
| London | 0 |
| New York | 0 |
| Off-hours | 0 |

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
| 09 | 0 | 0 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 1 | 960 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2016-12-26 07:00:00 | 2016-12-26 23:00:00 | 960 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2016_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 54 |
| ❗ Anomalies | 1 |
| High events coverage (Economic Calendar) | 1/169 (0.6%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2016.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2016_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: f305b26998f6a4158692823d0311109100f4945a9aaab9034e1bdf2da8de020e Report generated with the help of ChatGPT (GPT-5 Thinking).
