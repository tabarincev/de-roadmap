# List of content


## Подход к решению задач
```python
users_df = (
  spark.read.table("users_table")
  .where(col("dt") == date)
  .select(..)
)

events_df = (
  spark.read.table("events_table")
  .where(col("event_type").isin("drop", "create", "put"))
  .select(..)
)

result_df = users_df.join(events_df, "user_id", "left")
```

Решение:
Во всем виноват InMemoryFileIndex - он генерирует список файлов для обработки. Проблема заключается в том что список генерируется в один поток, а NameNode часто отвечает медленно. Когда файлов немного это не является проблемой, но когда файлов много - возникают задержки. Для этого передаем задачу Listing с драйвера на отдельную джобу (Работает для сырых файлов на hdfs - ORC, JSON и тд )
Выставим параметр - spark.sql.sources.parallelDiscovery.treshold=0

Читать данные будем не из таблицы, а из директории в HDFS с множеством файлов (*), тем самым данные будут читаться параллельно. Также не забываем добавлять колонки партицирования.

Перепишем запрос

```python
users_df = spark.read.orc("dwh/ods/users/dt=2024-01-01/*")

events_df = (
  spark.read.orc("dwh/ods/events/source=drop/dt=2024-01-01/*")
  .withColumn("source", lit("drop"))
  .union(
    spark.read.orc("dwh/ods/events/source=create/dt=2024-01-01/*")
    .withColumn("source", lit("create"))
  )
  .union(
    spark.read.orc("dwh/ods/events/source=put/dt=2024-01-01/*")
    .withColumn("source", lit("put"))
  )

result = users.join(events_df, "user_id", "left")
```

Смотрим в Spark UI и видим что shuffle read 1800Gb и 800Gb, поэтому подкрутим параметр spark.sql.shuffle.partition. По дефолту 200, посчитаем необходимое количество:
Partitions = Memory / 250 (max 300)

При перекосе данных можно "посолить данные"
Смотрим обе таблицы на "перекос" по ключу
```python
statistics_df = (
  events_df
  .groupBy("user_id")
  .agg(count(lit(1)).alias("cnt")
  .orderBy(col("cnt).desc_null_last)
  .show(10)
```

При добавлении "соли" необходимо смотреть план запроса, используется ли колонка с солью (Catalyst может добавить ее после join)
Посмотреть план запроса можно в Spark UI -> SQL -> Job -> Details

