---
type: moc
tags:
  - roadmap
status: active
created: 2026-10-02
---

# Handbook Progress

> Основной курс на этапе основ Python: [Основы Python — хендбук Яндекса](https://contest.yandex.ru/tracks/python/).
> Roadmap.sh — карта дальнейшего пути, Learning OS — способ запоминать. Связано: [[Roadmap]], [[Python]], [[AGENTS]].

---

## Правило

**Следующая глава начинается только когда по предыдущей есть заметка в `learning/` и пройден Examiner хотя бы раз.**

Текст хендбука в `raw/` не копируется (материалы авторов). В `raw/` кладётся файл-ссылка: URL главы, название, список решённых задач.

---

## Карта глав

| Глава | Старые заметки (теория, не моими словами) | Статус | Заметка в `learning/` | Examiner |
|---|---|---|---|---|
| [1. Введение](https://contest.yandex.ru/tracks/python/introduction/what-is-python) | [[000 Python Philosophy]] | диагностика | — | — |
| [2. Базовые конструкции](https://contest.yandex.ru/tracks/python/basic-python-constructs/input-output-numbers-strings-formatting) | [[001 Variables]], [[002 Data Types]], [[003 F-strings]], [[005 Operators]], [[006 Conditions]], [[007 Loops]] | диагностика | — | — |
| [3. Коллекции и память](https://contest.yandex.ru/tracks/python/collections-and-memory/strings-tuples-lists) | [[010 lists]], [[012 Dictionaries]], [[014 Tuples]], [[015 Sets]] | диагностика, пробелы: модель памяти, файлы, JSON | — | — |
| [4.1 Функции, области видимости](https://contest.yandex.ru/tracks/python/functions-in-python/functions-scopes-and-parameters) | [[011 Functions]] | диагностика (scope, return, global) | — | — |
| [4.2 Аргументы, lambda, функции высшего порядка](https://contest.yandex.ru/tracks/python/functions-in-python/positional-keyword-higher-order-and-lambda-functions) | [[019 Args and Kwargs]] | **🔄 первый цикл Learning OS** | — | — |
| [4.3 Рекурсия, декораторы, генераторы](https://contest.yandex.ru/tracks/python/functions-in-python/recursion-decorators-generators) | — | не начато | — | — |
| [4.5 Проект: ASGI/WSGI-сервер](https://contest.yandex.ru/tracks/python/functions-in-python/building-asgi-wsgi-server) | — | позже | — | — |
| [5. ООП](https://contest.yandex.ru/tracks/python/object-oriented-programming/python-object-model-classes-fields-methods) | [[013 Exceptions]], [[008 Modules]] (частично) | не начато | — | — |
| [6. Библиотеки: math, NumPy, pandas, requests](https://contest.yandex.ru/tracks/python/data-processing-libraries/math-and-numpy) | — | не начато, **цель Roadmap** | — | — |

**Вне хендбука:** [[009 Random]], [[016 Big O]], [[017 Sorting Algorithms]], [[018 Backend (заготовка)]] — паркуются, пока не пройдена глава 6.

---

## Статусы

- **диагностика** — старая теория есть, но не факт, что освоено. Проверяется Examiner (5 вопросов). Результат 4 из 5 и выше → «пройдено», иначе → цикл на слабую часть
- **🔄** — идёт цикл Learning OS
- **пройдено** — есть заметка в `learning/` и пройден Examiner
- **не начато** — по правилу выше стартует после предыдущей главы

---

## Недельный ритм (минимум)

| День | Что | Время |
|---|---|---|
| Будни | Глава хендбука + задачи | 15 мин |
| Будни | Заметка в `learning/` по памяти | 10 мин |
| Раз в неделю | Examiner по пройденному за неделю | 20 мин |

Повтор Examiner по теме: через 1 день, 3 дня, неделю.

---

## Связь с Roadmap

Глава 6 хендбука (math, NumPy, pandas, requests) совпадает с целью roadmap.sh Data Analysis. После неё — SQL и визуализация по [[Roadmap]].
