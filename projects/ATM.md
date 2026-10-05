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

# ATM

## 📌 Задача

Меню банкомата: проверить баланс, пополнить, снять деньги, выйти.

## 💻 Код (текущая версия, требует переписывания)

```python
Balance=int(input('Введите баланс: '))
Znach=int(input('1. Проверить баланс'
' 2. Пополнить'
' 3. Снять деньги'
' 4. Выйти'))
if Znach==1:
    print(f'Ваш баланс:{Balance}')
    Znach=int(input('1. Проверить баланс'
' 2. Пополнить'
' 3. Снять деньги'
' 4. Выйти'))
if Znach==2:
    Add=int(input('Введите сумму пополнения: '))
    Balance=Balance+Add
    Znach=int(input('1. Проверить баланс'
' 2. Пополнить'
' 3. Снять деньги'
' 4. Выйти'))
if Znach==3:
    Take=int(input('Сколько снять?'))
    if Balance>=Take: 
        Balance=Balance-Take
    else: print('Недостаточно средств(ты бомж)')
    Znach=int(input('1. Проверить баланс'
' 2. Пополнить'
' 3. Снять деньги'
' 4. Выйти'))
if Znach==4:print('Пока пока')
```

## 🔗 Применённая теория

- [[006 Conditions]]
- [[007 Loops]] — заявлена, но фактически не применена как надо (см. ниже)

## 💻 Код (текущая версия, через функции)

```python
balance = int(input('Введите баланс: '))
def show_menu():
    print('''1. Проверить баланс
2. Пополнить
3. Снять деньги
4. Выйти''')

def is_valid_amount(balance,amount):
    if amount<=balance:
        return True
    else: return False

def deposit(balance,amount):
    return balance+amount

def withdraw(balance,amount):
    if is_valid_amount(balance,amount):
        return balance-amount
    else:
        print('Недостаточно средств')
        return balance

user_answer=0
while user_answer!=4:
    show_menu()
    user_answer=int(input('Выберите действие: '))
    if user_answer==1:
        print(f'Ваш баланс: {balance}')
    if user_answer==2:
        amount=int(input('Введите сумму для пополнения: '))
        balance=deposit(balance,amount)
        print(f'Ваш баланс: {balance}')
    if user_answer==3:
        amount=int(input('Введите сумму для снятия: '))
        balance=withdraw(balance,amount)
        print(f'Ваш баланс: {balance}')
print('До свидания, приходите еще')
```

## 📝 Заметки / Ревью

**✅ ИСПРАВЛЕНО.** Переписан через функции после темы [[011 Functions]]: `show_menu()`, `is_valid_amount()`, `deposit()`, `withdraw()`. Главное — появился реальный `while` вокруг меню вместо цепочки совпадений. `withdraw()` вызывает `is_valid_amount()` — правильная композиция функций. Scope применён правильно — баланс меняется через параметры + `return`, а не через прямое изменение глобальной переменной внутри функции.

**Мелкий стиль-нит:** `is_valid_amount` возвращает `True`/`False` через явный `if/else`, хотя сравнение уже само по себе булево — можно одной строкой. `deposit()` не проверяет положительность суммы.

---

## 📜 История версий

- **v1** — фейковое меню, нет реального цикла
- **v2 → v3** — переписан через функции, баг закрыт, snake_case выдержан полностью

См. также [[Bug Journal]].
