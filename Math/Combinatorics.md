Комбинаторика

Moved
https://www.notion.so/f699bac1c9ac4f9f9519b96a83d38ec0

# External Links

Основы комбинаторики
Райгородский Андрей Михайлович
[https://openedu.ru/course/mipt/COMB/](https://openedu.ru/course/mipt/COMB/)

Виленкин
Виленкин комбинаторика
[https://math.ru/lib/363](https://math.ru/lib/363)


# Links

[[Combinatorial search]]


# Permutations

Перестановки
Порядок важен

https://www.notion.so/Permutations-78f05bc2ca334b1bb6e45090f19c2183

# Размещения

Размещение

[https://ru.wikipedia.org/wiki/Размещение](https://ru.wikipedia.org/wiki/%D0%A0%D0%B0%D0%B7%D0%BC%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D0%B5)

Размещения без повторений
- Похожи на перестановки, но учитывается только первые к элементов
- Порядок важен
- Количество размещений равно убывающему факториалу

Размещения без повторений
- permutations without repetition
- Partial permutation

Размещения с повторениями
- или выборка с возвращением
- Размещения с повторениями из n по k: $A^n_k = n^k$


# Сочетания

[https://ru.wikipedia.org/wiki/Сочетание](https://ru.wikipedia.org/wiki/%D0%A1%D0%BE%D1%87%D0%B5%D1%82%D0%B0%D0%BD%D0%B8%D0%B5)

Сочетание
- Размещения без повторений в которых порядок не важен
- Число способов выбрать k элементное подмножество из множества состоящего из n элементов.

Combination
https://en.wikipedia.org/wiki/Combination

Треугольник Паскаля
[https://ru.wikipedia.org/wiki/Треугольник_Паскаля](https://ru.wikipedia.org/wiki/%D0%A2%D1%80%D0%B5%D1%83%D0%B3%D0%BE%D0%BB%D1%8C%D0%BD%D0%B8%D0%BA_%D0%9F%D0%B0%D1%81%D0%BA%D0%B0%D0%BB%D1%8F)

Сочетания с повторениями
TBD

Хорошее доказательство формулы для Сочетания
- [[MIT 6.041SC. Probability Theory.]]


# Результаты

Количество подстрок в строке
- Почему это равно числу сочетаний из $n$ по 2?
- Потому что мы должны выбрать **два** индекса из $n$ индексов.
- https://leetcode.com/problems/longest-palindromic-substring/solution/

Количество подмножеств множества
- Number of subsets of a set
- $2^n$
- То чем ты пользуешься при доказательстве называется Характеристическая последовательность.

Subsequence
- Количество всех возможных подпоследовательностей - $2^n$