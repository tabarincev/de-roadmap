# List of content

- [DAG]()

# DAG
> `DAG` - это модель, которая инкапсулирует все необходимое для выполнения pipeline

- `DIRECTED` - есть направление в графе для каждого узла
- `ACYCLIC` - каждый узел не может создавать данные, которые будут ссылаться на самих себя
- `GRAPH` - модель для представления объектов и связей между ними через узлы и вершины

## Некоторые атрибуты DAG:
- `Schedule`: When the workflow should run.
- `Tasks`: tasks are discrete units of work that are run on workers.
- `Task Dependencies`: The order and conditions under which tasks execute.
- `Callbacks`: Actions to take when the entire workflow completes.
- `Additional Parameters`: And many other operational details

## Пример DAG в UI

![UI](https://airflow.apache.org/docs/apache-airflow/stable/_images/basic_dag.png)

> Он определяет четыре задачи - `A`, `B`, `C` и `D` - и диктует порядок, в котором они должны выполняться, и какие задачи зависят от других. Он также скажет, как часто производить запуск.

> Сам DAG не отвечает за то, что происходит внутри задач - он просто следит за порядком их запуска, сколько раз повторять их, есть ли у них тайм-ауты и так далее

## Инициализация DAG
Есть возмодность реализовать `DAG` тремя способами:
### Оператор `with`
```python
import datetime

from airflow.sdk import DAG
from airflow.providers.standard.operators.empty import EmptyOperator

with DAG(
    dag_id="my_dag_name",
    start_date=datetime.datetime(2021, 1, 1),
    schedule="@daily",
):
    EmptyOperator(task_id="task")
```
### Стандартный конструктор
```python
import datetime

from airflow.sdk import DAG
from airflow.providers.standard.operators.empty import EmptyOperator

my_dag = DAG(
    dag_id="my_dag_name",
    start_date=datetime.datetime(2021, 1, 1),
    schedule="@daily",
)
EmptyOperator(task_id="task", dag=my_dag)
```
### Декоратор `@dag`
```python
import datetime

from airflow.sdk import dag
from airflow.providers.standard.operators.empty import EmptyOperator


@dag(start_date=datetime.datetime(2021, 1, 1), schedule="@daily")
def generate_dag():
    EmptyOperator(task_id="task")


generate_dag()
```
## Зависимости между tasks
> `Task/Operator` обычно не один - у него есть зависимости от других задач (те, которые выше него - `upstream`), а другие задачи зависят от него (те, которые ниже него - `downstream`). Объявление этих зависимостей между задачами - это то, что составляет структуру `DAG`.

### Операторы `>>` и `<<`
```python
first_task >> [second_task, third_task]
third_task << fourth_task
```

### Операторы `set_upstream` и `set_downstream`
```python
first_task.set_downstream([second_task, third_task])
third_task.set_upstream(fourth_task)
```

### Оператор `cross_downstream`
```python
from airflow.sdk import cross_downstream

# Replaces
# [op1, op2] >> op3
# [op1, op2] >> op4
cross_downstream([op1, op2], [op3, op4])
```

### Оператор `chain`
```python
from airflow.sdk import chain

# Replaces op1 >> op2 >> op3 >> op4
chain(op1, op2, op3, op4)

# You can also do it dynamically
chain(*[EmptyOperator(task_id=f"op{i}") for i in range(1, 6)])
```

## Запуск DAG
> Возможен запуск двумя способами
- Ручной триггер или через REST API
- Запуск по расписанию

DAG не требуют расписания, но очень часто его определяют. Вы определяете его с помощью аргумента расписания, вот так:

```python
with DAG("my_daily_dag", schedule="0 0 * * *"):
    ...

with DAG("my_one_time_dag", schedule="@once"):
    ...

with DAG("my_continuous_dag", schedule="@continuous"):
    ...
```

[Ссылка на документацию по работе с `CRON`](https://airflow.apache.org/docs/apache-airflow/stable/authoring-and-scheduling/cron.html)

### Разница между `logical_date` и `execution_date`

## Задаем `default_args`

```python
import pendulum

with DAG(
    dag_id="my_dag",
    start_date=pendulum.datetime(2016, 1, 1),
    schedule="@daily",
    default_args={"retries": 2},
):
    op = BashOperator(task_id="hello_world", bash_command="Hello World!")
    print(op.retries)  # 2
```

### Полезные параметры

| Параметр | Что делает ?|
| :--------- | :------ |
| `owner` | Обозначает владельца `DAG` | 
| `depends_on_past` | Если `True`, задача будет выполняться только в том случае, если предыдущий `DagRun` с этой задачей был успешным (По умолчанию - `False`) |
| `start_date` | Указывает дату, когда `DAG` должен начать выполнение |
| `email_on_failure/retry` |  Если True, Airflow отправит уведомления по электронной почте о сбоях или повторных событиях |
| `retries` | Количество попыток, когда `FAILED` задача должна быть повторена, прежде чем она будет помечена как `FAILED` |
| `retry_delay` |  Определяет временной промежуток между `retries` |
| `execution_timeout` |  Указывает максимально допустимое время выполнения для `task` -  гарантирует, что задача не будет работать бесконечно |
| `schedule_interval` |  Определяет дату запуска DAG - как часто необходимо запускать, обычно в `CRON` формате - `0 12 * * *` |
| `catchup` | Определяет, должны ли быть выполнены прошлые запуски DAG, когда DAG включен после отсутствия запланированных запусков. По умолчанию значение True, но установка в False предотвращает заполнение пропущенных запусков |

## Control Flow

- Branching - select which Task to move onto based on a condition
- Trigger Rules - set the conditions under which a Dag will run a task
- Setup and Teardown - define setup and teardown relationships
- Latest Only - a special form of branching that only runs on Dags running against the present
- Depends On Past - tasks can depend on themselves from a previous run

## TaskGroup

## Зависимости DAG
- triggering - TriggerDagRunOperator
- waiting - ExternalTaskSensor

  
