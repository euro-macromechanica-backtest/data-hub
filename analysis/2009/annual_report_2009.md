# EURUSD 1m — Annual Report 2009

## Inputs used (hashes)
- DAT_ASCII CSV: 356095ae8e541c84288d2db525496177ad26833e5b3aa8bbf7cdfe52254101fc
- HistData TXT: 0a6ae4c9632d80b29cb762b84d5bc21ed60ebada2c94a3757026bcf2efa9805b
- Calendar CSV: 106a5ce6a585511dca74341fbd8c36cc318a8bd8c634b998cc1207c7d4e79d27
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: c5473e1b666e250689871b5459bec9f867b3afc5c54c0ff7b6505fa168d99890

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2009.csv | `356095ae8e541c84288d2db525496177ad26833e5b3aa8bbf7cdfe52254101fc` |
| DAT_ASCII_EURUSD_M1_2009.txt | `0a6ae4c9632d80b29cb762b84d5bc21ed60ebada2c94a3757026bcf2efa9805b` |
| calendar_2009.csv | `106a5ce6a585511dca74341fbd8c36cc318a8bd8c634b998cc1207c7d4e79d27` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 42.3% | 2516h 55m |
| holiday | 4 | 3.3% | 0h 40m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 67 | 54.5% | 12h 45m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 66 |
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
| Asia | 8 |
| London | 0 |
| New York | 10 |
| Off-hours | 49 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 1 | 10 |
| 02 | 2 | 20 |
| 03 | 0 | 0 |
| 04 | 5 | 50 |
| 05 | 5 | 65 |
| 06 | 7 | 85 |
| 07 | 6 | 70 |
| 08 | 6 | 80 |
| 09 | 8 | 80 |
| 10 | 6 | 60 |
| 11 | 3 | 30 |
| 12 | 18 | 215 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2009-12-24 22:05:00 | 2009-12-24 22:40:00 | 35 |
| 2 | 2009-08-23 22:35:00 | 2009-08-23 23:00:00 | 25 |
| 3 | 2009-06-04 23:10:00 | 2009-06-04 23:35:00 | 25 |
| 4 | 2009-12-24 20:30:00 | 2009-12-24 20:50:00 | 20 |
| 5 | 2009-05-03 22:15:00 | 2009-05-03 22:35:00 | 20 |
| 6 | 2009-05-25 20:25:00 | 2009-05-25 20:40:00 | 15 |
| 7 | 2009-07-12 22:45:00 | 2009-07-12 23:00:00 | 15 |
| 8 | 2009-07-19 22:05:00 | 2009-07-19 22:20:00 | 15 |
| 9 | 2009-08-09 22:35:00 | 2009-08-09 22:50:00 | 15 |
| 10 | 2009-11-23 22:45:00 | 2009-11-23 22:55:00 | 10 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2009_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 123 |
| ❗ Anomalies | 67 |
| High events coverage (Economic Calendar) | 1/171 (0.6%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2009.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2009_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: ef13cf99c7662053a171afc21ade25a94c07924899e1b9e92ca53a869ec1c5b0 Report generated with the help of ChatGPT (GPT-5 Thinking).
