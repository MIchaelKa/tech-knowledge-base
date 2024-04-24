
allenai

A Diagram Is Worth A Dozen Images
https://arxiv.org/abs/1603.07396

GH
https://github.com/allenai/dqa-net


# Сводка

**Размер**
5000 grade school science diagrams
15000 corresponding multiple choice questions

150000 rich annotations
для создания DPG

**Метрики**

**Формат** 
multiple choice questions

**Модель**
DQA-Net

# Ссылки

**AI2D-RST**
Enhancing the AI2 Diagrams Dataset Using Rhetorical Structure Theory

AI2D-RST: A multimodal corpus of 1000 primary school science diagrams
https://arxiv.org/abs/1912.03879

**Статьи**
The language of graphics: A framework for the analysis of syntax and meaning in maps, charts and diagrams. Yuri Engelhardt (2002)

**Термины**
scene parsing
синтаксис
семантика


# Термины

**DPG**
Diagram Parse Graphs

# Вопросы

синтаксис vs. семантика

# Обзор

## Две задачи
Syntactic parsing 
Semantic interpretation

## Syntactic parsing

Похожа на задачу scene parsing для естественных изображений
В результате на этом шаге хотим получить DPG

**Dsdp-Net**
Deep Sequential Diagram Parser Network
LSTM
Учиться последовательно добавлять отношения к графу
Можно ли использовать [[GNN]] на этом этапе?

## Semantic interpretation

**Dqa-Net**
Модель использует DPG
Механизм аттеншена на DPG графе
LSTM

**Оценка**
Diagram question answering
Оценка качества осмысления моделью семантики диаграммы через задачу QA

## DPG
Diagram Parse Graphs

представление диаграммы
моделирование структуры диаграммы

**Состав диаграммы**
- constituents - составные элементы, несколько типов включая сложный элемент, к которому можно рекурсивно обращаться как к под-диаграмме
- relationships - отношения между элементами



# Данные


# Архитектура


# Обучение


# Оценка

