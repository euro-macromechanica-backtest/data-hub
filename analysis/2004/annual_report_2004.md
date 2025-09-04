# EURUSD 1m — Annual Report 2004

## Inputs used (hashes)
- DAT_ASCII CSV: 834cbb13467921dc3fe5956fe4ee34b12818f8e748bec450767b5d070117b1cb
- HistData TXT: 0ce896ca897c42af91cc7f996fca308555eebd7b24452b768d404bc31629c640
- Calendar CSV: 1b70ee191f397522d1b879c17ed8c85eced8a894f278803442ece7f6b922d2bc
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 92db9c3c39c005a3a751572373991a4271e6b3f5a708c4ade7f219e158bf2b90

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2004.csv | `834cbb13467921dc3fe5956fe4ee34b12818f8e748bec450767b5d070117b1cb` |
| DAT_ASCII_EURUSD_M1_2004.txt | `0ce896ca897c42af91cc7f996fca308555eebd7b24452b768d404bc31629c640` |
| calendar_2004.csv | `1b70ee191f397522d1b879c17ed8c85eced8a894f278803442ece7f6b922d2bc` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 161 | 21.7% | 2548h 15m |
| holiday | 14 | 1.9% | 2h 25m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 567 | 76.4% | 182h 40m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 515 |
| 30–59m | 45 |
| 60–179m | 3 |
| 180–359m | 0 |
| 360–719m | 3 |
| 720–1439m | 1 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 210 |
| London | 18 |
| New York | 44 |
| Off-hours | 295 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 20 | 355 |
| 02 | 29 | 475 |
| 03 | 27 | 545 |
| 04 | 36 | 595 |
| 05 | 35 | 1020 |
| 06 | 31 | 550 |
| 07 | 49 | 905 |
| 08 | 68 | 1785 |
| 09 | 86 | 1635 |
| 10 | 81 | 1070 |
| 11 | 47 | 1145 |
| 12 | 58 | 880 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2004-08-23 22:00:00 | 2004-08-24 12:00:00 | 840 |
| 2 | 2004-05-31 16:00:00 | 2004-06-01 00:00:00 | 480 |
| 3 | 2004-09-06 16:00:00 | 2004-09-07 00:00:00 | 480 |
| 4 | 2004-11-25 16:00:00 | 2004-11-25 22:15:00 | 375 |
| 5 | 2004-11-25 22:15:00 | 2004-11-26 00:00:00 | 105 |
| 6 | 2004-12-06 16:45:00 | 2004-12-06 18:10:00 | 85 |
| 7 | 2004-12-26 22:15:00 | 2004-12-26 23:30:00 | 75 |
| 8 | 2004-07-05 05:45:00 | 2004-07-05 06:40:00 | 55 |
| 9 | 2004-02-19 22:00:00 | 2004-02-19 22:50:00 | 50 |
| 10 | 2004-07-01 22:00:00 | 2004-07-01 22:50:00 | 50 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2004_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 91 |
| Gaps total | 742 |
| ❗ Anomalies | 567 |
| High events coverage (Economic Calendar) | 0/167 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2004.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2004_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: e4a796660463ced9f1e47ada565177b9322df9a6262df95ebac5cbc791eed37d Report generated with the help of ChatGPT (GPT-5 Thinking).
