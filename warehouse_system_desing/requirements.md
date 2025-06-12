# List of content
- [Требования к хранилищу](https://github.com/tabarincev/de-roadmap/new/main#требования-к-хранилищу)
  - [Основные потребители](https://github.com/tabarincev/de-roadmap/new/main#1-основные-потребители)
  - [Количество потребителей](https://github.com/tabarincev/de-roadmap/new/main#2-количество-потребителей)
  - [Объем данных](https://github.com/tabarincev/de-roadmap/new/main#3-объем-данных)
  - [Необходимая частота обновления](https://github.com/tabarincev/de-roadmap/new/main#4-необходимая-частота-обновлений)
  - [Источники данных](https://github.com/tabarincev/de-roadmap/new/main#5-источники-данных)
  - [Выбор подхода (Lambda vs Kappa)](https://github.com/tabarincev/de-roadmap/new/main#6-выбор-подхода-lambda-vs-kappa)

# Требования к хранилищу
## 1. Основные потребители
- **`Аналитики и BI-специалисты`**: используют агрегированные данные для построения отчетов и дашбордов.
- **`Data Scientists и ML-инженеры`**: нуждаются в доступе к историческим, очищенным данным для построения `ML-моделей`.
- **`Бизнес-менеджеры`**: потребляют высокоуровневую аналитику.
- **`Операционные системы`**: возможно, потребуется потоковая интеграция с `CRM`, `ERP`, `веб-приложениями`.

## 2. Количество потребителей
- **`Малое (до 10)`**: достаточно `OLAP-интерфейса` и `BI-интеграции`.
- **`Среднее (10 – 100)`**: потребуется `load balancing`, `query caching`, возможна виртуализация (например, [Presto](https://prestodb.io) или [Trino](https://trino.io)).
- **`Крупное (> 100)`**: потребуется масштабирование на уровне доступа, кэширование и денормализация слоев.

## 3. Объем данных
- Общий объем хранилища
- Объем необходимый для аналитики
- Hot, Warm, Cold и Frozen данные

## 4. Необходимая частота обновлений
- **`Раз в день`**: достаточно batch-обработки с [Airflow](https://airflow.apache.org) и [dbt](https://www.getdbt.com).
- **`Каждый час/минуту`**: использовать микробатчинг c [Spark Structured Streaming](https://spark.apache.org/streaming/) или [Flink](https://flink.apache.org).
- **`Реалтайм (< 1 мин)`**: [Kafka](https://kafka.apache.org) + [Flink](https://flink.apache.org), а также [CDC](https://ru.wikipedia.org/wiki/Захват_изменения_данных) ([Debezium](https://debezium.io)).

> Также необходимо уточнить допустимый [SLA](https://ru.wikipedia.org/wiki/Соглашение_об_уровне_услуг)

## 5. Источники данных
- **`Базы данных`**: [PostgreSQL](https://www.postgresql.org), [MySQL](https://www.mysql.com) и тд.
- **`Событийные шины`**: [Kafka](https://kafka.apache.org), [Pulsar](https://pulsar.apache.org).
- **`API / Webhooks`**: [REST](https://ru.wikipedia.org/wiki/REST), [GraphQL](https://graphql.org).
- **`Файлы / Datalake`**: [CSV](https://ru.wikipedia.org/wiki/CSV), [JSON](https://www.json.org/json-en.html), [Parquet](https://parquet.apache.org), [Avro](https://avro.apache.org).

## 6. Выбор подхода (Lambda vs Kappa)
| Подход | Описание                                                                 | Когда выбирать                                                                 |
|--------|--------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| [Lambda](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/Lambda%26Kappa.md#что-такое-lambda-) | Отдельные pipeline’ы для batch и stream, объединяются в serving layer    | При необходимости истории + реалтайма                                          |
| [Kappa](https://github.com/tabarincev/de-roadmap/blob/main/concepts/data_architecture/Lambda%26Kappa.md#что-такое-kappa-)  | Только stream-обработка, batch имитируется через репроигрывание          | Когда основная логика работает в real-time и нет сложных batch-загрузок        |
