# EURUSD 1m — Annual Report 2007

## Inputs used (hashes)
- DAT_ASCII CSV: e9f9e89341b60bd8d3e609810650fbfeaa8b3e971bc01aca09e7eb21b4dc72e0
- HistData TXT: d74f3053dcb1ade7aa7ac669b2017957bfd639792f10423239c9467b008c1737
- Calendar CSV: 5409758725d6a8fa572b652201ef647d3f66fc4df54c1f9c18fc54ef0c681b15
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 61210954638150edab1c9306cecfe75dc72e89a208465da00db970d1d6013bac

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2007.csv | `e9f9e89341b60bd8d3e609810650fbfeaa8b3e971bc01aca09e7eb21b4dc72e0` |
| DAT_ASCII_EURUSD_M1_2007.txt | `d74f3053dcb1ade7aa7ac669b2017957bfd639792f10423239c9467b008c1737` |
| calendar_2007.csv | `5409758725d6a8fa572b652201ef647d3f66fc4df54c1f9c18fc54ef0c681b15` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 5.5% | 2500h 30m |
| holiday | 19 | 2.0% | 36h 40m |
| event | 1 | 0.1% | 0h 10m |
| anomaly | 880 | 92.4% | 168h 10m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 871 |
| 30–59m | 7 |
| 60–179m | 1 |
| 180–359m | 1 |
| 360–719m | 0 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 483 |
| London | 42 |
| New York | 149 |
| Off-hours | 206 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 59 | 630 |
| 02 | 84 | 870 |
| 03 | 40 | 445 |
| 04 | 90 | 1015 |
| 05 | 157 | 1945 |
| 06 | 126 | 1430 |
| 07 | 102 | 1140 |
| 08 | 34 | 550 |
| 09 | 54 | 585 |
| 10 | 46 | 495 |
| 11 | 26 | 295 |
| 12 | 62 | 690 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2007-08-08 10:40:00 | 2007-08-08 14:05:00 | 205 |
| 2 | 2007-05-28 18:10:00 | 2007-05-28 19:15:00 | 65 |
| 3 | 2007-05-28 20:15:00 | 2007-05-28 21:10:00 | 55 |
| 4 | 2007-05-28 21:20:00 | 2007-05-28 22:00:00 | 40 |
| 5 | 2007-06-22 05:30:00 | 2007-06-22 06:05:00 | 35 |
| 6 | 2007-05-07 01:10:00 | 2007-05-07 01:45:00 | 35 |
| 7 | 2007-05-27 22:05:00 | 2007-05-27 22:40:00 | 35 |
| 8 | 2007-11-06 02:25:00 | 2007-11-06 02:55:00 | 30 |
| 9 | 2007-05-28 04:55:00 | 2007-05-28 05:25:00 | 30 |
| 10 | 2007-04-17 22:00:00 | 2007-04-17 22:25:00 | 25 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2007_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 92 |
| Gaps total | 952 |
| ❗ Anomalies | 880 |
| High events coverage (Economic Calendar) | 2/146 (1.4%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2007.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2007_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 12d901a8e149d8e6fc8c1084483d5ccaf56cf6db1e73a459115512dbe2161b26 Report generated with the help of ChatGPT (GPT-5 Thinking).
