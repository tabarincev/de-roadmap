## Типы JOIN
  #### Логические
  - INNER
  - OUTER
  - SEMI, ANTI
  - CROSS

  #### Физические
  - Shuffle Hash Join
  - Broadcast Hash Join
  - Sort Merge Join
  - Cartesian Join
  - Broadcast Nested Loop Join

## Как выбирается механизм JOIN ?
- Параметры конфигурации
- Хинты
- Размер наборов данных
- Тип JOIN
- Эквивалентные или неэквивалентные джойны
