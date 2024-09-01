
# Внешние ссылки

**Paper**
PDFVQA: A New Dataset for Real-World VQA on PDF Documents
[https://arxiv.org/abs/2304.06447](https://arxiv.org/abs/2304.06447)

**GH**
[https://github.com/adlnlp/pdfvqa](https://github.com/adlnlp/pdfvqa)

# Сводка

**Основные моменты**
multi-page
graph
вопросы о структуре документа

**Формат изображений**
Страницы из научных статей. А4 и текст маленького размера.
Изображения маленького размера для такого формата.
~792x612

**Граф**
Нет связей между страницами?


# Ссылки

[[Graph]]
[[ChartQA]]

[[LayoutLM]]

[[GNN]]
Doc-GCN

Scene text VQA
InfographicVQA

# Термины

**Structured layout**
Разметка документа
Иерархия элементов документа

# Вопросы

Q. Зачем нужен граф, почему не достаточно дерева?
A. Например если нет одного заголовка верхнего уровня, который может стать корнем дерева, но есть несколько заголовков одинакового уровня. Какие связи будут между такими вершинами

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
document element recognition
fixed answer space

B
structural understanding
object recognition
answer **extraction** on the document page level

С
parent relation understanding

Например заголовок будет родителем по отношению к контексту. Чтобы ответить правильно на вопрос “Какой раздел описывает таблицу номер 3?” нужно уметь понимать эти отношения между элементами документа, в данном случае это пример нахождения элемента выше по иерархии (нужно найти заголовок соответсвующий контенту)

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
