1. Основные концепции и архитектура Spark
Architecture
Spark Context
Spark Cluster on YARN vs k8s
Cluster vs Client mode
Driver vs Executor
Spark Connect
PySpark API
2. Управление ресурсами и конфигурация
Dynamic allocation
Spark App configuration
Graceful Shutdown
Python Environment Configuration (в PySpark)
3. Параллелизм и разбиение данных
Shuffle vs Broadcast
Partition pruning (Dynamic)
Wide vs Narrow
Repartition vs Coalesce
Data Locality
Data Skew
Bucketing vs Partitioning
4. Производительность и оптимизация
Catalyst
AQE (Adaptive Query Execution)
Spill-effect
Projection pushdown
Profiling & Debug
Pipeline examples
Python UDFs и Pandas UDFs в PySpark
PyArrow in PySpark
5. Работа с данными: API и структуры данных
RDD vs DataSet vs DataFrame
Actions vs Transformations
cache() vs persist()
take() vs collect()
DataFrame API vs RDD API (в контексте PySpark)
6. Обработка запросов и их этапы
Jobs vs Stages vs Tasks
Joins & Hints
Shared Variables & Broadcast Variables & Accumulators
Обработка и оптимизация запросов на Python (Python-centric Optimization)
7. Модели данных и оптимизация хранения
Joins & Hints
Bucketing vs Partitioning
Journaling
Storage Format Optimization (например, Parquet, ORC) в PySpark
8. Масштабируемость и устойчивость
Scalability
Testing
UDF
Vectorized UDFs с PyArrow
9. Отладка и управление памятью
Garbage collector
Profiling & Debug
Memory Management (в том числе особенности памяти в Python)
10. Особенности интеграции Python и Spark
Python Serialization & Deserialization
Py4J и взаимодействие JVM-Python
Integration with Pandas and NumPy
Data Locality в контексте PySpark
11. Особые сценарии и тестирование
Data Locality
Testing
Graceful Shutdown
Unit Testing and Mocking in PySpark
Dependency Management (работа с виртуальными окружениями и библиотеками в PySpark)
12. Особенности настройки и оптимизации для больших данных
Python GIL и многопоточность в контексте PySpark
Работа с большими наборами данных в Pandas-on-Spark
Оптимизация Python UDFs для минимизации расходов на производительность