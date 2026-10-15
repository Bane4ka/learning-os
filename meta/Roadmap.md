---
tags:
  - roadmap
created: 2026-08-16
status: active
type: moc
---
[[Programming MOC]]
[[Principles]]

# 🗺 Roadmap — Python for Data Analysis (roadmap.sh)


**Источник плана:** [roadmap.sh — Python for Data Analysis](https://roadmap.sh/data-analysis) (файл, который ты прислал). Идём строго по нему до конца, затем — ML Engineering roadmap (следующий этап, отдельный план, пока не расписываю заранее).

---

## 🎯 Текущая цель

**Конечная цель — ML Engineer.** Python Data Analysis — первый этап, фундамент под ML. Параллельно — свои pet-проекты по мере роста навыков (уточнено 02.10.2026).

Пройти этот roadmap полностью — от основ Python до продвинутых тем анализа данных (SQL, визуализация, большие данные) — затем перейти на ML Engineering. Не распыляться на другие направления, пока этот план не пройден или не появится веская причина отклониться.

---

## ✅ Уже закрыто (входит в этот roadmap)

### Python — База
- [[001 Variables]], [[002 Data Types]], [[005 Operators]], [[006 Conditions]], [[007 Loops]] — Introduction / Conditionals / Loops / Operators / Data Types
- [[003 F-strings]] — Printing / Variables (частично)
- [[010 lists]], [[012 Dictionaries]], [[014 Tuples]], [[015 Sets]] — Data Structures (Lists, Tuples, Dictionaries, Sets)
- [[011 Functions]] — Defining Functions (база)

### Environment
- VS Code — есть, используется постоянно
- Git/GitHub — вне этого roadmap, но уже освоено на практике (коммиты в `python-roadmap`)

---

## ⏸ Открытые пробелы в блоке "Functions & Methods" — закрыть в первую очередь

Прежде чем идти в NumPy/Pandas, где это используется на каждом шагу:

- **args & kwargs** — 🔄 текущая тема, теория готова ([[019 Args and Kwargs]])
- **Lambda Functions** — упоминалось вскользь в [[Quiz Leaderboard]] как "готовый рецепт", реально не объяснено
- **List Comprehensions** — не пройдено
- **Built-in Functions** (обзор `map`, `filter`, `zip`, `enumerate` и т.д. — не пройдено системно)

Это не новый большой блок теории — это короткие темы, но без них код на Pandas будет выглядеть как магия (`.apply(lambda x: ...)`, comprehensions в подготовке данных — стандартная практика).

---

## 📦 Package Management & Environment Setup — не начато

- pip, conda, virtualenv/venv
- JupyterLab, Google Colab (VS Code уже есть)

Нужно перед NumPy/Pandas — тебе физически понадобится Jupyter/Colab для удобной работы с данными, таблицами, графиками.

---

## 📊 Основной блок — Data Manipulation (не начато)

### NumPy
- Arrays & ndarray, Array Operations, Indexing & Slicing
- Linear Algebra Basics (векторы/матрицы — тут встретится математика, о которой говорили раньше)
- Random Module

### Pandas
- Series and DataFrame
- Reading Data (+ File Formats: CSV, Excel, JSON, Parquet)
- Indexing & Slicing, Filtering & Querying
- Groupby & Aggregation
- Merging & Joining
- Reshaping
- Pandas String Methods
- Polars — упомянут как альтернатива/дополнение, не приоритет на старте

### Reading Web Data
- APIs with requests
- BeautifulSoup
- scrapy (упомянут в контексте Data Cleaning на схеме, по смыслу ближе сюда)

---

## 🧹 Data Cleaning (не начато)

- Missing Values — `isnull`/`isna`, Dropping vs. Imputing, Forward/Backward Fill
- Outlier Detection — IQR, Z-score, Visual Inspection
- Data Type Conversion — Casting Types, Parsing Dates, Encoding Categories
- String Cleaning — `strip`, `replace`, `split`, `re`

---

## 📈 Exploratory Data Analysis (не начато)

- Descriptive Statistics — Mean/Median/Mode, Variance & Std. Deviation, Correlation & Covariance
- Distribution Analysis — Histogram, Boxplot
- Relationship Analysis — Scatterplot, Correlation Matrix, Cross-tabulation

---

## 🎨 Data Visualization (не начато)

- **Matplotlib** — Plot Categories, Subplots and Figures, Customizing Plots, Saving Figures
- **Seaborn** — Distribution Plots, Categorical Plots, Heatmaps, Regression Plots, Customizing Plots
- **Plotly** — Interactive Visualization
- **Dashboards** — Streamlit, Dash, Power BI / Tableau (обзорно, не глубоко)

---

## 🗄 SQL Fundamentals (не начато)

- SQL база — SELECT/WHERE/JOIN/GROUP BY и т.д.
- `sqlite3`, `SQLAlchemy` — работа с SQL из Python
- `DuckDB` + Pandas

---

## 🚀 Advanced Topics (не начато, ближе к концу плана)

- **Big Data Tools** — Dask, PySpark (обзорно)
- **Data Pipelines** — Airflow (обзорно)
- **SciPy**, **Scikit-learn** — мостик к ML
- **OOP for Data Analysis** — классы применительно к пайплайнам обработки данных
- **Geospatial Analysis** — GeoPandas (нишевая тема, по необходимости)

---

## ⏸ Припарковано — не по этому roadmap, но не выброшено

Track "Algorithms & CS fundamentals" (введён 01.08, до этого пересмотра курса):

- [[016 Big O]], [[017 Sorting Algorithms]] — теория написана, применена частично
- [[Search Algorithms]] — три функции поиска готовы, не сделан счётчик сравнений
- [[Sorting Algorithms]] (проект) — не начат
- [[Quiz Leaderboard]] — теория (tuples/sets) дана, есть черновик кода, не завершён

Это не бесполезно — Big O и структуры данных пригодятся при работе с большими датасетами (Dask/PySpark из этого же roadmap). Но сейчас не в фокусе — трек этого файла: **roadmap.sh Data Analysis**, без отвлечений.

[[013 Exceptions]] — не входит явно в этот roadmap, но уже освоено, остаётся в активе как общая база Python.

---

## 🧬 Режим работы: Learning OS (с 02.10.2026)

Каждая тема этого плана проходит цикл: источник в `raw/` → Ingest → твоя заметка в `learning/` → Tutor → Examiner → Compile → проект → Reviewer. Правила и режимы: [[AGENTS]]. Первый цикл — на теме args/kwargs (закрытие пробела выше). Основной курс на этапе основ Python — Хендбук Яндекса, прогресс: [[Handbook Progress]].

---

## ➡️ После этого плана

**ML Engineering roadmap** — следующий этап по твоим словам. Пока не расписываю по темам — сделаем это отдельным файлом, когда дойдём до конца текущего плана (или когда решишь, что пора переключаться раньше).

---

## 🔗 Связанные темы

- [[Programming MOC]]
- [[Principles]]
- [[Python]]
- [[Bug Journal]]
