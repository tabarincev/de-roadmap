## List of content
- Что такое шардирование ?
- Способы
  - Средствами БД
  - Надстройками к БД
  - Клиентскими средствами
- Метод работы
  
## Что такое шардирование ?
https://planetscale.com/blog/database-sharding
Это разделение хранилища на несколько независимых частей (шардов). Шардирование — это разновидность партиционирования. Отличие в том, что партиционирование подразумевает разделение данных внутри одной БД, а шардирование распределяет их по разным экземплярам БД. 
Шардирование помогает оптимизировать хранение данных приложения за счёт их распределения между инсталляциями БД (которые находятся на разных железках), что улучшает отзывчивость сервиса, так как размер данных в целом на каждом инстансе станет меньше.

## Способы шардирования
Осуществить шардирование можно несколькими способами:
### Средствами БД
Некоторые базы — MongoDB, Elasticsearch, ClickHouse и другие — умеют самостоятельно распределять данные между своими экземплярами, для этого достаточно настроить конфигурацию. На мой взгляд, это лучший вариант.
### Надстройками к БД
Самый спорный способ — применение надстроек, которые выполняют шардирование, например Vitess или Citus, поскольку при этом есть риск потери данных и производительности.
### Клиентскими средствами
В этом случае экземпляры БД даже не подозревают о существовании друг друга, шардированием управляет стороннее приложение — со всеми вытекающими рисками.

## Метод работы
Выбираем ключ для распределения данных (это может быть идентификатор, временная метка или хеш записи) и в соответствии с ним записываем информацию в нужный шард. Как правило, ключи стараются выбирать так, чтобы данные были равномерно распределены по шардам. Сделать это не сложно — достаточно ориентироваться на текущее содержимое БД. 
Важно учитывать для чего вы делаете шардирование. В случае если требуется распределить нагрузку на запись, необходимо подобрать такой ключ, который обеспечит равномерное распределение запросов между инстансами. Нельзя забывать и о «горячих» данных, запросы к которым происходят чаще, из-за чего нагрузка на шарды оказывается неравномерной. Для этого можно добавить в приложение метрику, показывающую, сколько раз в какой шард будут попадать данные по конкретному ключу. 
