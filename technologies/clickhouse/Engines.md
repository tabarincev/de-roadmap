## Виртуальные столбцы
Виртуальный столбец — это неотъемлемый атрибут движка таблиц, определенный в исходном коде движка.
Виртуальные столбцы не надо указывать в запросе CREATE TABLE и они не отображаются в результатах запросов SHOW CREATE TABLE и DESCRIBE TABLE. Также виртуальные столбцы доступны только для чтения, поэтому вы не можете вставлять в них данные.
Чтобы получить данные из виртуального столбца, необходимо указать его название в запросе SELECT. SELECT * не отображает данные из виртуальных столбцов.
При создании таблицы со столбцом, имя которого совпадает с именем одного из виртуальных столбцов таблицы, виртуальный столбец становится недоступным. Не делайте так. Чтобы помочь избежать конфликтов, имена виртуальных столбцов обычно предваряются подчеркиванием.

## Table engines
- #### MergeTree
  - MergeTree
  - ReplacingMergeTree
  - SummingMergeTree
  - AggregatingMergeTree
  - CollapsingMergeTree
  - VersionedCollapsingMergeTree
  - GraphiteMergeTree
- #### Integration
  - Kafka
  - MySQL
  - ODBC
  - JDBC
  - S3
  - MongoDB
  - HDFS
  - EmbeddedRocksDB
  - RabbitMQ
  - PostgreSQL
- #### Special
  - Distributed
  - MaterializedView
  - Dictionary
  - Merge
  - File
  - Null
  - Set
  - Join
  - URL
  - View
  - Memory
  - Buffer



## Database engines
- 
