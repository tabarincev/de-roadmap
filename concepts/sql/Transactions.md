## List of content
- [Что такое транзакция ?](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#что-такое-транзакция-)
- [Операторы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#операторы)
  - [BEGIN](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#begin)
  - [COMMIT](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#commit)
  - [ROLLBACK](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#rollback)
  - [SAVEPOINT](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#savepoint)
- [ACID](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#acid)
  - [Atomicity — Атомарность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#atomicity--атомарность)
  - [Consistency — Согласованность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#consistency--согласованность)
  - [Isolation — Изолированность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#isolation--изолированность)
  - [Durability — Надёжность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#durability--надёжность)
- [Уровни изоляции транзакций](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#уровни-изоляции-транзакций)
  - [Uncommitted Read (UR)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#uncommitted-read-ur)
  - [Committed Read (CR)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#committed-read-cr)
  - [Repeatable Read (RR)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#repeatable-read-rr)
  - [Serializable Read (SR)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#serializable-read-sr)
- [Последствия отсутствия уровня изоляции](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#последствия-отсутствия-уровня-изоляции)
  - [Потерянное обновление](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#потерянное-обновление)
  - [Грязное чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#грязное-чтение)
  - [Неповторяющееся чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#неповторяющееся-чтение)
  - [Фантомное чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md#фантомное-чтение)
 
# Что такое транзакция ?
В SQL транзакцией является последовательность одного или более операторов SQL, которые выполняются как единая единица работы. Транзакции используются для гарантии, что операции с базой данных выполняются согласованным и надежным образом, поддерживающим целостность данных, хранящихся в базе данных.

# Операторы
### BEGIN
### COMMIT
### ROLLBACK
### SAVEPOINT

# ACID
### Atomicity — Атомарность
### Consistency — Согласованность
### Isolation — Изолированность
### Durability — Надёжность

# Уровни изоляции транзакций
По стандарту SQL поддерживает четыре уровня изоляции транзакций:

### Uncommitted Read (UR)
- Самый низкий уровень изоляции.
- Транзакция может видеть изменения других транзакций, которые еще не завершены.

### Committed Read (CR)
- Транзакция видит только те изменения, которые были зафиксированы до начала каждой команды.
- Изменения, сделанные параллельными незавершенными транзакциями, недоступны.

### Repeatable Read (RR)
- Транзакция видит только те данные, которые были зафиксированы до её начала.
- Изменения, сделанные после начала транзакции, не видны, даже если они были зафиксированы.

### Serializable Read (SR)
- Самый высокий уровень изоляции.
- Обеспечивает выполнение транзакций так, как если бы они выполнялись последовательно, одна за другой.
- Может приводить к откатам транзакций из-за конфликтов.

# Последствия отсутствия уровня изоляции в PostgreSQL
Отсутствие или неправильный выбор уровня изоляции транзакций может привести к различным проблемам при работе с базой данных, особенно в условиях конкурентного доступа (когда несколько транзакций выполняются одновременно). Эти проблемы связаны с некорректной обработкой данных и нарушением их целостности. Рассмотрим основные последствия.

## Грязное чтение (Dirty Read)
Транзакция читает данные, которые были изменены другой незавершенной транзакцией. Если эта другая транзакция откатится, то данные, которые были прочитаны первой транзакцией, окажутся некорректными.

### **Пример:**
  1. Транзакция A обновляет значение `balance` и не завершает работу (`COMMIT`).
  2. Транзакция B читает это обновленное значение.
  3. Транзакция A делает `ROLLBACK`.

**Итог:** Транзакция B использовала несуществующие данные.

### **Решение:**
Уровень изоляции **`READ COMMITTED`** или выше предотвращает грязные чтения.

## Неповторяемое чтение (Non-Repeatable Read)
Транзакция дважды читает одни и те же данные, но между этими чтениями другая транзакция изменяет их. В результате данные оказываются несогласованными в рамках одной транзакции.

### **Пример:**
  1. Транзакция A читает `balance = 100`.
  2. Транзакция B обновляет `balance` до 200 и фиксирует изменения (`COMMIT`).
  3. Транзакция A снова читает `balance`, видя теперь значение 200.

**Итог:** Непоследовательные данные в рамках транзакции.

### **Решение:**
Уровень изоляции **`REPEATABLE READ`** или выше предотвращает неповторяемое чтение.

## Фантомное чтение (Phantom Read)
Транзакция выполняет запрос, возвращающий набор строк, но другая транзакция добавляет, удаляет или изменяет строки, соответствующие этому запросу. При повторном выполнении того же запроса результаты отличаются.

### **Пример:**
  1. Транзакция A выполняет запрос: `SELECT * FROM orders WHERE amount > 100;` (возвращает 5 строк).
  2. Транзакция B добавляет новую запись с `amount = 150` и фиксирует изменения (`COMMIT`).
  3. Транзакция A снова выполняет тот же запрос и видит уже 6 строк.

**Итог:** Различные результаты одного и того же запроса.

### **Решение:**
Уровень изоляции **`SERIALIZABLE`** предотвращает фантомные чтения.

## Потеря обновлений (Lost Update)
Две транзакции читают одно и то же значение и обновляют его, но одно из обновлений теряется.

### **Пример:**
  1. Транзакция A читает значение `balance = 100`.
  2. Транзакция B также читает значение `balance = 100`.
  3. Транзакция A увеличивает `balance` на 50 и фиксирует (`COMMIT`).
  4. Транзакция B увеличивает `balance` на 30 и фиксирует (`COMMIT`), перезаписывая результат транзакции A.

**Итог:** `balance = 130`, хотя правильное значение должно быть 180.

### **Решение:**
Уровень изоляции **`REPEATABLE READ`** или механизмы блокировок предотвращают потерю обновлений.

## Аномалия сериализации
Результат выполнения транзакций отличается от результатов их последовательного выполнения.

### **Пример:**
  - Транзакция A вычисляет сумму всех заказов.
  - Транзакция B добавляет новый заказ.
  - Итоговая сумма не соответствует реальному состоянию данных.

### **Решение:**
Уровень изоляции **`SERIALIZABLE`** предотвращает эту проблему.

# Резюме последствий по уровням изоляции

| Проблема               | READ UNCOMMITTED | READ COMMITTED | REPEATABLE READ | SERIALIZABLE |
|------------------------|------------------|----------------|-----------------|--------------|
| Грязное чтение         | ✅               | ❌             | ❌              | ❌           |
| Неповторяемое чтение   | ✅               | ✅             | ❌              | ❌           |
| Фантомное чтение       | ✅               | ✅             | ✅              | ❌           |
| Потеря обновлений      | ✅               | ✅             | ❌              | ❌           |
| Аномалия сериализации  | ✅               | ✅             | ✅              | ❌           |


# Как выбрать подходящий уровень изоляции
### Committed Read (по умолчанию)
   - Хорош для большинства OLTP-приложений, где важна скорость и допустима небольшая вероятность некорректных данных.
### Repeatable Read
   - Подходит для аналитических операций, где критична консистентность данных в рамках транзакции.
### Serializable
   - Используйте, если требуется максимальная изоляция и консистентность, но будьте готовы к снижению производительности и возможным откатам транзакций.
### Uncommitted Read
   - Используется крайне редко, только если требуется максимально быстрое выполнение запросов, и некорректные данные не являются критичными.
