# Data Enginner Roadmap 2024

## Concepts 

#### [Data Architecture]()
- [Kappa]()
- [Lambda]()
  
#### [Storage Design]()
- [DWH]()
  - [Kimball]()
  - [Inmon]()
  - [Snowflake]()
  - [Star]()
- [Data Lakes]()
  - [Data Lake]()
  - [Data Lakehouse]()
  - [Streamhouse]()
- [Data Mesh]()
- [Data Fabric]()

#### [LSA - Layered Scalable Architecture]()
- [DWH]()
  - [Primary Data Layer]()
  - [Core Data Layer]()
  - [Data Mart Layer]()
  - [Service Layer]()
- [Data Lake]()
  - [RAW]()
  - [Stagging]()
  - [ODS]()
  - [DDS]()
  - [DM]()

#### [Data Governance](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataGovernance.md)
- [Data Quality]()
  - [Измерения]()
  - [Инструменты]()
    - [Soda]()
    - [Great Expectations]()
- [Data Lineage]()
- [Data Catalog]()

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

#### [SQL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/SQL.md)

https://www.youtube.com/watch?v=DJ5u5HrbcMk&list=PLSE8ODhjZXjbj8BMuIrRcacnQh20hmY9g&t=495
- [Типы баз данных](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md)
  - [Реляционные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#реляционные)
    - [Реляционная модель данных](https://github.com/Max-Starling/Notes/blob/master/DataModels-Databases.md#реляционная-модель-данных)
  - [Нереляционные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#нереляционные)
    - [Документоориентированные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#документоориентированные)
    - [Графовые](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#графовые)
    - [Ключ-значение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#ключ-значение)
    - [Колоночные](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#колоночные)
  - [Сравнение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/DatabaseTypes.md#сравнение)

- [Индексы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Indexes.md)
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

- [Кластер](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md)
  - [Что такое кластер ?](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#что-такое-кластер-)
  - [Плюсы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#плюсы)
    - [High Availability](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#high-availability)
    - [Load Balancing](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#load-balancing)
    - [Scalability](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#scalability)
    - [Data Redundancy and Backup](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#data-redundancy-and-backup)
    - [Disaster Recovery](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#disaster-recovery)
  - [Типы кластеров](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#типы-кластеров)
    - [Shared-Nothing](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#shared-nothing)
    - [Shared-Disk](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#shared-disk)
    - [Shared-Everything](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#shared-everything)
    - [Replication](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#replication)
    - [Load-Balanced](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Clustering.md#load-balanced)

- [Масштабирование баз данных]()
  - [Шардирование]()
  - [Партиционирование]()
  - [Репликация]()

- [Нормальные формы]() (https://habr.com/ru/articles/254773/)
  - [Терминалогия](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#терминалогия)
    - [Атрибут](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#атрибут)
    - [Домен атрибута](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#домен-атрибута)
    - [Кортеж](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#кортеж)
    - [Отношение](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#отношение)
    - [Схема отношения](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#схема-отношения)
    - [Проекция](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#проекция)
    - [Функциональная зависимость](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#функциональная-зависимость)
    - [Нормальная форма](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#нормальная-форма)
    - [Метод нормальных форм (НФ)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#метод-нормальных-форм-нф)
    - [Цель нормализации](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#цель-нормализации)
  - [Формы](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#формы)
    - [1НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#1нф)
    - [2НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#2нф)
    - [3НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#3нф)
    - [Нормальная форма Бойса-Кодда (НФБК)](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#нормальная-форма-бойса-кодда-нфбк)
    - [4НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#4нф)
    - [5НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#5нф)
    - [6НФ](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/NormalForms.md#6нф)

- [Отношение таблиц](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Relations.md)
  - [One-to-One](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Relations.md#one-to-one)
  - [One-to-Many](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Relations.md#one-to-many)
  - [Many-to-Many](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Relations.md#many-to-many)
  - [Self-Reference](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/Relations.md#self-reference)

- [Как база данных хранит данные ?]()

- [Типы команд]()
  - [DML](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/CommandTypes.md#dml)
  - [DDL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/CommandTypes.md#ddl)
  - [DCL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/CommandTypes.md#dcl)
  - [TCL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/CommandTypes.md#tcl)

- [Контроль и разграничение доступа - RBAC]()

- [Query Engine]() (https://howqueryengineswork.com/00-introduction.html)

- [Physical joins](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md)
  https://www.youtube.com/watch?v=pJWCwfv983Q
  - [Hash Join](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#hash-join)
  - [Sort Merge Join](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#sort-merge-join)
  - [Nested Loop](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#nested-loop)
  
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
- [Что такое Docker ?]()
  - [Сравнение контейнера и виртуальной машины]()
  - [Преимущества контейнеризации]()

- [Docker]()
  - [Архитектура]()
  - [Этапы]()
  - [Хранение данных - VOLUME]()

- [Dockerfile]()
  - [Использование образов с помощью FROM]()
  - [Копирование файлов с помощью ADD И COPY]()
  - [Запуск команд с помощью RUN и CMD]()
  - [Рабочая директория WORKDIR]()
  - [Аргументы ARG]()
  - [Переменные окружения ENV]()
  - [Порты и инструкция EXPOSE]()
  - [Пример Dockerfile для Телеграм бота]()

- [Docker Compose]()
  - [Композиция контейнеров]()
  - [Сервисы]()
  - [Порядок запуска сервисов]()
  - [Порты]()
  - [Пример композиции контейнеров трёхуровнего приложения]()
  - [Переменные ENVIRONMENT и ARGS]()
  - [Передача и использование аргументов в Docker Compose]()
  - [Проверка конфигурации]()

- [Docker Swarm]()

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
- [Что такое Git ?]()
- [Как работает Git ?]()
  - [Состояния файлов]()
  - [Три области Git]()
  - [Коммит и индекс]()
  - [Ветвление]()
  - [HEAD и верхушка ветки]()
- [Основные команды Git]()
  - [merge]()
    - [Как работает merge]()
    - [Fast-forward merge]()
    - [True merge]()
    - [Конфликты при true merge и их разрешение]()
  - [rebase]()
    - [Как работает rebase]()
    - [rebase vs merge]()
    - [Другие возможности rebase и интерактивный режим]()
  - [pull и fetch]()
  - [Откат изменений с reset, checkout, revert, restore]()
    - [reset]()
      - [checkout]()
      - [revert]()
      - [restore]()
- [Версионирование и тэги]()
- [Полезные возможности Git]()
  - [Отмена последнего коммита]()
  - [Перенос коммитов из одной локальной ветки в другую]()
  - [Смена CRLF на LF одновременно для всех файлов в проекте]()
- [Git flow]()
- [SSH Github & Gitlab]()
- [Git Config]()
- [Git Bash / Git Fork]()

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

## Общее
- [ООП]()
  - [Инкапсуляция]()
  - [Наследование]()
  - [Полиморфизм]()
  - [Абстракция]()
- [Принципы]()
  - [KISS]()
  - [DRY]()
  - [SOLID]()
  - [YAGNI]()
  - [SLAP]()
- [Паттерны проектирования]()
  - [Порождающие (Creational)]()
    - [Абстрактная фабрика (Abstract factory)]()
    - [Построитель (Builder)]()
    - [Фабричный метод (Factory method)]()
    - [Прототип (Prototype)]()
    - [Одиночка (Singleton)]()
    - [Порождающие паттерны. Итог]()
  - [Структурные (Structural)]()
    - [Адаптер (Adapter)]()
    - [Мост (Bridge)]()
    - [Компоновщик (Composite)]()
    - [Декоратор (Decorator)]()
    - [Фасад (Facade)]()
    - [Приспособленец (Flyweight)]()
    - [Заместитель (Proxy)]()
    - [Структурные паттерны. Итог]()
  - [Поведенческие (Behavioral)]()
    - [Цепочка ответственности (Chain of responsobility)]()
    - [Команда (Command)]()
    - [Интерпретатор (Interpreter)]()
    - [Итератор (Iterator)]()
    - [Посредник (Mediator)]()
    - [Хранитель (Memento)]()
    - [Наблюдатель (Observer)]()
    - [Состояние (State)]()
    - [Стратегия (Strategy)]()
    - [Шаблонный метод (Template method)]()
    - [Посетитель (Visitor)]()
    - [Поведенческие паттерны. Итог]()
- [Тестирование]()
  - [Пирамида тестирования]()
  - [Mock]()
  - [Виды тестов]()
    - [Unit-тесты]()
    - [Интеграционные тесты (Integration tests)]()
    - [Функциональное тестирование]()
    - [Системный тест (System test, Service test)]()
    - [Проверка работоспособности (Smoke test, Sanity check)]()
    - [Регрессионное тестирование (Regression testing)]()
    - [Прочее]()

#### Resources
https://mehulkansal.hashnode.dev
