# Data Enginner Roadmap 2024

## Concepts 
#### [Data Architecture](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md)
- [Data Lake](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)
- [Data Warehouse](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)
- [Data Mesh](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)
- [Lambda vs Kappa](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Architecture.md#data-lake)

#### [Data Governance](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataGovernance.md)

#### [Data Pipeline](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataPipeline.md)
- CDC
- ELT
- ETL
- Hot vs Warm vs Cold data
- SCD2
  
#### [Data Modeling](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataModeling.md)
- Data Vault 2.0
- Anchor Modeling
- HnNf

#### [Data Processing](https://github.com/tabarincev/de-roadmap/blob/main/concepts/Processing.md)
- Batch vs Stream
- OLTP vs OLAP vs HTAP

#### [Data Quality](https://github.com/tabarincev/de-roadmap/blob/main/concepts/DataQuality.md)


#### [SQL](https://github.com/tabarincev/de-roadmap/blob/main/concepts/SQL.md)
- Indexes
- Isolation levels (UR, CR, RR, SR)
- Clustering
- Sharding
- Replication
- How database physically stores data ?
- DDL vs DML vs DCL vs TCL
- RBAC
- Physical joins (Nested loop, Merge sort join, Hash join)
- Execution plan optimization
  
## System Design

## Modern Data Stack
- dbt + Trino + Iceberg

## Technologies
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

#### Docker
- Basics
- Conteiner vs VM
- Build & Run conteiners
- CLI
- Deploy

#### ClickHouse
- ACID
- Rebalancing & Profiling queries
- Caching
- Views Types
- Dictionaries
- Engines
- Parts
- Indexes
- Joins 
- Data formats
- Blocks
- Mutations
#### PostgreSQL

#### Spark
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

  
#### Kafka
- Producer, Consumer, Topic, Consumer group
- Replication
- Partition, Offset
- Kafka vs Flink vs Spark Streaming
  
#### Git

#### Airflow
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

#### Hadoop
- Architecture
- Formats (ORC, AVRO, Parquet, Hudi, Iceberg, Delta Lake)
- MapReduce
