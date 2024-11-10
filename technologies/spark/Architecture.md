## List of content
- [Компоненты (Spark Core)](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#компоненты)
  - [Spark SQL](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-sql)
  - [Spark GraphX](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-graphx)
  - [Spark Streaming](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-streaming)
  - [Spark MLlib](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#spark-mllib)
- [Архитектура Spark-кластера](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#архитектура-spark-кластера)
  - [Компоненты](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#компоненты-1)
    - [Driver](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#driver)
      - Spark Conf
      - Spark Context
    - [Worker Node](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#worker-node)
    - [Executor](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#executor)
  - [Менеджеры ресурсов (Cluster Manager)](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#менеджеры-ресурсов)
    - YARN
    - Mesos
    - k8s
  - [Режим взаимодействия](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#режим-взаимодействия)
    - [Client](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#client)
    - [Cluster](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#cluster)
- [Структура Spark-задания](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#структура-spark-задания)
  - [Job](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#job)
  - [Stage](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#stage)
  - [Task](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Architecture.md#task)

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
