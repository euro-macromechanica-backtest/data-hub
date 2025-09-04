# EURUSD 1m — Annual Report 2003

## Inputs used (hashes)
- DAT_ASCII CSV: e21fd776e58bd97513ee0ecfc7df1651445a8ac89a4ab058bed71506ab283f15
- HistData TXT: ae5b2a5a53d3ddfe44d16d7d1a8c343a1b5de4d79b12789ad6b6c2170f258908
- Calendar CSV: 4168cdeadda3c48a47a8a29901549b8589f965359d190c86b94ca7592c724b4b
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: dbaa2a596644b33ea519ac490a4732696df91a7f754cdee52166581f3d9fce5d

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2003.csv | `e21fd776e58bd97513ee0ecfc7df1651445a8ac89a4ab058bed71506ab283f15` |
| DAT_ASCII_EURUSD_M1_2003.txt | `ae5b2a5a53d3ddfe44d16d7d1a8c343a1b5de4d79b12789ad6b6c2170f258908` |
| calendar_2003.csv | `4168cdeadda3c48a47a8a29901549b8589f965359d190c86b94ca7592c724b4b` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 5.8% | 2632h 15m |
| holiday | 12 | 1.3% | 41h 05m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 825 | 92.8% | 210h 40m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 800 |
| 30–59m | 18 |
| 60–179m | 3 |
| 180–359m | 0 |
| 360–719m | 4 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 351 |
| London | 43 |
| New York | 39 |
| Off-hours | 392 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 111 | 1340 |
| 02 | 96 | 1550 |
| 03 | 79 | 1005 |
| 04 | 96 | 1165 |
| 05 | 110 | 1930 |
| 06 | 96 | 1140 |
| 07 | 69 | 935 |
| 08 | 30 | 465 |
| 09 | 26 | 875 |
| 10 | 30 | 405 |
| 11 | 31 | 1000 |
| 12 | 51 | 830 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2003-05-26 15:00:00 | 2003-05-27 00:00:00 | 540 |
| 2 | 2003-02-17 16:05:00 | 2003-02-18 00:05:00 | 480 |
| 3 | 2003-09-01 16:00:00 | 2003-09-02 00:00:00 | 480 |
| 4 | 2003-11-27 16:00:00 | 2003-11-28 00:00:00 | 480 |
| 5 | 2003-12-29 07:10:00 | 2003-12-29 09:35:00 | 145 |
| 6 | 2003-03-11 22:00:00 | 2003-03-11 23:15:00 | 75 |
| 7 | 2003-05-22 08:10:00 | 2003-05-22 09:25:00 | 75 |
| 8 | 2003-04-30 22:00:00 | 2003-04-30 22:50:00 | 50 |
| 9 | 2003-11-05 22:00:00 | 2003-11-05 22:50:00 | 50 |
| 10 | 2003-09-09 22:00:00 | 2003-09-09 22:45:00 | 45 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2003_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 90 |
| Gaps total | 889 |
| ❗ Anomalies | 825 |
| High events coverage (Economic Calendar) | 5/166 (3.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2003.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2003_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 225f0ef60181c3c21e7aa716304d8fd6af96c402d2423cd1326c8e5f60a84d31 Report generated with the help of ChatGPT (GPT-5 Thinking).
