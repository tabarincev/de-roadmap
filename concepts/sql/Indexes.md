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

# Что такое индекс ?
`Индекс` — это служебная структура данных, которая позволяет ускорить операции поиска, сортировки и фильтрации данных в реляционных базах данных. Индексы создаются для одного или нескольких столбцов таблицы, с целью `ускорения выполнения запросов к базе данных`

# Плюсы
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
Индексы могут использоваться для реализации ограничений на уникальность данных (`UNIQUE`), а также для обеспечения ссылочной целостности (`FOREIGN KEY`)

# Накладные расходы

### Влияние на производительность
Добавление индексов замедляет операции вставки, обновления и удаления, так как индекс должен быть обновлен при каждой модификации данных. При создании индексов необходимо учитывать характер нагрузки на таблицу, особенно если часто выполняются операции записи. Например, при `OLTP` нагрузке чтение данных значительно преобладает над записью (80% чтения и 20% записи), что оправдывает использование индексов.

### Блокировка таблицы
Добавление индекса блокирует таблицу, что может негативно сказаться на производительности, особенно в высоконагруженных системах

### Дополнительное использование дискового пространства
Индексы требуют значительного объема дискового пространства для хранения. Обычно объем индексов составляет около половины размера таблицы. Если размер индексов превышает размер таблицы, это может указывать на необходимость оптимизации

### Необходимость технического обслуживания
Со временем индексы могут фрагментироваться и требовать пересоздания для поддержания эффективности. В некоторых системах управления базами данных (СУБД) это может происходить автоматически, однако в других случаях требуется ручное вмешательство.

# Типы индексов
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
- Для оптимизации часто выполняемых `SELECT` запросов, которые выбирают несколько колонок.
- Когда необходимо минимизировать количество обращений к диску, чтобы ускорить выполнение запросов.
- Для `OLAP`, где важно быстрое чтение данных без необходимости частых обновлений.

# Реализации индекса
### B-Tree 
`B-tree (Balanced Tree)`
- Основан на работе ```B-Tree``` дерева.
- Подходит для операций сравнения (`<`, `>`, `BETWEEN`), равенства (`=`) и сортировки.
- Хорошо оптимизирован для большинства операций чтения и поиска.
- Покрывает до 90% задач по индексации в типичных приложениях.
- Не рекомендуется для данных с высокой степенью повторения, так как эффективность индекса в таких случаях может снижаться
  
Создание B-Tree индекса
```sql
CREATE INDEX idx_column_name ON table_name(column_name);
```

### Hash
`Hash`
-	Предназначен для операций равенства (=).
-	Менее универсален, чем `B-Tree, но иногда быстрее для точного сравнения.

Создание Hash индекса
```sql
CREATE INDEX idx_column_hash ON table_name USING HASH(column_name);
```

### GIN
`GIN (Generalized Inverted Index)` 
- Применяется для поиска по массивам, `JSONB`, полям типа `tsvector`.
- Эффективен для поиска совпадений по множеству значений.

Создание GIN индекса
```sql
CREATE INDEX idx_column_gin ON table_name USING GIN(column_name);
```

### GiST
`GiST (Generalized Search Tree)`
- Подходит для поиска по диапазонам, географическим данным, иерархиям.
- Часто используется с геометрическими данными.

Создание GiST индекса 
```sql
CREATE INDEX idx_column_gist ON table_name USING GiST(column_name);
```

### SP-GiST
`SP-GiST (Space-Partitioned Generalized Search Tree)`
- Поиск по географическим или пространственным данным.
- Работа со строками с общей структурой (например, поиск по префиксам).
- Иерархические данные (например, деревья, графы).
- Работа с распределенными или разреженными значениями.

Создание SP-GiST индекса
```sql
CREATE INDEX idx_prefix ON table_name USING SPGIST(column_name);
```

### BRIN
`BRIN (Block Range Index)`
- Используется для больших таблиц с упорядоченными данными.
- Хранит информацию о блоках данных, а не об отдельных строках.
- Идеален для столбцов с коррелированными значениями (например, временные метки).

Создание BRIN индекса
```sql
CREATE INDEX idx_column_brin ON table_name USING BRIN(column_name);
```

# Ошибки
### Низкая селективность
Индексы плохо работают на столбцах с низкой селективностью (например, на поле `is_active`, где 99% записей имеют значение `TRUE`).

**Решение:**
- Избегать индексации таких столбцов.
- Рассмотреть частичный индекс, если значения распределены неравномерно:
  
### Неиспользуемые индексы
Если запрос возвращает значительную часть строк из таблицы, `PostgreSQL` предпочтет полное сканирование таблицы (`Seq Scan`), поскольку затраты на чтение индекса и последующее чтение строк превышают выгоду.

**Решение:**
- Подумать о необходимости индекса перед его созданием


## Когда индексы не работают ?
### Операторы не поддерживаются типом индекса
-	`B-Tree` поддерживает только сравнение (`=`, `<`, `>`, и т. д.).
-	`Hash` работает только с оператором равенства (`=`).
-	Для поиска по массивам, `JSONB` или геометрическим данным необходимо использовать `GIN`, `GiST` или `SP-GiST`.

### Маленькие таблицы
На небольших таблицах `PostgreSQL` часто выбирает полное сканирование таблицы, так как это быстрее, чем доступ через индекс. Построение и использование индекса в таких случаях может только замедлить выполнение запроса.

### Агрегатные функции
Индексы не применяются для агрегатных функций, таких как `COUNT()`, `AVG()`, если они используются без фильтрации.

### Поиск с LIKE и ведущими символами %
Индексы не используются, если шаблон поиска начинается с `%`, поскольку база данных не может эффективно определить диапазон значений.

**Решение:**
- Использовать полнотекстовый поиск (`GIN` индекс с `to_tsvector`) для подобных операций.
