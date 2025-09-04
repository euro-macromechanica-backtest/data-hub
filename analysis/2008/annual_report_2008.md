# EURUSD 1m — Annual Report 2008

## Inputs used (hashes)
- DAT_ASCII CSV: 74bf9d673c3065abe660ab141b08ba4b2d463a56108c97bf8cdaf62860091d24
- HistData TXT: 378351813087fa704e3f21b6c0620821ef6a464afac67409557b97d7144e560d
- Calendar CSV: 5da9581c107be9b08439a062d854fb3a8cd2682e0a91aedf65b507bacb1c893b
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 9c05cfe01c1c43e940fae9352f70ea508cbccb57af6854111adace41d6be6d64

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2008.csv | `74bf9d673c3065abe660ab141b08ba4b2d463a56108c97bf8cdaf62860091d24` |
| DAT_ASCII_EURUSD_M1_2008.txt | `378351813087fa704e3f21b6c0620821ef6a464afac67409557b97d7144e560d` |
| calendar_2008.csv | `5da9581c107be9b08439a062d854fb3a8cd2682e0a91aedf65b507bacb1c893b` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 21.7% | 2496h 25m |
| holiday | 8 | 3.3% | 39h 15m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 180 | 75.0% | 31h 35m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 180 |
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
| Asia | 78 |
| London | 1 |
| New York | 20 |
| Off-hours | 81 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 11 | 120 |
| 02 | 30 | 325 |
| 03 | 9 | 90 |
| 04 | 8 | 80 |
| 05 | 40 | 425 |
| 06 | 24 | 245 |
| 07 | 32 | 345 |
| 08 | 12 | 125 |
| 09 | 5 | 50 |
| 10 | 0 | 0 |
| 11 | 3 | 30 |
| 12 | 6 | 60 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2008-02-25 01:25:00 | 2008-02-25 01:45:00 | 20 |
| 2 | 2008-02-25 01:50:00 | 2008-02-25 02:10:00 | 20 |
| 3 | 2008-07-04 20:05:00 | 2008-07-04 20:25:00 | 20 |
| 4 | 2008-06-11 22:45:00 | 2008-06-11 23:00:00 | 15 |
| 5 | 2008-07-27 22:20:00 | 2008-07-27 22:35:00 | 15 |
| 6 | 2008-05-04 22:40:00 | 2008-05-04 22:55:00 | 15 |
| 7 | 2008-02-19 01:40:00 | 2008-02-19 01:55:00 | 15 |
| 8 | 2008-05-26 18:20:00 | 2008-05-26 18:35:00 | 15 |
| 9 | 2008-05-26 18:50:00 | 2008-05-26 19:05:00 | 15 |
| 10 | 2008-01-02 05:00:00 | 2008-01-02 05:15:00 | 15 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2008_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 98 |
| Gaps total | 240 |
| ❗ Anomalies | 180 |
| High events coverage (Economic Calendar) | 1/149 (0.7%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2008.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2008_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 9f99f7bb0734a1a7ec209714eb623e02c80ca6303967e84640efb2c329ca1724 Report generated with the help of ChatGPT (GPT-5 Thinking).
