# 🔗 Inputs — Provenance & Binding — Привязка входных данных к результатам Euro Macromechanica (EMM) Backtest

Этот документ фиксирует, **как именно** входные данные из репозитория **data-hub** (`raw/`, `prepared/`, `economic_calendars/`)
сопоставляются с их использованием в публичных результатах бэктеста **results**. Здесь описана **логика связки**.
Подробные команды проверки хэшей см. в [results/docs/INTEGRITY.ru.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md) — для RAW HistData, PREPARED и экономических календарей.

---

## 🎯 Назначение
- Обозначить, **какие именно входы** (сырые минутные данные, подготовленные минутные данные, календари) использовались.
- Показать, **где лежат хэши/подписи/OTS**, подтверждающие **момент времени** и **целостность** входов.
- Дать **простую карту соответствий** между **data-hub** и **results**.

## 📦 Охват (что считается «входами»)
- **RAW-минутные данные** (*HistData*): `source_data/raw/**`
- **PREPARED-минутные данные** (нормализованные/очищенные от дублей, UTC): `source_data/prepared/**`
- **Экономические календари** (агрегированная мета-информация, UTC): `economic_calendars/prepared/**`

> ⚠️ Права на **RAW** и **PREPARED** остаются у исходных провайдеров. Этот репозиторий их **не** перезалицензирует.

---

## 🧩 Логика привязки (Binding)

### 1) RAW → PREPARED в **data-hub**
- PREPARED-файлы генерируются **детерминированно** из RAW с помощью нормализатора.
  При использовании **minute data normalizer** с фиксированными версиями Python и зависимостей (см. `requirements.lock`)
  одни и те же входы всегда дают **одинаковые SHA-256** выходных CSV — **независимо от ОС**.
- Таким образом, PREPARED-данные **криптографически привязаны** к конкретному набору RAW.
- ▶️ **Смотреть README нормализатора и `requirements.lock`** для точных версий и параметров запуска.

> 📌 Нормализатор настроен на детерминированный workflow. При соблюдении версий Python (например, 3.13.x) и пакетов из `requirements.lock`
хэши входных и выходных CSV стабильно совпадают.

### 2) **data-hub** (PREPARED) → **results** (файлы годовых прогонов)
- В **results** каждый годовой прогон имеет свой `artifacts_YYYY.sha256` (плюс `.asc`, `.ots` для BASELINE),
  где перечислены **все использованные входные файлы** (включая PREPARED-минутки и экономические календари).
- Проверка связки:
  1. Сравнить SHA-256 PREPARED-файлов, перечисленных в `results/**/artifacts_YYYY.sha256`,
     с SHA-256 соответствующих файлов в `source_data/prepared/YYYY/...csv` (в **data-hub**).
     То есть **скачать PREPARED-CSV, посчитать хэш и сверить с манифестом** `results/**/artifacts_YYYY.sha256`.
  2. Аналогично для календарей: сверить хэши файлов из `results/**/artifacts_YYYY.sha256`
     с хэшами в `economic_calendars/**` (в **data-hub**).

### 3) Манифесты наборов (OTS-якоря «во времени»)
- Для облегчения аудита публикуются «roll-up»-манифесты `.sha256` с хэшами всех файлов ключевых наборов (`GPG`, `OTS`):
  например, «все PREPARED», «все календари».
- Их GPG и OTS размещены в **data-hub**: `integrity/**`. Эти манифесты дают
  **доказательство состояния набора на момент времени** (через OpenTimestamps/Bitcoin-якорь).
- Аудитор:
  - сверяет, что хэши файлов в манифесте совпадают с текущими файлами в `source_data/raw/YYYY/`, `source_data/prepared/YYYY/`, `economic_calendars/`;
  - и что **годовые манифесты results** ссылаются ровно на те же файлы (см. пункт 2).

> 🧠 Итог: цепочка **RAW → PREPARED → Results** подтверждается комбинацией
**покомпонентных манифестов** и **общих roll-up-манифестов с GPG и OTS**.

---

## 📝 Примечания
- Этот файл описывает **логику привязки**.
- ▶️ **См. также:** README нормализатора минутных данных и файл `requirements.lock` (точные версии Python/пакетов).
- Для сторонних данных действуют условия их провайдеров; см. `LICENSES.md` и `NOTICE-THIRD-PARTY*`.

---

## 🔗 Быстрые ссылки
- Инструкция по аудиту: [results/docs/AUDIT.ru.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.ru.md)
- Гайд по верификации: [results/docs/INTEGRITY.ru.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md)
- Сырые данные: [`source_data/raw`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data/raw)
- Подготовленные минутки: [`source_data/prepared/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/source_data/prepared)
- Календари: [`economic_calendars/`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/economic_calendars)
- Результаты (годовые манифесты): репозиторий **results** (`artifacts_YYYY.sha256` + `.asc` + `.ots` для BASELINE)
- Minute data normalizer [data-preparation-toolkit/minute_data_normalizer](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit/tree/main/minute_data_normalizer)