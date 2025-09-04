# EURUSD 1m — Annual Report 2017

## Inputs used (hashes)
- DAT_ASCII CSV: d5d095207bcdbfc77b899e4ab69c2fd31cee09791a9ff4c74f9c066fb49a6ac4
- HistData TXT: 46885b89eb1a6e36edbf342c88c3d4c574851c5591ed2d960516f785786ffaf6
- Calendar CSV: cd62e7c81d8a14598e704a8d8d34cb24a46156b99776a3d84b7d3aa8324caf84
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 1b5c9422233bace47ed0c1ced600ec07cf3b9681bbf289163751d5f3e75b21a5

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2017.csv | `d5d095207bcdbfc77b899e4ab69c2fd31cee09791a9ff4c74f9c066fb49a6ac4` |
| DAT_ASCII_EURUSD_M1_2017.txt | `46885b89eb1a6e36edbf342c88c3d4c574851c5591ed2d960516f785786ffaf6` |
| calendar_2017.csv | `cd62e7c81d8a14598e704a8d8d34cb24a46156b99776a3d84b7d3aa8324caf84` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 100.0% | 2472h 00m |
| holiday | 0 | 0.0% | 0h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 0 | 0.0% | 0h 00m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 0 |
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
| 12 | 0 | 0 |

## 5) Extreme candles
_No anomalies found in 2017._

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2017_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 100 |
| Gaps total | 51 |
| ❗ Anomalies | 0 |
| High events coverage (Economic Calendar) | 0/167 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2017.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2017_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: b2163b00049301d5503c6b8fa1fd4956615a19f100ddc2b607e5647a87ec9ade Report generated with the help of ChatGPT (GPT-5 Thinking).
