# Data Enginner Roadmap 2024

## Concepts 
#### [Data Architecture](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md)
- [Data Lake](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)
- [LakeHouse](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/lakehouse.md)
- Streamhouse (https://bigdataschool.ru/blog/news/flink/what-is-streamhouse-on-apache-flink-and-paimon.html)
- [Data Warehouse](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/data_warehouse.md)
- [Data Mesh](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)
- [Lambda](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/lambda.md) vs [Kappa](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/kappa.md)
- [Kimball](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/kimball.md) vs [Inmon](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/inmon.md) (https://docs.getdbt.com/blog/kimball-dimensional-model)
- [Star](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/star.md) vs [Snowflake](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/snowflake.md)

#### [Data Governance](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataGovernance.md)
- [Principals](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_governance/principals.md)
- [Tools](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_governance/tools.md)
  
#### [Data Pipeline](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataPipeline.md)
- [CDC](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_pipeline/cdc.md)
- [ELT](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_pipeline/elt.md)
- [ETL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_pipeline/etl.md)
- Hot vs Warm vs Cold data
- [SCD](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_pipeline/scd.md)
  
#### [Data Modeling](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataModeling.md)
- [Data Vault](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_modeling/data_vault.md) https://search.app?link=https%3A%2F%2Fhabr.com%2Fru%2Fcompanies%2Fcinimex%2Farticles%2F857084%2F&utm_campaign=aga&utm_source=agsadl1%2Cagsadl3%2Csh%2Fx%2Fgs%2Fm2%2F4
- [Anchor Modeling](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_modeling/anchor.md)
- [HnNf](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_modeling/hnnf.md)

#### [Data Processing](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Processing.md)
- Batch vs Stream vs Micro-Batch
- OLTP vs OLAP vs HTAP

#### [Data Quality](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataQuality.md)
- Dimensions
- Tools

#### [SQL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/SQL.md)

https://www.youtube.com/watch?v=DJ5u5HrbcMk&list=PLSE8ODhjZXjbj8BMuIrRcacnQh20hmY9g&t=495
- [Типы баз данных](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md)
  - [Реляционные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#реляционные)
  - [Нереляционные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#нереляционные)
    - [Документоориентированные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#документоориентированные)
    - [Графовые](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#графовые)
    - [Ключ-значение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#ключ-значение)
    - [Колоночные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#колоночные)
  - [Сравнение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#сравнение)
- [Indexes](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md)
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
- [Транзакции](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Transactions.md)
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
 
- [Clustering](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md)
- Sharding & Replication (https://habr.com/ru/companies/ozontech/articles/705912/)
- Table vs View vs Materialized View
- Нормальные формы (https://habr.com/ru/articles/254773/)
  - Термины
  - 1NF - 6NF
  - Дополнительные NF
- Relations
  - One-to-One
  - One-to-Many
  - Many-to-Many
  - self-reference
- Constraints
- How database physically stores data ?
- DDL vs DML vs DCL vs TCL
- RBAC
- Query Engine (https://howqueryengineswork.com/00-introduction.html)
- Physical joins (Nested loop, Merge sort join, Hash join) https://www.youtube.com/watch?v=pJWCwfv983Q \
  - Hash Join \ 
экви-джоин (строго по равенству) большой и маленькой таблицы. Маленькая помещается в память, ключи обеих таблиц хэшируются, 
один раз проходим по большой таблице и один раз по маленькой. 
O(m+n) по времени + O(n) по памяти
Визуализация - https://bertwagner.com/posts/hash-match-join-internals/

  - Sort Merge Join \
экви-джоин двух больших таблиц, которые не помещаются в память. Сортируем по ключу и проходимся "замочком", состёгивая две таблицы вместе. \
Если сортировка проводится за O(n*log(n)), то O (n*log(n) + m*log(m) + n + m) -> (n+m) схлопываются как незначительные, получаем O(n*log(n)) + m*log(m)). 
В заранее отсортированных массивах O(m+n)
Визуализация - https://bertwagner.com/posts/visualizing-merge-join-internals-and-understanding-their-implications/

  - Nested loop \
все остальные джоины ( a.id >= b.id, a.id like '%word%' и прочие != ), каждое значение левой таблицы сопоставляем со значением с правой таблицы (аналог CROSS JOIN), \
сложность O(n*m).
Визуализация - https://bertwagner.com/posts/visualizing-nested-loops-joins-and-understanding-their-implications/

- Execution plan optimization
  
## System Design
- https://divyumrastogi.gitbooks.io/system-design/content/the_system_design_primer/anki_flashcards.html
- https://youtu.be/bUHFg8CZFws
- https://youtu.be/ZgdS0EUmn70?si=DMh6I_hoKulUPXK9
- https://habr.com/ru/companies/yandex/articles/564132/
- https://habr.com/ru/articles/850888/

  
## Modern Data Stack
- [Dbt + Trino + Iceberg](https://github.com/tabarincev/modern-data-pipeline)

## Technologies
<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/183423507-c056a6f9-1ba8-4312-a350-19bcbc5a8697.png" alt="Python icon">

#### Python - https://github.com/yakimka/python_interview_questions/tree/master

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/192158606-7c2ef6bd-6e04-47cf-b5bc-da2797cb5bda.png" alt="Bash icon">

#### Linux

- Navigation
- Working with files
- Text processing
- Process managing
- Users and groups
- Filesystem
- Network
- Utils
- SSH

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/117207330-263ba280-adf4-11eb-9b97-0ac5b40bc3be.png" alt="Docker icon">

#### Docker
(https://kodekloud.com/courses/docker-for-the-absolute-beginner/)
- Basics
- Conteiner vs VM
- Build & Run conteiners
- CLI
- Deploy

#### GreenPlum
https://greenplum.org/tutorials/

#### ClickHouse
- ACID
- Rebalancing & Profiling queries
- Caching
- Views Types
- Dictionaries
- Engines
- Parts & Partitions (https://chistadata.com/parts-and-partitions-in-clickhouse-part-i/)
- Indexes
- Joins 
- Data formats
- Blocks
- Mutations
- Monitoring
- System tables

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/117208740-bfb78400-adf5-11eb-97bb-09072b6bedfc.png" alt="PostgreSQL icon">

#### PostgreSQL

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/184357834-eba1eee1-6074-4b9c-8ed3-5373868096cc.png" alt="Spark icon">

#### Spark 
(https://quizlet.com/964581753/spark-flash-cards/?i=66jmdb&x=1jqt)
- Architecture
- Shuffle vs Broadcast
- Actions vs Transformations
- Wide vs Narrow
- RDD vs DataSet vs DataFrame
- Partition pruning (Dynamic)
- Projection pushdown
- Spill-effect
- Dynamic allocation
- Catalyst
- Spark Connect
- Spark Context
- Driver vs Executor
- Jobs vs Stages vs Tasks
- Repartition vs Coalesce
- Shared Variables & Broadcast Variables & Accumulators
- Joins & Hints
- Journaling
- Cluster vs Client mode
- Profiling & Debug
- AQE
- Pipeline examples
- Spark Cluster on YARN vs k8s
- take() vs collect()
- Garbage collector
- Spark App configuration
- PyArrow in PySpark
- Data Locality
- Data Skew
- Bucketing vs Paritioning
- Scalability
- UDF
- Testing
- cache() vs persist()
- Graceful Shutdown

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/192107004-2d2fff80-d207-4916-8a3e-130fee5ee495.png" alt="Kafka icon">

#### Kafka
- Producer, Consumer, Topic, Consumer group
- Replication
- Partition, Offset
- Kafka vs Flink vs Spark Streaming

<img align="left" width="25" height="25" src="https://user-images.githubusercontent.com/25181517/192108372-f71d70ac-7ae6-4c0d-8395-51d8870c2ef0.png" alt="Git icon">

#### Git

#### Airflow (https://quizlet.com/de/966067770/airflow-de-flash-cards/)
- Architecture
- DAG
- Operators
- Sensors
- XCOM
- TaskFlow
- Jinja templates
- backfill & catchup
- Pool vs Queue
- Connections vs Hooks

<img align="left" width="25" height="25" src="https://github.com/marwin1991/profile-technology-icons/assets/136815194/c7f2fa08-bb92-4898-a73e-b206be6bd573" alt="Hadoop icon">

#### Hadoop (https://youtu.be/N6TmDNexxGI?si=FOKcoRbKQ87qXjGz)
- Architecture
- Formats (ORC, AVRO, Parquet, Hudi, Iceberg, Delta Lake)
- MapReduce

#### DBT 
- https://github.com/dbt-labs/dbt-project-maturity/tree/main

#### k8s


#### Resources
https://mehulkansal.hashnode.dev
