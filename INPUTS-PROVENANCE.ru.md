# 🔗 Inputs — Provenance & Binding — Привязка входных данных к результатам Euro Macromechanica (EMM) Backtest

Этот документ фиксирует **как именно** входные данные из репозитория **data-hub** – (raw/ prepared/ calendars)
сопоставляются с использованием в публичных результатах бэктеста **results**. Здесь описана **логика связки** и **таблицы для якорей OTS** (SHA‑256, txid, блок, UTC‑время).  
Подробные команды проверки хэшей см. в [results/docs/`INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md) – для raw Histdata данных, prepared, экономических календарей. `analysis/ANALYSIS-INTEGRITY.ru.md` (нюанс с нормализацией отчёта) – для сверки манифеста анализа c отчетами, svg и входными данными (raw Histdata данных, экономических календарей).

---

## 🎯 Назначение
- Обозначить, **какие именно входы** (сырые минутные данные, подготовленные минутные данные, календари) использовались.
- Показать, **где лежат хэши/подписи/OTS**, подтверждающие **момент времени** и **целостность** входов.
- Дать **простую карту соответствий** между **data-hub** – и **results**.

## 📦 Охват (что считается «входами»)
- **RAW минутные данные** (*HistData*): `source_data/**`
- **PREPARED минутные данные** (нормализованные/очищенные от дублей, UTC): `prepared/**`
- **Экономические календари** (агрегированная мета‑информация, UTC): `economic_calendars/**`

> ⚠️ Права на **RAW** и **PREPARED** остаются у исходных провайдеров. Этот репозиторий **не** переразрешает их лицензии.

---

## 🧩 Логика привязки (Binding)

### 1) RAW → PREPARED в data-hub 
- PREPARED‑файлы генерируются из RAW анализатором и сопровождаются **манифестами анализа** `analysis/YYYY/output_bundle_report/artifacts_YYYY.sha256` (маппинг «исходник→результат»). 
- Проверка связки подробно описана в [`/analysis/ANALYSIS-INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/analysis/ANALYSIS-INTEGRITY.ru.md)
- Таким образом PREPARED данные **криптографически привязаны** к конкретному набору RAW.
> 📌 **Анализатор состоит из 2-х основных этапов: подоготовка минутных данных и анализ разрывов. Экономические календари также привязаны к манифесту анализа так как участвуют в анализе разрывов. Их можно верифицировать с манифестом анализа что подтверждает полноценную связь всех компонентов в моменте времени.**


### 2) data-hub – PREPARED → results – файлы результатов годовых прогонов
- В *results* каждый годовой прогон имеет собственный `artifacts_YYYY.sha256` (плюс `.asc`, `.ots` для HEADLINE), где перечислены **все использованные входные файлы** (включая PREPARED‑минутки и экономические календари).  
- Проверка связки:
  1. Сравнить SHA‑256 PREPARED‑файлов перечисленных в **results** – `results/**/artifacts_YYYY.sha256`, с SHA‑256 соответствующих файлов в `prepared/YYYY**` **data-hub**.
  2. Аналогично для календарных файлов: хэши из **results** – `results/**/artifacts_YYYY.sha256` сравнить с файлами в `economic_calendars/YYYY/**` **data-hub**.

### 3) Архивы‑роллап (OTS‑якоря во времени)
- Для упрощения аудита используются сами **архивы (tar.gz/tar.xz)** и **архивы‑снимки (SHA‑256, GPG и OTS)** (roll‑up) ключевых наборов входов: «все PREPARED», «все календари».  
- Их SHA‑256, GPG и OTS публикуются в **data-hub** `integrity/**`. Эти архивы‑снимки **не заменяют** покомпонентные манифесты, а дают
  **доказательство состояния набора в момент времени** (Bitcoin‑якорь).  
- Аудитор:
  - убеждается, что распакованные файлы из архивов соответствуют хэшам в текущих папках (`source_data/`, `prepared/`, `economic_calendars/`),  
  - и что **годовые манифесты results** ссылаются ровно на эти же файлы (см. пункт 2).

> 🧠 Итого: цепочка «RAW → PREPARED → Results» подтверждается комбинацией **покомпонентных манифестов** и **архивов‑снимков с OTS**.

---

## Таблицы якорей

### A) RAW минутные данные (архив-снимок)

| Поле | Значение |
|---|---|
| Архив | `eurusd_raw_2001-2025-07.tar.xz` |
| Содержимое | Сырые минутные данные (M1) из HistData; без модификаций |
| Хэш-функция | `SHA-256` |
| SHA-256 архива | `7654b325da63fb415ad0a1aef17daf1a9f1ea721d0bf50413eacdd3d5c5bab7d` |
| Подпись GPG (.asc) | `integrity/source_data/eurusd_raw_2001-2025-07.tar.xz.sha256.asc` |
| OTS (.ots) | `integrity/source_data/eurusd_raw_2001-2025-07.tar.xz.sha256.ots` |
| Bitcoin txid | `d883cb3a197d8ed47a184b4dcd305047cedae9a0ad948bd7993737af571ce088` |
| Высота блока | `909599` |
| Время блока (UTC) | `2025-08-11T19:21:02Z` |
| Ссылка (data-hub) | [`source_data/eurusd_raw_2001-2025-07.tar.xz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/source_data/eurusd_raw_2001-2025-07.tar.xz) |

---

### B) PREPARED минутные данные (архив-снимок)

| Поле | Значение |
|---|---|
| Архив | `eurusd_prepared_2001-2025-07.tar.gz` |
| Содержимое | Подготовленные минутные данные (UTC±00:00) после фильтра/нормализации |
| Хэш-функция | `SHA-256` |
| SHA-256 архива | `e81f26072b48e62eb37dcd4da9919608e05da871b7264d3718e01244a2658d5f` |
| Подпись GPG (.asc) | `integrity/prepared/eurusd_prepared_2001-2025-07.tar.gz.sha256.asc` |
| OTS (.ots) | `integrity/prepared/eurusd_prepared_2001-2025-07.tar.gz.sha256.ots` |
| Bitcoin txid | `3646771ecc29d275b1b80ead9d5866a3b8867e6488df8d42145e2824a06e2a71` |
| Высота блока | `910536` |
| Время блока (UTC) | `2025-08-18T02:06:26Z` |
| Ссылка (data-hub) | [`prepared/eurusd_prepared_2001-2025-07.tar.gz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/prepared/eurusd_prepared_2001-2025-07.tar.gz) |

---

### C) Экономические календари (архив-снимок)

| Поле | Значение |
|---|---|
| Архив | `calendars_2001-2025-07.tar.gz` |
| Содержимое | Календарные метаданные (центробанки/статведомства), времена публикаций в UTC |
| Хэш-функция | `SHA-256` |
| SHA-256 архива | `0bd28458c49affc3b052116279827a8c840edf2dc4295d57a0b7e2a7b0b2e045` |
| Подпись GPG (.asc) | `integrity/economic_calendars/calendars_2001-2025-07.tar.gz.sha256.asc` |
| OTS (.ots) | `integrity/economic_calendars/calendars_2001-2025-07.tar.gz.sha256.ots` |
| Bitcoin txid | `a95e00f437575dad58c5e074352b6f4c9637ace705eccb05aa936e1cb99c6ffb` |
| Высота блока | `910177` |
| Время блока (UTC) | `2025-08-15T16:31:10Z` |
| Ссылка (data-hub) | [`economic_calendars/calendars_2001-2025-07.tar.gz`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/economic_calendars/calendars_2001-2025-07.tar.gz) |

---

## 🔍 Инструкции по верификации

- **[results/docs/`INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md)** — команды проверки SHA‑256/GPG/OTS, в т.ч. заметка про **абсолютные пути** в манифестах (как «ребейзить» в относительные для `sha256sum -c`).  
- **`analysis/ANALYSIS-INTEGRITY.ru.md`** — специальная ремарка про **нормализацию строки** в годовом отчёте перед хэшированием (чтобы совпадал с манифестом).

---

## 📝 Примечания

- Манифесты могут содержать **абсолютные пути** — это не влияет на корректность хэшей. Для локальной проверки используйте «ребейз» путей на относительные (см. [results/docs/`INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md)).  
- Этот файл описывает **логику привязки**.
- Для сторонних данных действуют условия их провайдеров; см. `LICENSES.md` и `NOTICE-THIRD-PARTY*`.

---

## 🔗 Быстрые ссылки

- Подробная инструкция по аудиту: [results/docs/AUDIT.ru.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.ru.md)
- Гайд по верификации: [results/docs/`INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md)
- Нюанс верификации отчёта анализа: [`analysis/ANALYSIS-INTEGRITY.ru.md`](https://github.com/euro-macromechanica-backtest/data-hub/blob/main/analysis/ANALYSIS-INTEGRITY.ru.md)
- Сырые данные: [`source_data/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data)
- Подготовленные минутки: [`prepared/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/prepared)
- Календари: [`economic_calendars/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/economic_calendars)
- Результаты (годовые манифесты): см. репозиторий **results** – (`artifacts_YYYY.sha256` + `.asc` + `.ots` для HEADLINE)
