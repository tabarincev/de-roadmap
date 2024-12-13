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
 
## Что такое транзакция ?
В SQL транзакцией является последовательность одного или более операторов SQL, которые выполняются как единая единица работы. Транзакции используются для гарантии, что операции с базой данных выполняются согласованным и надежным образом, поддерживающим целостность данных, хранящихся в базе данных.

## Операторы
### BEGIN
### COMMIT
### ROLLBACK
### SAVEPOINT

## ACID
### Atomicity — Атомарность
### Consistency — Согласованность
### Isolation — Изолированность
### Durability — Надёжность

## Уровни изоляции транзакций
### Uncommitted Read (UR)
### Committed Read (CR)
### Repeatable Read (RR)
### Serializable Read (SR)

## Последствия отсутствия уровня изоляции
### Потерянное обновление
### Грязное чтение
### Неповторяющееся чтение
### Фантомное чтение
