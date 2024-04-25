
GH
[https://github.com/adlnlp/pdfvqa](https://github.com/adlnlp/pdfvqa)

rnd-hub
[https://rnd-catalog.de.mlrnd.ru/datasets/pdfvqa](https://rnd-catalog.de.mlrnd.ru/datasets/pdfvqa)

PDFVQA: A New Dataset for Real-World VQA on PDF Documents
[https://arxiv.org/abs/2304.06447](https://arxiv.org/abs/2304.06447)


# Сводка

**Основные моменты**
multi-page
graph
вопросы о структуре документа

# Ссылки

[[Graph]]

[[LayoutLM]]

Doc-GCN
[[GNN]]

Scene text VQA
InfographicVQA

# Термины

**Structured layout**
Разметка документа
Иерархия элементов документа

# Вопросы

Зачем нужен граф, почему не достаточно дерева?

# Обзор

**Multi-Page**
Вопросы по документу состоящему из нескольких страниц

**Структура документа**
Добавляются вопросы о структуре документа, об отношении между элементами документа, например подписи и диаграммы. Предполагается что такие умения будут затем нужны модели чтобы правильно извлекать информацию для ответа на вопросы категории С.

В датасете делается упор именно на структуру научных статей?
PubMed

# **Разметка**

тут в смысле Annotation

**Автоматическая разметка**
_automatic question-answer generation process_
Выложен ли код?
question patterns

функциональная программа на графе

balancing
TODO

**Источник данных**
PubMed

associated XML files
К каждой статье на PubMed есть такой файл?
Есть ли такой же на arxiv?

Mask-RCNN

# **3 типа задач**

A

B
structural understanding
object recognition

С
parent relation understanding

Например заголовок будет родителем по отношению к контексту. Чтобы ответить правильно на вопрос “Какой раздел описывает таблицу номер 3?” нужно уметь понимать эти отношения между элементами документа, в данном случае это пример нахождения элемента выше по иерархии (нужно найти заловок соответсвующий контенту)

Identifying the items at the higher-level hierarchy
Identifying the items at the lower-level hierarchy

# Graph

Relational Graphs
Relational Graph Annotation

_annotates the hierarchically logical relational graph_

Как-то связано с графом в [[GQA]]?

**Модель**
_new graph-based VQA model_

Doc-GCN