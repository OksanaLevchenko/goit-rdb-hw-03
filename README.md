# goit-rdb-hw-03

## Dataset

Для домашнього завдання я використала датасет **Bank Marketing**.

Офіційне джерело: UCI Machine Learning Repository.

Dataset ID: `222`.

Датасет містить інформацію про маркетингову кампанію банку та контакти з клієнтами.

Цільова змінна `y` показує, чи підписався клієнт на строковий депозит.

## Data loading

Дані завантажуються у notebook за допомогою пакета `ucimlrepo`.

```python
from ucimlrepo import fetch_ucirepo

dataset = fetch_ucirepo(id=222)

Після завантаження features і target об’єднуються в один DataFrame та зберігаються у CSV.

Dataset size

Кількість рядків: 45 211.

У роботі використовується повний датасет.

What was done

У notebook виконано:

запуск PostgreSQL через pgserver;
створення staging-таблиці;
завантаження CSV через COPY FROM STDIN;
створення clean-таблиці;
очищення та типізація даних;
перевірка дублікатів;
перевірка NULL та unknown;
аналіз категоріальних і числових колонок;
outlier-check;
10 DQL/EDA SQL-запитів;
Reflection.
ML task

Для цього датасету природною ML-задачею є classification.

Мета — передбачити, чи підпишеться клієнт на депозит.

Колонку duration не варто використовувати як feature для прогнозу до завершення дзвінка, тому що вона може створити data leakage.

How to run
Відкрити notebook у Google Colab.
Запустити Runtime → Run all.
Notebook встановить залежності, запустить PostgreSQL, завантажить дані та виконає всі SQL-запити.
