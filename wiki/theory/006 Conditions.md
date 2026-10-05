---
tags:
  - python/core
created: 2026-06-30
status: learning
level: 1
---

# Conditions

## 🧠 Что это

Позволяют программе принимать решения.

---

```python
if condition:
    ...

elif condition:
    ...

else:
    ...
```

---

## Важно

Условия должны возвращать bool.

```python
age >= 18
```

↓

```
True
```

---

## Вложенные условия

```python
if age >= 18:

    if age >= 21:
        ...
```

---

## Хороший стиль

Лучше

```python
if is_student:
```

чем

```python
if is_student == True:
```

---

## Где используется

Везде.

Игры.

Сайты.

ML.

AI.

---

## 🚀 Мини-проект

[[Guess Number]], [[BMI Calculator]], [[ATM]]

---

## 🔗 Связанные темы

- [[005 Operators]]
- [[007 Loops]]