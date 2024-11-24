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
Компонент, который можно использовать совместно со Spark Core, у него есть API для языков Scala, Java, Python и R и основных SQL-запросов.
Spark SQL описывает интерфейс для частично структурированного типа данных
DataFrames частично структурированную типизированную версию RDD. Spark SQL имеет значение для производительности Spark, и многое из выполняемого с помощью Spark Core можно сделать
и благодаря Spark SQL

### Spark Streaming
Использует планировщик Spark Core для потоковой аналитики
и мини-пакетов (micro-batch) данных. Для Spark Streaming релевантны некоторые специфические соображения, например относительно размеров окон для пакетов

### Spark MLlib
Это библиотека функций, позволяющих реализовывать алгоритмы машинного обучения в распределенном Big Data фреймворке Apache Spark. MLlib предназначена для работы с ML-моделями в кластерах и может использоваться во всех языках программирования, которые поддерживает Spark (Java, Python, Scala)

### Spark GraphX
Фреймворк для работы с графами, основанный на Spark и включающий
API для вычислений на графах. GraphX — один из наименее «зрелых» компонен-
тов Spark

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

https://habr.com/ru/companies/sberbank/articles/805285/
#### Client

#### Cluster

## Структура Spark-задания
### Job
### Stage
### Task
Этапы состоят из задач. Задача (task) — самый маленький блок иерархии выполнения, каждая задача соответствует одному локальному расчету. Все задачи одного
этапа выполняет один и тот же код, но для различных элементов данных. Одна задача не может выполняться более чем в одном исполнителе. Однако у каждого исполнителя есть динамически выделяемое количество слотов для выполнения задач, 
и он способен выполнять несколько задач параллельно в течение своего жизненного цикла. Количество задач этапа соответствует количеству секций выходного набора RDD данного этапа.
