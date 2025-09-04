# Euro Macromechanica (EMM) Backtest — Data Hub  
**⚠️ Внимание: внутри есть сторонние датасеты (third-party).**

Этот репозиторий — часть экосистемы **Euro Macromechanica (EMM) Backtest** и служит хабом данных для **прозрачности и воспроизводимости** бэктеста стратегии EMM: здесь хранятся сырые минутные ряды (например, HistData), подготовленные файлы, скомпилированные календари и агрегаты анализа.

---

## ‼️ Читайте главный [results/`README.ru.md`](https://github.com/euro-macromechanica-backtest/results/blob/main/README.ru.md) экосистемы **Euro Macromechanica (EMM) Backtest!** 

---

## 🔗 Связанная экосистема

- **Результаты бэктеста, доказательство наличия стратегии, политика качества данных, интегриты** — *[results](https://github.com/euro-macromechanica-backtest/results)* 
- **Анализатор и нормализатор минутных данных** – *[minute-data-analyzer](https://github.com/euro-macromechanica-backtest/minute-data-analyzer)*
- **Сборщик экономических календарей** – *[economic-calendar-builder](https://github.com/euro-macromechanica-backtest/economic-calendar-builder)*

---

## 🧭 Назначение

- Сбор, нормализация и хранение исходных данных для бэктеста EMM.
- Публикация агрегатов анализа (разрывы/континуити и пр.) и материалов для верификации результата.
- Подробные процессы подготовки данных: см. [`economic_calendars/README.ru.md`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/economic_calendars/README.ru.md) (сбор и нормализация календарей)
  и [`analysis/README.ru.md`](https://github.com/euro-macromechanica-backtest/data-hub/tree/main/analysis/README.ru.md) (метрики гэпов/continuity и сводные таблицы).


Итоговый вердикт по качеству данных и правила включения лет в **headline/stress** см. в репозитории результатов:  
**`results` → [`data_quality_policy/…`](https://github.com/euro-macromechanica-backtest/results/tree/main/data_quality_policy)**

---

## 🔐 Интегрити-артефакты

- Все минутные данные **EUR/USD (янв-2001 — конец июля-2025)** в `source_data/` сопровождаются архивом со **SHA-256**, **GPG-подписью** и **OpenTimestamps (OTS)** — это фиксирует момент получения данных.
- Скомпилированные экономические календари — аналогично (SHA-256 / GPG / OTS).
- Отчёты анализа публикуются бандлами с манифестом `artifacts.sha256`, в котором перечислены **хэши всех входных и выходных файлов**. По ним можно проверить, что выпущенный результат соответствует заявленным входам (без изменения содержимого).

Инструкции для проверки см. [**results/docs/`AUDIT.ru.md`**](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/AUDIT.ru.md).

**Примечание**: SHA-256 хэши могут содержать абсолютные пути; это не влияет на корректность хэшей. Для проверки с такими путями см. специальный раздел в [**results/docs/`INTEGRITY.ru.md`**](https://github.com/euro-macromechanica-backtest/results/blob/main/docs/INTEGRITY.ru.md).

Публичный GPG ключ в см. в репозитории результатов:  
**`results` → [`keys/emm_public_key.asc`](https://github.com/euro-macromechanica-backtest/results/tree/main/keys/emm_pub_key.asc)**

---

## 📁 Структура

```
source_data/              # сырые сторонние датасеты (действуют оригинальные условия)
prepared/                 # нормализованные/очищенные файлы из source_data
economic_calendars/       # скомпилированные календарные метаданные (UTC), где это разрешено источником
                          # подробности: economic_calendars/README.md
analysis/                 # агрегаты: гэпы, continuity-метрики, сводные таблицы
                          # подробности: analysis/README.ru.md
integrity/                # artifacts.sha256 (+ .asc, .ots) для верификации
SOURCES.md                # происхождение (URL, SHA-256)
LICENSES.md               # карта лицензий по папкам
NOTICE-THIRD-PARTY.md     # уведомление о правах сторонних провайдеров
DATA-USAGE.md             # правила использования материалов из этого репозитория

```

---



## ⚖️ Лицензии и права

- Права на **сторонние датасеты** принадлежат их провайдерам. Этот репозиторий **не** релицензирует чужие данные.  
  См. `LICENSES.md`, `NOTICE-THIRD-PARTY.md` и `SOURCES.md`.
- Для собственных агрегатов/отчётов действуют лицензии, указанные в `LICENSES.md`.
- **Takedown:** по запросу правообладателя сторонних данных автор удалит соответствующие файлы в течение **5 рабочих дней**.

---

## ✉️ Контакты

GitHub: **@rleydev (thelaziestcat)** · Email: **thelaziestcat@proton.me**  / **thelazyazzcat@gmail.com**

--- 

> Кратко: этот репозиторий — **хранилище данных и агрегатов**, снабжённое проверяемыми артефактами целостности (SHA-256/GPG/OTS) для воспроизводимости бэктеста EMM.
