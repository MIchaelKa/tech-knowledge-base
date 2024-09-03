
beam - луч

# Links

[[Transformer]]


# Overview

**wiki**
https://en.wikipedia.org/wiki/Beam_search

Beam search is a heuristic search algorithm that explores a graph by expanding the most promising node in a limited set.

Beam search is an optimization of **best-first search**

[[Combinatorial Search]]
[[Graph]]


**Жадный алгоритм**
Задача выбора следующего символа, слова.
Если всегда брать софтмакс максимум - получаем жадный алгоритм, но не факт что так мы найдет максимум по всему слову.

**Лосс**
Лосс когда предсказываем предложение из нескольких слов. Его нужно сравнить с GT предложением.

*model produces the outputs one at a time*
see the end of http://jalammar.github.io/illustrated-transformer/
**beam search**