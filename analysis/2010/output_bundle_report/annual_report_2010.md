# EURUSD 1m — Annual Report 2010

## Inputs used (hashes)
- DAT_ASCII CSV: 527f761a54bef058b2e8876aad62968627c71a4a78736b72e78ea093fa835e1c
- HistData TXT: d6437659804330fa3ef111dfedce4b882d6d6bef425ca219d17920e234c3b81c
- Calendar CSV: f6a4502692f34bae0c62ba76d4d72827de34943d270b65d5546bc942ffc6b0ba
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 090ff6b48d85719135af3ca59531a0c407484ea267372e232bfa11c54e48afaa

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2010.csv | `527f761a54bef058b2e8876aad62968627c71a4a78736b72e78ea093fa835e1c` |
| DAT_ASCII_EURUSD_M1_2010.txt | `d6437659804330fa3ef111dfedce4b882d6d6bef425ca219d17920e234c3b81c` |
| calendar_2010.csv | `f6a4502692f34bae0c62ba76d4d72827de34943d270b65d5546bc942ffc6b0ba` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 29.8% | 2450h 10m |
| holiday | 4 | 2.3% | 0h 45m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 116 | 67.8% | 20h 05m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 116 |
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
| Asia | 20 |
| London | 1 |
| New York | 15 |
| Off-hours | 80 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 7 | 70 |
| 02 | 4 | 40 |
| 03 | 10 | 105 |
| 04 | 11 | 110 |
| 05 | 3 | 30 |
| 06 | 6 | 60 |
| 07 | 12 | 120 |
| 08 | 21 | 225 |
| 09 | 19 | 200 |
| 10 | 9 | 95 |
| 11 | 6 | 65 |
| 12 | 8 | 85 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2010-08-03 22:50:00 | 2010-08-03 23:05:00 | 15 |
| 2 | 2010-10-13 22:15:00 | 2010-10-13 22:30:00 | 15 |
| 3 | 2010-03-17 00:25:00 | 2010-03-17 00:40:00 | 15 |
| 4 | 2010-11-04 23:35:00 | 2010-11-04 23:50:00 | 15 |
| 5 | 2010-08-18 22:45:00 | 2010-08-18 23:00:00 | 15 |
| 6 | 2010-09-06 20:35:00 | 2010-09-06 20:50:00 | 15 |
| 7 | 2010-09-29 22:30:00 | 2010-09-29 22:45:00 | 15 |
| 8 | 2010-12-24 17:10:00 | 2010-12-24 17:25:00 | 15 |
| 9 | 2010-08-03 22:35:00 | 2010-08-03 22:50:00 | 15 |
| 10 | 2010-09-06 22:20:00 | 2010-09-06 22:30:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2010_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 171 |
| ❗ Anomalies | 116 |
| High events coverage (Economic Calendar) | 1/175 (0.6%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2010.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2010_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 4399e774b89d0a2e7063484e9d2316f4657fe44e428e0fad7c76e4cd9dba5f0a Report generated with the help of ChatGPT (GPT-5 Thinking).
