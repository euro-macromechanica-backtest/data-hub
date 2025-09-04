# EURUSD 1m — Annual Report 2001

## Inputs used (hashes)
- DAT_ASCII CSV: d21fd56cc2f1df019abf8e6fe46cf52e5bfe8e0caa554b3110cf94564ac7905a
- HistData TXT: 90cac3d55ec822ebcb54611c59603e74c0d67c768c8ae7dcde7cc6d755a96961
- Calendar CSV: 8619d06ccd532bb4ea831bc6619b21bdf7a9fa6dd80cad9fc1a3bafedf4597df
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: f97fbc5d127ba2f399bdb5384997b478767f0db5bae29da11df51aa593f74a18

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2001.csv | `d21fd56cc2f1df019abf8e6fe46cf52e5bfe8e0caa554b3110cf94564ac7905a` |
| DAT_ASCII_EURUSD_M1_2001.txt | `90cac3d55ec822ebcb54611c59603e74c0d67c768c8ae7dcde7cc6d755a96961` |
| calendar_2001.csv | `8619d06ccd532bb4ea831bc6619b21bdf7a9fa6dd80cad9fc1a3bafedf4597df` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 2.8% | 3368h 20m |
| holiday | 69 | 3.7% | 62h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 1734 | 93.5% | 406h 10m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 1694 |
| 30–59m | 23 |
| 60–179m | 9 |
| 180–359m | 3 |
| 360–719m | 5 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1128 |
| London | 61 |
| New York | 127 |
| Off-hours | 418 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 32 | 360 |
| 02 | 81 | 1315 |
| 03 | 86 | 1095 |
| 04 | 87 | 1200 |
| 05 | 196 | 2985 |
| 06 | 160 | 1940 |
| 07 | 225 | 3600 |
| 08 | 221 | 2735 |
| 09 | 136 | 2415 |
| 10 | 244 | 2860 |
| 11 | 165 | 2590 |
| 12 | 101 | 1275 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2001-07-04 14:00:00 | 2001-07-05 00:05:00 | 605 |
| 2 | 2001-09-03 14:00:00 | 2001-09-04 00:00:00 | 600 |
| 3 | 2001-05-28 14:00:00 | 2001-05-29 00:00:00 | 600 |
| 4 | 2001-02-19 16:30:00 | 2001-02-20 00:00:00 | 450 |
| 5 | 2001-07-03 18:00:00 | 2001-07-04 00:05:00 | 365 |
| 6 | 2001-11-21 18:30:00 | 2001-11-22 00:05:00 | 335 |
| 7 | 2001-11-12 18:30:00 | 2001-11-13 00:00:00 | 330 |
| 8 | 2001-09-17 01:40:00 | 2001-09-17 04:55:00 | 195 |
| 9 | 2001-06-18 00:55:00 | 2001-06-18 03:50:00 | 175 |
| 10 | 2001-10-09 17:20:00 | 2001-10-09 18:45:00 | 85 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2001_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 81 |
| Gaps total | 1854 |
| ❗ Anomalies | 1734 |
| High events coverage (Economic Calendar) | 28/168 (16.7%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2001.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2001_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 64f9dac008f497dca759b927da0eeff7cc9cc938e0423704c1509774e6d99014 Report generated with the help of ChatGPT (GPT-5 Thinking).
