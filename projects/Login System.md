---
type: project
tags:
  - python/core
level: 1
day: 2
status: done
theory:
  - "[[006 Conditions]]"
  - "[[007 Loops]]"
---

# Login System

## 📌 Задача

Проверка логина/пароля с ограниченным числом попыток.

## 💻 Код

```python
login='admin'
password='12345'
count_fails=3
while count_fails!=0:
    user_login=str(input('Введите логин: '))
    user_password=str(input('Введите пароль: '))
    if user_login==login and user_password==password:
        print('Добро пожаловать!')
        break
    else:
        count_fails=count_fails-1
        print(f"Неверный логин или пароль. У вас осталось {count_fails} попыток")
if count_fails==0:
    print('Попытки кончились повторите через 20 минут')
```

## 🔗 Применённая теория

- [[006 Conditions]] — `and`, `if/else`
- [[007 Loops]] — `while` + `break` использованы правильно

## 📝 Заметки

Один из лучших файлов на текущий момент. `while` с настоящим условием выхода, `break` при успехе, декремент счётчика — всё логично и без обходных путей. Именно так должна выглядеть структура цикла в [[ATM]] — сравни эти два файла, разница в подходе к циклу видна невооружённым глазом.
