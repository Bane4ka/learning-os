---
type: project
tags:
  - python/core
level: 1
day: 1
status: done
theory:
  - "[[001 Variables]]"
  - "[[003 F-strings]]"
  - "[[006 Conditions]]"
---

# Student Card

## 📌 Задача

Собрать данные о пользователе через `input()` и вывести их в виде аккуратной карточки.

## 💻 Код

```python
name=input("Name: ")
age=input("Age: ")
height=input("Height: ")
weight=input("Weight: ")
fav=input("Favorite programming language: ")
stud=input("Are you a student?: ").lower()
if stud=='yes' or stud=='y':
    stud='Student'
else:
    stud='Not a student'
print(f'''(
Name: {name}
Age: {age}
Height: {height}
Weight: {weight}
Favorite programming language: {fav}
status: {stud}''')
```

## 🔗 Применённая теория

- [[001 Variables]] — переменные для хранения ввода
- [[003 F-strings]] — форматированный вывод карточки
- [[006 Conditions]] — `if/else` для определения статуса

## 📝 Заметки

Первый проект, без структурных багов. `.lower()` использован правильно с самого начала — хорошая база на будущее (сравни с тем, что в `buy_manager.py` этот же метод сначала забыли вызвать).
