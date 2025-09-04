# EURUSD 1m — Annual Report 2022

## Inputs used (hashes)
- DAT_ASCII CSV: 6d807a638acf1caea389f3a708541b4abcac767472da54042cdcc2468a81d0b8
- HistData TXT: f52bed823c21dd768be969fd6a0368681f3a2db16e1b868a06375d00c2b31278
- Calendar CSV: a5fdbd372aa6a410e31d869d8be319e3a4d0c48cc5204b47132675e61c6483ef
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 3f19bd3ae1ebc91117f25bef4de3aacc5f9884a8d83d4c8a797d2d7425ce67a8

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2022.csv | `6d807a638acf1caea389f3a708541b4abcac767472da54042cdcc2468a81d0b8` |
| DAT_ASCII_EURUSD_M1_2022.txt | `f52bed823c21dd768be969fd6a0368681f3a2db16e1b868a06375d00c2b31278` |
| calendar_2022.csv | `a5fdbd372aa6a410e31d869d8be319e3a4d0c48cc5204b47132675e61c6483ef` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 51 | 86.4% | 2449h 20m |
| holiday | 1 | 1.7% | 0h 10m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 7 | 11.9% | 2h 05m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 6 |
| 30–59m | 0 |
| 60–179m | 1 |
| 180–359m | 0 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 1 |
| London | 0 |
| New York | 0 |
| Off-hours | 6 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 1 | 10 |
| 02 | 0 | 0 |
| 03 | 1 | 60 |
| 04 | 0 | 0 |
| 05 | 0 | 0 |
| 06 | 0 | 0 |
| 07 | 1 | 10 |
| 08 | 0 | 0 |
| 09 | 0 | 0 |
| 10 | 2 | 25 |
| 11 | 0 | 0 |
| 12 | 2 | 20 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2022-03-28 00:00:00 | 2022-03-28 01:00:00 | 60 |
| 2 | 2022-10-09 22:00:00 | 2022-10-09 22:15:00 | 15 |
| 3 | 2022-01-03 21:20:00 | 2022-01-03 21:30:00 | 10 |
| 4 | 2022-07-24 22:45:00 | 2022-07-24 22:55:00 | 10 |
| 5 | 2022-10-27 22:25:00 | 2022-10-27 22:35:00 | 10 |
| 6 | 2022-12-26 22:15:00 | 2022-12-26 22:25:00 | 10 |
| 7 | 2022-12-29 22:00:00 | 2022-12-29 22:10:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2022_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 59 |
| ❗ Anomalies | 7 |
| High events coverage (Economic Calendar) | 0/167 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2022.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2022_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 1893e8cd64df4d7423cf895e53eea603bb9eb6835b599efae116d764716cc96e Report generated with the help of ChatGPT (GPT-5 Thinking).
