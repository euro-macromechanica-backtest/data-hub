# Euro Macromechanica (EMM) Backtest — Data Hub  
**⚠️ Внимание: репозиторий содержит сторонние датасеты (third-party).**

> Этот репозиторий — часть экосистемы **Euro Macromechanica (EMM) Backtest** и служит хабом данных для **прозрачности и воспроизводимости** бэктеста стратегии EMM: здесь хранятся сырые минутные ряды (например, HistData), подготовленные файлы, собранные экономические календари и агрегаты анализа.

---

## ‼️ Читайте [обзор и методологию – Euro Macromechanica (EMM) Backtest](https://github.com/euro-macromechanica-backtest/results/blob/main/README.ru.md)

---

## 🔗 Связанная экосистема

- **Результаты бэктеста, подтверждение наличия стратегии, политика качества данных (core baseline/extended baseline/stress), интегрити-материалы** — *[results](https://github.com/euro-macromechanica-backtest/results)*  
- **Нормализатор минутных данных и экономических календарей, анализатор отчётов о разрывах** — *[data-preparation-toolkit](https://github.com/euro-macromechanica-backtest/data-preparation-toolkit)*
- **Схема методологии расчёта метрик и калькулятор метрик** для результатов бэктеста EMM — *[metrics-toolkit](https://github.com/euro-macromechanica-backtest/metrics-toolkit)*

---

## 🧭 Назначение

- Сбор, нормализация и хранение исходных данных для бэктеста EMM.
- Публикация агрегатов анализа (разрывы) и материалов для верификации результатов.

Итоговый вердикт по качеству данных и правила включения лет в **baseline/stress** см. в репозитории результатов:  
**`results` → [`data_quality_policy/`](https://github.com/euro-macromechanica-backtest/results/tree/main/data_quality_policy)**

---

## 🔐 Интегрити-артефакты

- Все минутные данные (RAW) и текстовые отчёты по разрывам **EUR/USD (январь 2001 — август 2025)** в `source_data/raw/**` сопровождаются roll-up-манифестами `.sha256`, **GPG-подписью** и **OpenTimestamps (OTS)** — это фиксирует момент получения данных.  
- Все минутные данные (PREPARED) в `source_data/prepared/` — аналогично: roll-up-манифест `.sha256` / GPG / OTS.  
- Скомпилированные экономические календари в `economic_calendars/` — аналогично: roll-up-манифест `.sha256` / GPG / OTS.  
- CSV-файлы анализа разрывов для оценки M5 публикуются вместе с манифестом `artifacts.sha256`, который содержит **SHA-256-хэши всех входных и выходных файлов**. Это позволяет проверить, что опубликованные результаты соответствуют заявленным входам без изменения содержимого. Дополнительно публикуются roll-up-манифест (агрегирующий все **.sha256-манифесты**), **GPG-подпись и OTS-якорь (OpenTimestamps)**.

Инструкции по аудиту см. **[results/docs/AUDIT.ru.md](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.ru.md)**
Инструкция по верификации SHA-256, GPG-подписей и OTS-якоря см. **[results/docs/INTEGRITY.ru.MD](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md)**
Публичный GPG-ключ см. в репозитории результатов:  
**`results` → [`keys/emm_pub_key.asc`](https://github.com/euro-macromechanica-backtest/results/tree/main/keys/emm_pub_key.asc)**

---

## 📁 Структура

```
source_data/raw            # сырые сторонние датасеты (действуют условия оригинальных провайдеров)
source_data/prepared/      # нормализованные/очищенные файлы из source_data
economic_calendars/        # собранные календарные метаданные (UTC и raw)
data_quality_analysis/     # агрегаты: гэпы, сводные таблицы
integrity/                 # artifacts.sha256 (+ .asc, .ots) для верификации
SOURCES.md                 # происхождение (URL)
LICENSES.md                # карта лицензий по папкам
NOTICE-THIRD-PARTY.md      # уведомление о правах сторонних провайдеров
DATA-USAGE.md              # правила использования материалов из этого репозитория
INPUTS-PROVENANCE.md       # привязка входных данных к результатам (есть версия на RU)
```

---

## ⚖️ Лицензии и права

- Права на **сторонние датасеты** принадлежат их провайдерам. Этот репозиторий **не** релицензирует чужие данные.  
  См. `LICENSES.md`, `NOTICE-THIRD-PARTY.md` и `SOURCES.md`.
- Для собственных агрегатов/отчётов действуют лицензии, указанные в `LICENSES.md`.
- **Takedown:** по запросу правообладателя сторонних данных автор удалит соответствующие файлы в течение **5 рабочих дней**.

---

## ✉️ Контакты

GitHub: **@rleydev (thelaziestcat)** · Email: **thelazyazzcat@gmail.com** / **thelaziestcat@proton.me**

---

> Кратко: этот репозиторий — **хранилище данных и агрегатов**, снабжённое проверяемыми артефактами целостности (SHA-256 / GPG / OTS) для воспроизводимости бэктеста EMM.
