# EURUSD 1m — Annual Report 2014

## Inputs used (hashes)
- DAT_ASCII CSV: 7f8a903a156c2e883ec5c389e555af6f340c634f414df69341c2b4fcfefdffab
- HistData TXT: 29abc42d4303249c1fbe7b2b05600d4c59461676c9692bff242e9223d9d0f546
- Calendar CSV: ac7302c25f73374ee21d62bec773470dd843472b02df783b61650547f8723aad
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 44ff174238c3025e72a296686af77fa0474f5f922bb73200790d150d7a2658bb

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2014.csv | `7f8a903a156c2e883ec5c389e555af6f340c634f414df69341c2b4fcfefdffab` |
| DAT_ASCII_EURUSD_M1_2014.txt | `29abc42d4303249c1fbe7b2b05600d4c59461676c9692bff242e9223d9d0f546` |
| calendar_2014.csv | `ac7302c25f73374ee21d62bec773470dd843472b02df783b61650547f8723aad` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 85.2% | 2518h 05m |
| holiday | 1 | 1.6% | 28h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 8 | 13.1% | 1h 25m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 8 |
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
| Asia | 4 |
| London | 1 |
| New York | 0 |
| Off-hours | 3 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 1 | 10 |
| 02 | 1 | 15 |
| 03 | 1 | 10 |
| 04 | 1 | 10 |
| 05 | 0 | 0 |
| 06 | 1 | 10 |
| 07 | 1 | 10 |
| 08 | 1 | 10 |
| 09 | 0 | 0 |
| 10 | 1 | 10 |
| 11 | 0 | 0 |
| 12 | 0 | 0 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2014-02-11 22:00:00 | 2014-02-11 22:15:00 | 15 |
| 2 | 2014-01-02 01:45:00 | 2014-01-02 01:55:00 | 10 |
| 3 | 2014-03-09 22:35:00 | 2014-03-09 22:45:00 | 10 |
| 4 | 2014-04-20 22:35:00 | 2014-04-20 22:45:00 | 10 |
| 5 | 2014-06-09 05:25:00 | 2014-06-09 05:35:00 | 10 |
| 6 | 2014-07-25 00:05:00 | 2014-07-25 00:15:00 | 10 |
| 7 | 2014-08-28 00:20:00 | 2014-08-28 00:30:00 | 10 |
| 8 | 2014-10-09 11:35:00 | 2014-10-09 11:45:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2014_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 61 |
| ❗ Anomalies | 8 |
| High events coverage (Economic Calendar) | 2/178 (1.1%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2014.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2014_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 14a9ccd181ddec75ec23361056eca045aa94ce518addb2f773370ab76ffad41b Report generated with the help of ChatGPT (GPT-5 Thinking).
