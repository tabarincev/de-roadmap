# Cookbook

- [Introduction](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#introduction)
- [Filtering rows](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#filtering-rows)
- [Array operations](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#array-operations)
- [Text processing](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#text-processing)
- [Time operations](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#time-operations)
- [Numeric operations](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#numeric-operations)
- [Dataframe joins](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#dataframe-joins)
- [Agrregating & map](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#agrregating--map)
- [Sampling](https://github.com/tabarincev/de-roadmap/blob/main/technologies/spark/Cookbook.md#sampling)

## Introduction

#### 0. Инициализация SparkSession
```python
with SparkSession.builder.master("local[1]").appName("<YOUR_APP_NAME>").getOrCreate() as spark:
  pass
```

#### 1. Пустой DataFrame
```python
import pyspark.sql.types as T

schema = T.StructType(
  [
    T.StructField("A", T.ArrayType(T.StringType()), True),
    T.StructField("B", T.ArrayType(T.StringType()), True),
  ]
)

data = []
df = spark.createDataFrame(schema=schema, data=data)
df.show()
```

#### 2. DataFrame из словаря
```python
import pyspark.sql.functions as F

dict_a = {"key1": "value1", "key2": "value2"}
values = [(k, v) for k, v in dict_a.items()]
columns = ["key", "value"]
  
df = spark.createDataFrame(values, columns)
df.show()
```


## Filtering rows

## Array operations

## Text processing

## Time operations

## Numeric operations

## Dataframe joins

## Agrregating & map

## Sampling
