# EURUSD 1m — Annual Report 2005

## Inputs used (hashes)
- DAT_ASCII CSV: f71eba6a3597c86371d44c75137297efbcfcd48ac65f6eee1810d28a4f3abf41
- HistData TXT: 282661f30ba6aa230978e54311276a35c36ffe9c4d4ee6302f3edc8caa8cbf32
- Calendar CSV: 257f60ba3b393980915b3881d8f928567f01dadd98f488fbd48e4417c252b1f5
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: 

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2005.csv | `f71eba6a3597c86371d44c75137297efbcfcd48ac65f6eee1810d28a4f3abf41` |
| DAT_ASCII_EURUSD_M1_2005.txt | `282661f30ba6aa230978e54311276a35c36ffe9c4d4ee6302f3edc8caa8cbf32` |
| calendar_2005.csv | `257f60ba3b393980915b3881d8f928567f01dadd98f488fbd48e4417c252b1f5` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 352 | 37.4% | 2518h 45m |
| holiday | 15 | 1.6% | 3h 05m |
| event | 1 | 0.1% | 2h 55m |
| anomaly | 572 | 60.9% | 159h 20m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 554 |
| 30–59m | 14 |
| 60–179m | 0 |
| 180–359m | 0 |
| 360–719m | 4 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 233 |
| London | 21 |
| New York | 34 |
| Off-hours | 284 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 21 | 245 |
| 02 | 47 | 590 |
| 03 | 45 | 685 |
| 04 | 49 | 705 |
| 05 | 92 | 1635 |
| 06 | 49 | 660 |
| 07 | 50 | 1255 |
| 08 | 43 | 590 |
| 09 | 40 | 1005 |
| 10 | 39 | 505 |
| 11 | 45 | 1040 |
| 12 | 52 | 645 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2005-11-24 16:00:00 | 2005-11-25 00:00:00 | 480 |
| 2 | 2005-05-30 16:00:00 | 2005-05-31 00:00:00 | 480 |
| 3 | 2005-09-05 16:00:00 | 2005-09-06 00:00:00 | 480 |
| 4 | 2005-07-04 16:05:00 | 2005-07-05 00:00:00 | 475 |
| 5 | 2005-01-14 04:35:00 | 2005-01-14 05:20:00 | 45 |
| 6 | 2005-07-26 22:00:00 | 2005-07-26 22:40:00 | 40 |
| 7 | 2005-07-28 00:25:00 | 2005-07-28 01:05:00 | 40 |
| 8 | 2005-07-28 09:30:00 | 2005-07-28 10:10:00 | 40 |
| 9 | 2005-02-07 23:30:00 | 2005-02-08 00:05:00 | 35 |
| 10 | 2005-05-26 22:00:00 | 2005-05-26 22:35:00 | 35 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2005_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 92 |
| Gaps total | 940 |
| ❗ Anomalies | 572 |
| High events coverage (Economic Calendar) | 3/169 (1.8%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2005.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2005_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 8dfbb2c1daeef8be8c4804e3ed8cf4eff4e34384915c877eacf38a3553e002e6 Report generated with the help of ChatGPT (GPT-5 Thinking).
