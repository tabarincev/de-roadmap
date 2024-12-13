## List of content
- [Hash Join](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#hash-join)
  - [Сложность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#сложность)
  - [Визуализация](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#визуализация)
- [Sort Merge Join](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#sort-merge-join)
  - [Сложность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#сложность-1)
  - [Визуализация](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#визуализация-1)
- [Nested Loop](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#nested-loop)
  - [Сложность](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#сложность-2)
  - [Визуализация](https://github.com/tabarincev/de-roadmap/blob/main/concepts/sql/PhysicalJoins.md#визуализация-2)

## Hash Join
Экви-джоин строго по равенству большой и маленькой таблицы. Маленькая помещается в память, ключи обеих таблиц хэшируются, один раз проходим по большой таблице и один раз по маленькой.
### Сложность
Время: ```O(m + n)```

Память: ```O(n)```
### Визуализация
https://bertwagner.com/posts/hash-match-join-internals/

## Sort Merge Join
Экви-джоин двух больших таблиц, которые не помещаются в память. Сортируем по ключу и проходимся "замочком", состёгивая две таблицы вместе.
### Сложность
Если сортировка проводится за ```O(nlog(n))```

Время: ```O(nlog(n) + mlog(m) + n + m) -> O(n + m)``` схлопываются как незначительные, получаем ```O(nlog(n)) + m*log(m))```. В заранее отсортированных массивах ```O(m + n)```

Память: ```O(1)```
### Визуализация
https://bertwagner.com/posts/visualizing-merge-join-internals-and-understanding-their-implications/

## Nested Loop
Все остальные джоины ```a.id >= b.id, a.id like '%word%' и прочие !=```, каждое значение левой таблицы сопоставляем со значением с правой таблицы (аналог ```CROSS JOIN```)
### Сложность
Время: ```O(n * m)```

Память ```O(1)```

### Визуализация
https://bertwagner.com/posts/visualizing-nested-loops-joins-and-understanding-their-implications/
