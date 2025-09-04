# EURUSD 1m DATA ANALYSIS — Process & Conventions

---

## 🌍 Overview
This project standardizes minute-level EURUSD data and produces quarterly CSVs plus a yearly (or partial-year) analysis with a single anomalies SVG and a summary of anomalies. The pipeline is deterministic where required and fully UTC-based.  

---

## 📥 Inputs
- Minute source (HistData DAT_ASCII), timezone EST (UTC−5) without DST:  
  - Yearly: `DAT_ASCII_EURUSD_M1_YYYY.csv` and/or `.txt`  
  - Monthly (e.g., 2025 partial runs): `DAT_ASCII_EURUSD_M1_YYYYMM.csv` and/or `.txt`  
- Economic calendar (UTC): `calendar_YYYY.csv`  
  - Required columns: `datetime_utc` (+ event, impact/importance).  

---

## 🕒 Timezone & Parsing
- Source timestamps are EST (UTC−5) with no DST. On read, convert EST → UTC (+5h).  
- DAT_ASCII delimiter auto-detected (`;` preferred).  
- Parse OHLC and volume as numeric.  

---

## 🔹 Step 1 — Standardization (Quarterly CSV.GZ)
- Output per quarter: `EURUSD_M1_YYYY_Q{1..4}.csv.gz`  
- Header:  
  ```
  datetime;open;high;low;close;volume
  ```
- UTC datetimes, sorted ascending; duplicates dropped.  
- Deterministic gzip: `mtime=0`.  
- Partial-year (e.g., 2025 Jan–Jul): additionally emit July as `EURUSD_M1_YYYY_07.csv.gz`.  

---

## 🔹 Step 2 — Yearly (or Partial-Year) Analysis

### Gap detection (M5)
- Resample M1 → M5 (right-closed, right-labeled).  
- Gap = interval > 5 minutes between consecutive M5 bars.  

### Classification
By interval intersection, not start time:  
1. Weekend: Fri 22:00 → Sun 22:00 UTC  
2. Holidays: from `fx_holidays.py`  
3. Events: High-impact, ±60s, not overriding weekend/holiday  
4. Else: anomaly  

---

## 📊 Coverage (Calendar)
Coverage = High-impact events matched (±60s) / all High-impact events in the year (or coverage period).  

---

## 🏆 Score
- Weekend/holiday do not penalize.  
- If anomalies = 0 ⇒ Score = 100.  

---

## 📦 Outputs
- Report (Markdown): `annual_report_YYYY.md`  
- Summary (only anomalies): `gaps_summary_YYYY.md.gz`  
- Visualization: `EURUSD_YYYY_anomalies_M5.svg.gz` (axes, grid, red dots)  
- Manifest: `artifacts_YYYY.sha256`  

---

## 🔒 Determinism & Packaging
Only gzip artifacts with `mtime=0`: quarterlies, gaps_summary, anomalies SVG. No TARs.  

---

## 📑 Manifest & Hashing
- `artifacts_YYYY.sha256` includes all inputs + outputs.  
- Report prints MANIFEST-SHA as external marker (not included in its own hash).  

---

## 🏷️ Naming Conventions
- **Inputs:**  
  - Yearly: `DAT_ASCII_EURUSD_M1_YYYY.(csv|txt)`  
  - Monthly: `DAT_ASCII_EURUSD_M1_YYYYMM.(csv|txt)`  
  - Calendar: `calendar_YYYY.csv`  

- **Outputs:**  
  - Step 1: `EURUSD_M1_YYYY_Q1.csv.gz … EURUSD_M1_YYYY_Q4.csv.gz` (+ `EURUSD_M1_YYYY_07.csv.gz` if partial)  
  - Step 2: `annual_report_YYYY.md`, `gaps_summary_YYYY.md.gz`, `EURUSD_YYYY_anomalies_M5.svg.gz`, `artifacts_YYYY.sha256`  

---

## ✅ Quality Checks
1. Quarterlies: gzip mtime=0; correct header; delimiter `;`; UTC; sorted; no duplicates.  
2. Calendar: only High-impact; ±60s; UTC; event doesn’t override weekend/holiday.  
3. Classification: by interval intersection.  
4. SVG: axes + grid; X=time; Y=minutes; red points.  
5. Report: fully filled; Sec.9 link correct; Sec.10 text correct.  
6. Determinism: only specified gzip deterministic.  
7. Manifest: includes all inputs+outputs; SHA external in report.  

---

## 📆 Partial-Year Runs
- Step 1: produce `Q1`, `Q2`, and `YYYY_07.csv.gz`.  
- Step 2: analyze Jan 1 → Jul 31. Same filenames; report states coverage period.  

---

---

# EURUSD 1m DATA ANALYSIS — Процесс и правила

---

