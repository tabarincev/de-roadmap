## Introduction
#### 1. Пустой DataFrame
```python
import pyspark.sql.types as T

from pyspark.sql import SparkSession

with SparkSession.builder.master("local[1]").appName("test-app").getOrCreate() as spark:
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
