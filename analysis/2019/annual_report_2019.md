# EURUSD 1m — Annual Report 2019

## Inputs used (hashes)
- DAT_ASCII CSV: f9248bea5fd065c468859024f5e80f0a54c175fb65b7a919a9deeef20f15989d
- HistData TXT: f0046214f0916b85e526d67775ff4362486f32cd35b02a46bb05e3f389026d5d
- Calendar CSV: 5e87559246523b4142757224c7135f8a8dd4a8221e8f13d34132204286c06819
- Defaults SHA-256: e12aeb6eb062b7752c1b5b9f2d1cb9b4b63a70605dfd39f9c6e2d49ecdb5d1ea
- RUN_ID: aa70b464e873e923eb817a8d2dbe3d4aa8b3e23f6ab3a3750d81547d0808fd63

**Input files (names + SHA-256):**
| file | sha256 |
|---|---|
| DAT_ASCII_EURUSD_M1_2019.csv | `f9248bea5fd065c468859024f5e80f0a54c175fb65b7a919a9deeef20f15989d` |
| DAT_ASCII_EURUSD_M1_2019.txt | `f0046214f0916b85e526d67775ff4362486f32cd35b02a46bb05e3f389026d5d` |
| calendar_2019.csv | `5e87559246523b4142757224c7135f8a8dd4a8221e8f13d34132204286c06819` |

---
## 1) Gap classification (M5). Weekend window: Fri 22:00 → Sun 22:00 (UTC). FX holidays from policy; Economic Calendar (High; ±60s).
| reason | count | share | total duration |
|---|---:|---:|---:|
| weekend | 52 | 92.9% | 2502h 30m |
| holiday | 1 | 1.8% | 14h 00m |
| event | 0 | 0.0% | 0h 00m |
| anomaly | 3 | 5.4% | 8h 00m |

## 2) Durations (micro/medium/large)
| length bin | anomalies |
|---|---:|
| ≤5m | 0 |
| 6–29m | 0 |
| 30–59m | 0 |
| 60–179m | 2 |
| 180–359m | 0 |
| 360–719m | 1 |
| 720–1439m | 0 |
| 1440–2879m | 0 |
| ≥2880m | 0 |

## 3) Sessions (UTC)
| session (UTC) | anomalies |
|---|---:|
| Asia | 2 |
| London | 0 |
| New York | 0 |
| Off-hours | 1 |

## 4) Monthly statistics
| month | anomalies | minutes |
|---:|---:|---:|
| 01 | 0 | 0 |
| 02 | 0 | 0 |
| 03 | 0 | 0 |
| 04 | 1 | 60 |
| 05 | 1 | 360 |
| 06 | 0 | 0 |
| 07 | 0 | 0 |
| 08 | 0 | 0 |
| 09 | 0 | 0 |
| 10 | 0 | 0 |
| 11 | 0 | 0 |
| 12 | 1 | 60 |

## 5) Extreme candles
| # | gap_start (UTC) | gap_end (UTC) | length_min |
|---:|---|---|---:|
| 1 | 2019-05-27 05:00:00 | 2019-05-27 11:00:00 | 360 |
| 2 | 2019-04-01 00:00:00 | 2019-04-01 01:00:00 | 60 |
| 3 | 2019-12-24 22:00:00 | 2019-12-24 23:00:00 | 60 |

## 6) Cross-check with CME/EBS maintenance windows
_No extra maintenance closures defined in config._

## 7) Visualizations
- EURUSD_2019_anomalies_M5.svg.gz — anomalies map with axes & grid (X=time, Y=gap duration, red dots).

## Scorecard (0–100)
| metric | value |
|---|---:|
| Continuity Score | 99 |
| Gaps total | 56 |
| ❗ Anomalies | 3 |
| High events coverage (Economic Calendar) | 0/168 (0.0%) |


## 9) Full list of ❗ anomalies
Full table is provided in gaps_summary_2019.md.gz

## 10) SVG with ❗ anomalies
Provided as EURUSD_2019_anomalies_M5.svg.gz

---
Transparency footer
— Manifest SHA-256: 2c88e15d87ce693957de09ebc3a899d53327828c4f70b79298d4515299cf040b Report generated with the help of ChatGPT (GPT-5 Thinking).
