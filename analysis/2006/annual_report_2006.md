# EURUSD 1m — Annual Report 2006

## Inputs used (hashes)
- DAT_ASCII CSV: 50d7e918bcf6b3117b0b9862400ad64ef4c90f40da7784d16566e68cc2ee778a
- HistData TXT: 433b6cce3972e73b5278dc0f66617430c78f74a0c3fc86bf4f3add2c2ba0d0dc
- Calendar CSV: 1370c52c8da8063e93c37f6f62f02166b2609c1afa99480e33ad80fea7b90fe2
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 27030e02efc922f5efec4755a7deafc1192eacc49134afe86533cba7d76210e4

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2006.csv | `50d7e918bcf6b3117b0b9862400ad64ef4c90f40da7784d16566e68cc2ee778a` |
| DAT_ASCII_EURUSD_M1_2006.txt | `433b6cce3972e73b5278dc0f66617430c78f74a0c3fc86bf4f3add2c2ba0d0dc` |
| calendar_2006.csv | `1370c52c8da8063e93c37f6f62f02166b2609c1afa99480e33ad80fea7b90fe2` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 6.5% | 2500h 15m |
| holiday | 17 | 2.2% | 3h 15m |
| event | 2 | 0.3% | 0h 20m |
| anomaly | 714 | 91.1% | 130h 50m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 712 |
| 30–59m | 2 |
| 60–179m | 0 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 364 |
| London | 27 |
| New York | 80 |
| Off-hours | 243 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 37 | 470 |
| 02 | 67 | 810 |
| 03 | 38 | 425 |
| 04 | 52 | 580 |
| 05 | 33 | 345 |
| 06 | 31 | 320 |
| 07 | 50 | 515 |
| 08 | 66 | 695 |
| 09 | 84 | 920 |
| 10 | 116 | 1275 |
| 11 | 90 | 965 |
| 12 | 50 | 530 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2006-02-20 20:05:00 | 2006-02-20 20:45:00 | 40 |
| 2 | 2006-10-16 05:40:00 | 2006-10-16 06:15:00 | 35 |
| 3 | 2006-10-09 23:50:00 | 2006-10-10 00:15:00 | 25 |
| 4 | 2006-12-26 10:45:00 | 2006-12-26 11:05:00 | 20 |
| 5 | 2006-09-20 03:35:00 | 2006-09-20 03:55:00 | 20 |
| 6 | 2006-08-20 22:15:00 | 2006-08-20 22:35:00 | 20 |
| 7 | 2006-10-15 23:40:00 | 2006-10-16 00:00:00 | 20 |
| 8 | 2006-07-06 04:50:00 | 2006-07-06 05:10:00 | 20 |
| 9 | 2006-11-01 03:45:00 | 2006-11-01 04:05:00 | 20 |
| 10 | 2006-02-28 22:00:00 | 2006-02-28 22:20:00 | 20 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2006_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 94 |
| Gaps total | 784 |
| ❗ Anomalies | 714 |
| High events coverage (Economic Calendar) | 3/167 (1.8%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2006.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2006_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: a07e4ac6aadac60b08b2299b576f416f79185d6b2350c29c62c5608995d01b3e Report generated with the help of ChatGPT (GPT-5 Thinking).