## 🌍 Общее
Пайплайн нормализует минутные данные EURUSD и выпускает квартальные CSV, а также годовой (или частичный) анализ с одной SVG-визуализацией аномалий и сводной таблицей. Вся обработка ведётся в UTC.  

---

## 📥 Входные данные
- Минутки (HistData DAT_ASCII), часовой пояс источника — EST (UTC−5) без DST:  
  - Годовые: `DAT_ASCII_EURUSD_M1_YYYY.csv` и/или `.txt`  
  - Помесячно (для частичных запусков): `DAT_ASCII_EURUSD_M1_YYYYMM.csv` и/или `.txt`  
- Экономкалендарь (UTC): `calendar_YYYY.csv`  
  - Обязательные столбцы: `datetime_utc` (+ event, impact/importance).  

---

## 🕒 Таймзона и парсинг
- Источник всегда в EST (UTC−5) без перевода часов. При чтении выполняем конверсию EST → UTC (+5ч).  
- Разделитель в DAT_ASCII определяется автоматически (предпочтительно `;`).  
- Поля OHLC и volume парсим как числа.  

---

## 🔹 Шаг 1 — Нормализация (квартальные CSV.GZ)
- На выходе по кварталам: `EURUSD_M1_YYYY_Q{1..4}.csv.gz`  
- Заголовок:  
  ```
  datetime;open;high;low;close;volume
  ```
- UTC, сортировка по возрастанию; дубликаты удаляются.  
- Gzip-детерминизм: `mtime=0`.  
- Частичный год (например 2025 Jan–Jul): дополнительно выпускать `EURUSD_M1_YYYY_07.csv.gz`.  

---

## 🔹 Шаг 2 — Годовой / частичный анализ

### Детектирование гэпов (M5)
- Ресемплируем M1 в M5 (right-closed, right-labeled).  
- Гэп = интервал > 5 мин.  

### Классификация
По пересечению интервалов, не по времени старта:  
1. Weekend: пт 22:00 → вс 22:00 UTC  
2. Праздники: из `fx_holidays.py`  
3. События: High-impact, окно ±60с, не заменяют weekend/holiday  
4. Остальное: anomaly  

---

## 📊 Покрытие (календарь)
Coverage = доля High-событий, попавших в гэпы (±60с), к общему числу High-событий.  

---

## 🏆 Оценка
- Weekend/holiday не штрафуют.  
- Если аномалий=0 ⇒ Score=100.  

---

## 📦 Выходные артефакты
- Отчёт (Markdown): `annual_report_YYYY.md`  
- Сводка (только аномалии): `gaps_summary_YYYY.md.gz`  
- Визуализация: `EURUSD_YYYY_anomalies_M5.svg.gz` (оси, сетка, красные точки)  
- Манифест: `artifacts_YYYY.sha256`  

---

## 🔒 Детерминизм и упаковка
Только указанные gzip с `mtime=0`: кварталы, gaps_summary, anomalies SVG. TAR не создаём.  

---

## 📑 Манифест и хэши
- `artifacts_YYYY.sha256` содержит все входы и выходы.  
- В отчёте печатаем MANIFEST-SHA как внешнюю метку (не учитывается в собственном хэше отчёта).  

---

## 🏷️ Именование
- **Входы:**  
  - Год: `DAT_ASCII_EURUSD_M1_YYYY.(csv|txt)`  
  - Месяц: `DAT_ASCII_EURUSD_M1_YYYYMM.(csv|txt)`  
  - Календарь: `calendar_YYYY.csv`  

- **Выходы:**  
  - Шаг 1: `EURUSD_M1_YYYY_Q1.csv.gz … EURUSD_M1_YYYY_Q4.csv.gz` (+ `EURUSD_M1_YYYY_07.csv.gz` если частичный)  
  - Шаг 2: `annual_report_YYYY.md`, `gaps_summary_YYYY.md.gz`, `EURUSD_YYYY_anomalies_M5.svg.gz`, `artifacts_YYYY.sha256`  

---

## ✅ Контроль качества
1. Квартальные: gzip mtime=0; точный заголовок; `;`-разделитель; UTC; сортировка; без дубликатов.  
2. Календарь: только High-impact; ±60с; UTC; событие не заменяет weekend/holiday.  
3. Классификация: по пересечению интервалов.  
4. SVG: оси и сетка; X=время; Y=минуты; точки красные.  
5. Отчёт: шаблон полностью; п.9 ссылка корректна; п.10 текст корректен.  
6. Детерминизм: только указанные gzip детерминированные.  
7. Манифест: включает все входы/выходы; SHA внешняя в отчёте.  

---

## 📆 Частичный год
- Шаг 1: выпускать `Q1`, `Q2` и `YYYY_07.csv.gz`.  
- Шаг 2: анализировать 01 Jan → 31 Jul. Файлы стандартные; период явно указан в отчёте.  
