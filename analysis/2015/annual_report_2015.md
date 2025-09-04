# EURUSD 1m — Annual Report 2015

## Inputs used (hashes)
- DAT_ASCII CSV: 6f3d88318899cf49797017466b88eb033ed0bd1e5d3c380eb197d669e6feab00
- HistData TXT: d3b2e8eb11007274f10e39f81e8991335d1d66cc9bc7281f171a5f5bd1f3e705
- Calendar CSV: 01bc34e90703db2ffd47fca8b2755dba65beee9081d37bc141dc8e04c79b842b
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 6c7fb5cec5f7d37678c2f609af583c58cc36b0a8d98b56d32fa64663a5a3113f

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2015.csv | `6f3d88318899cf49797017466b88eb033ed0bd1e5d3c380eb197d669e6feab00` |
| DAT_ASCII_EURUSD_M1_2015.txt | `d3b2e8eb11007274f10e39f81e8991335d1d66cc9bc7281f171a5f5bd1f3e705` |
| calendar_2015.csv | `01bc34e90703db2ffd47fca8b2755dba65beee9081d37bc141dc8e04c79b842b` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 94.5% | 2523h 10m |
| holiday | 2 | 3.6% | 3h 05m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 1 | 1.8% | 0h 40m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 0 |
| 30–59m | 1 |
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
| New York | 1 |
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
| 08 | 1 | 40 |
| 09 | 0 | 0 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 0 | 0 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2015-08-21 18:20:00 | 2015-08-21 19:00:00 | 40 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2015_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 55 |
| ❗ Anomalies | 1 |
| High events coverage (Economic Calendar) | 1/167 (0.6%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2015.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2015_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 289b58aad5fffb4d098ed1decc34a319a5cc5a1e62721d36c5f7ef5ad67493d9 Report generated with the help of ChatGPT (GPT-5 Thinking).
