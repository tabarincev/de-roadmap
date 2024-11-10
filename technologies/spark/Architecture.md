## List of content
- [Компоненты (Spark Core)](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#компоненты)
  - [Spark SQL](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-sql)
  - [Spark GraphX](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-graphx)
  - [Spark Streaming](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-streaming)
  - [Spark MLlib](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-mllib)
- Архитектура Spark-кластера
  - Компоненты
    - Driver
      - Spark Conf
      - Spark Context
    - Worker Node
    - Executor
  - Менеджеры ресурсов (Cluster Manager)
    - YARN
    - Mesos
    - k8s
  - Режим взаимодействия
    - Client
    - Cluster
- Структура Spark-задания
  - Job
  - Stage
  - Task

## Компоненты
### Spark SQL
### Spark Streaming
### Spark MLlib
### Spark GraphX

## Архитектура Spark-кластера
Приложение Spark запускается в момент начала выполнения SparkContext. При выполнении SparkContext в рабочих
узлах (Worker Node) кластера запускается Driver и набор исполнителей (Executors). Каждый исполнитель
соответствует виртуальной машине Java (JVM), так что не способен охватывать несколько узлов, хотя в одном узле может быть несколько исполнителей
### Компоненты
#### Driver
#### Worker Node
#### Executor
![arch](https://f133fde2.rocketcdn.me/wp-content/uploads/2020/07/apache-spark-architecture.png)

### Менеджеры ресурсов
#### YARN
#### Mesos
#### k8s

### Режим взаимодействия 
#### Client

#### Cluster

## Структура Spark-задания
### Job
### Stage
### Task
