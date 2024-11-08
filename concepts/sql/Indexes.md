## List of content
- [Что такое индекс ?](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#что-такое-индекс-)
- [Плюсы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#плюсы)
  - [Ускорение запросов](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#ускорение-запросов)
  - [Покрытие запросов](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#покрытие-запросов)
  - [Поддержка ограничений](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#поддержка-ограничений)
- [Накладные расходы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#накладные-расходы)
  - [Влияние на производительность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#влияние-на-производительность)
  - [Блокировка таблицы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#блокировка-таблицы)
  - [Дополнительное использование дискового пространства](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#дополнительное-использование-дискового-пространства)
  - [Необходимость технического обслуживания](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#необходимость-технического-обслуживания)
- [Типы индексов](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#типы-индексов)
  - [Cluster](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#cluster)
  - [Non-Cluster](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#non-cluster)
  - [Unique](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#unique)
  - [Composite](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#composite)
  - [Covering](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#covering)
- [Реализация индексов](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#реализации-индекса)
  - [B-Tree](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#b-tree)
  - [Hash](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#hash)
  - [GIN](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#gin)
  - [GiST](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#gist)
  - [SP-GiST](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#sp-gist)
  - [BRIN](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#brin)
- [Ошибки](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#ошибки)
  - [Низкая селективность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#низкая-селективность)
  - [Неиспользуемые индексы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#неиспользуемые-индексы)
  - [Высокие накладные расходы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#высокие-накладные-расходы)
- [Когда индексы не работают ?](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#когда-индексы-не-работают-)
  - [Использование вычисляемых выражений](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#использование-вычисляемых-выражений)
  - [Обработка большого количества записей](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#обработка-большого-количества-записей)
  - [Агрегатные функции](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#агрегатные-функции)
  - [Логические операторы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md#логические-операторы)

## Что такое индекс ?
`Индекс` — это служебная структура данных, которая позволяет ускорить операции поиска, сортировки и фильтрации данных в реляционных базах данных. Индексы создаются для одного или нескольких столбцов таблицы, с целью `ускорения выполнения запросов к базе данных`

## Плюсы
### Ускорение запросов
Индексы значительно ускоряют выполнение запросов, особенно для операций равенства, сравнений и сортировки данных.

```sql
SELECT *
FROM employees
WHERE department = 'HR';
```
Индекс на столбце department ускорит выполнение этого запроса.

### Покрытие запросов
В некоторых случаях индексы могут содержать все данные, необходимые для выполнения запроса, что позволяет избежать чтения самих строк таблицы (так называемый `Покрывающий индекс`).

```sql
SELECT
  name,
  age
FROM
  employees
WHERE department = 'IT';
```
Если индекс покрывает столбцы name, age и department, то чтение строк таблицы не потребуется.

### Поддержка ограничений
Индексы могут использоваться для реализации ограничений на уникальность данных (UNIQUE), а также для обеспечения ссылочной целостности (FOREIGN KEY)

## Накладные расходы

### Влияние на производительность
Добавление индексов замедляет операции вставки, обновления и удаления, так как индекс должен быть обновлен при каждой модификации данных. При создании индексов необходимо учитывать характер нагрузки на таблицу, особенно если часто выполняются операции записи. Например, при OLTP нагрузке чтение данных значительно преобладает над записью (80% чтения и 20% записи), что оправдывает использование индексов.

### Блокировка таблицы
Добавление индекса блокирует таблицу, что может негативно сказаться на производительности, особенно в высоконагруженных системах

### Дополнительное использование дискового пространства
Индексы требуют значительного объема дискового пространства для хранения. Обычно объем индексов составляет около половины размера таблицы. Если размер индексов превышает размер таблицы, это может указывать на необходимость оптимизации

### Необходимость технического обслуживания
Со временем индексы могут фрагментироваться и требовать пересоздания для поддержания эффективности. В некоторых системах управления базами данных (СУБД) это может происходить автоматически, однако в других случаях требуется ручное вмешательство.

## Типы индексов
### Cluster
- Сортирует и физически хранит таблицу в определенном порядке
- Только 1 кластерный индекс
- Эффективен для поиска по диапозону

### Non-Cluster
- Хранится отдельно от данных таблицы
- Таблица может иметь несколько индексов
- Эффективен для поиска по конкретным значениям

### Unique
- Гарантирует уникальность значений

```sql
CREATE UNIQUE INDEX idx_user ON test.user USING BTREE (id);
```

### Composite
- Состоит из нескольких столбцов
- Эффективен для поиска по нескольким столбцам

### Covering
- Копирует используемые в запросе неключевые значения в сам индекс

```sql
CREATE INDEX idx_example ON table_name (column1) INCLUDE (column2);
```

#### Преимущества:
  - Значительное улучшение производительности запросов, так как нет необходимости обращаться к основной таблице
  - Уменьшение числа обращений к диску, особенно для часто используемых запросов с выборкой нескольких колонок
#### Недостатки:
  - Покрывающие индексы могут занимать больше места в памяти, особенно если в них включены несколько дополнительных колонок.
  - Увеличение времени на операции вставки, обновления и удаления, так как индекс требует обновления при изменениях данных.

#### Покрывающие индексы стоит использовать в следующих случаях:
- Для оптимизации часто выполняемых SELECT-запросов, которые выбирают несколько колонок.
- Когда необходимо минимизировать количество обращений к диску, чтобы ускорить выполнение запросов.
- Для OLAP, где важно быстрое чтение данных без необходимости частых обновлений.

## Реализации индекса
### B-Tree
Широко применяются для ускорения операций поиска, сортировки и диапазонных запросов
- Основан на работе ```B-Tree``` дерева.
- Подходит для операций сравнения (`<`, `>`, `BETWEEN`), равенства (`=`) и сортировки.
- Хорошо оптимизирован для большинства операций чтения и поиска.
- Покрывает до 90% задач по индексации в типичных приложениях.
- Не рекомендуется для данных с высокой степенью повторения, так как эффективность индекса в таких случаях может снижаться
  
Создание простого B-Tree индекса
```sql
CREATE INDEX idx_user ON test.user (id);
```

### Hash
Хорошо подходят для поиска по точным значениям, но неэффективны для диапазонных запросов

### GIN

### GiST

### SP-GiST

### BRIN

## Ошибки
### Низкая селективность

### Неиспользуемые индексы

### Высокие накладные расходы

## Когда индексы не работают ?
### Использование вычисляемых выражений

### Обработка большого количества записей

### Агрегатные функции

### Логические операторы


