---
tags:
  - bugs
type: log
status: ongoing
---

# Bug Journal

> Сюда попадают реальные ошибки из практики — синтаксические и логические. Не удалять записи, даже когда баг исправлен — это история прогресса.

---

## ✅ SyntaxError — unterminated f-string ([[Student Card]], черновик)

```
ivansolovev@MacBook-Air-Ivan ~ % /usr/local/bin/python3 /Users/ivansolovev/Desktop/Develop/roadmap/day1/student_card.py
  File "/Users/ivansolovev/Desktop/Develop/roadmap/day1/student_card.py", line 11
    print(f'========================
          ^
SyntaxError: unterminated f-string literal (detected at line 11)
```

---

## ✅ Логический баг — потеря выигрыша при выигрыше ([[Casino]])

`if rand==7 / if rand==3 / else` вместо `if/elif/else`. При `rand==7` код всё равно проваливался в `else` следующего блока и списывал ставку вместо начисления выигрыша. **Исправлено** — см. [[Casino]].

---

## ✅ Метод без вызова ([[Buy Manager]])

`.lower` вместо `.lower()` — в список попадала ссылка на метод, а не строка. Из-за этого `remove()` никогда не находил совпадений. **Исправлено** — см. [[Buy Manager]].

---

## ✅ Фейковое меню без цикла ([[ATM]])

Меню работало только потому что переменная случайно перезаписывалась между блоками `if`, не было настоящего `while` вокруг меню. **Исправлено** переписыванием через функции после [[011 Functions]] — см. [[ATM]].

---

## ✅ Потерянный `input()` в retry-цикле ([[Expense Tracker]] / mini-tasks day06)

```python
def safe_int(promt):
    while True:
        try:
            value = int(promt)   # promt — это текст подсказки, а не ввод пользователя!
        except ValueError:
            print("...")
```

`input(promt)` вообще не вызывался — функция пыталась сконвертировать сам текст подсказки в число — бесконечный цикл `while True` с одинаковым результатом каждый раз, без шанса реально ввести число. **Исправлено** — `int(input(promt))` вместо `int(promt)`.

---

## ✅ Прямая мутация в `except`, ломающая retry ([[Expense Tracker]] / mini-tasks day06)

В `safe_int`/`safe_divide` внутри `except ValueError:` стоял `return("Текст ошибки")` вместо `print(...)`. `return` внутри `while True` немедленно останавливал функцию при первой же ошибке — весь смысл retry-цикла пропадал, плюс функция начинала возвращать то `int`, то `str` — разные типы из одной функции. Правило: `return` в `except` уместен, только когда нет окружающего `while True` для retry (как в `get_by_index`/`get_value_key`). **Исправлено** — вернул `print` + продолжение цикла туда, где нужен retry.

---

## ✅ `break` без своего цикла ломал не ту ветку ([[Expense Tracker]])

```python
if user_choise == 1:
    category = input(...)
    try:
        amount = int(input(...))
        break        # ← своего while True нет — прерывает ВНЕШНИЙ while
    except ValueError:
        print(...)
    add_expense(expenses, category, amount)
```

`break` всегда действует на ближайший объемлющий цикл. Без своего `while True` вокруг `try` он прерывал **внешний** цикл меню целиком, пропуская `add_expense` при успехе, и падал `NameError` при ошибке (`amount` не успевал создаться). До этого была ещё промежуточная версия через `continue`, которая откатывала к внешнему циклу и заставляла вводить категорию заново даже при ошибке только в сумме. **Исправлено** — вложенный `while True` именно вокруг ввода суммы.

---

## ✅ `expenses[value]` вместо `value` ([[Expense Tracker]])

```python
for key, value in expenses.items():
    print(key, expenses[value])   # value уже и есть нужные данные
```

Попытка искать в словаре по **значению** как по ключу. Как только `value` стал списком (после фикса `add_expense`), это бы ещё и упало с `TypeError: unhashable type: 'list'`. **Исправлено** — `print(key, value)` напрямую.
