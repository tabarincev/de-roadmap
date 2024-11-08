## List of content
- [Последствия отсутствия уровня изоляции](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#последствия-отсутствия-уровня-изоляции)
  - [Потерянное обновление](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#потерянное-обновление)
  - [Грязное чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#грязное-чтение)
  - [Неповторяющееся чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#неповторяющееся-чтение)
  - [Фантомное чтение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#фантомное-чтение)
- [Уровни изоляции](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#уровни-изоляции)
  - [Uncommitted Read](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#uncommitted-read-ur)
  - [Committed Read](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#committed-read-cr)
  - [Repeatable Read](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#repeatable-read-rr)
  - [Serializable Read](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/IsolationLayers.md#serializable-read-sr)

## Последствия отсутствия уровня изоляции
Свойство Isolation в ```ACID``` гласит:
Во время выполнения транзакции другие транзакции не должны оказывать влияние на результат. Но изолированность транзакций обходится дорого, поэтому в базах данных существуют режимы, которые не полностью изолируют транзакцию от других.

Однако, это приводит к неприятным последствиям, таким как:
### Потерянное обновление
Две параллельные транзакции меняют одни и те же данные. Итоговый результат обновления предсказать невозможно.
### Грязное чтение
В результатах запроса появляются промежуточные результаты параллельной транзакции, которая ещё не завершилась
### Неповторяющееся чтение
Запрос с одними и теми же условиями даёт неодинаковые результаты в рамках транзакции.
### Фантомное чтение
В результатах повторяющегося запроса появляются и исчезают строки, которые модифицирует параллельная транзакция

## Уровни изоляции
### Uncommitted Read (UR)
Могут происходить грязные чтения, неповторяемые чтения, фантомные чтения и потерянное обновление

### Committed Read (CR)
Грязные чтения предотвращены, но могут возникать неповторяющиеся чтения, фантомные чтения и потерянное обновление

### Repeatable Read (RR)
Грязные чтения, неповторяющиеся чтения и потерянное обновление предотвращены, но могут возникать фантомные чтения

### Serializable Read (SR)
Транзакции полностью изолированы. Исключено влияние одной транзакции на другую в момент выполнения
