
self-**di**stillation with **no** labels

# Внешние ссылки

Paper
Emerging Properties in Self-Supervised Vision Transformers
https://arxiv.org/abs/2104.14294

Вышла после [[CLIP]] (2103)

Official

YK
https://www.youtube.com/watch?v=h3ij3F3cPIk


# Сводка

**Команда**
FAIR, Meta

**Основные моменты**

**Количество параметров**

**Оценка**

**Данные для тренировки**


# Ссылки

vs. [[DINO-DETR]]
[[DINOv2]]


# Обзор

DINO
self-distillation with no labels

[[Self-Supervised Learning (SSL)]] + [[ViT]] = go together very well

Методология для unsupervised pre-training для visual transformer
No labels at training time

Self-distillation

teacher-student
[[Knowledge Distillation]]

No [[Contrastive Learning (CL)]] or Negative Sampling

Augmentations
[[BYOL]]

Global crops - more than 50% of the image
Local crops

2 аугментированные версии одной картинки
Одна подается на вход учителю, вторая студенту
Студент учиться предсказывать тоже самое представление
Loss: $-p_2 log (p_1)$

**Collapse**
Проблема с использованием одной модели и схемы с 2-мя аугментированными картинками выше.
Модель выучивает одно представление для всего, мы хотим этого избежать.

Трюк использовать две разные модели, учитель и студент. Почему две разные модели работают лучше? Могут ли это быть модели идентичной архитектуры.

В этой статье
Отходим от привычной схемы для [[Knowledge Distillation]]
Модель учителя создается из студента!
Для построения учителя используется [[Exponential Moving Average (EMA)]]

**Учитель**
centering
sharpening

**Sharpening**
[[Temperature]]
Температура намного меньше у учителя чем у студента
У учителя much more peaked distribution

**Softmax**
Пропускаем представление (эмбеддинг) через софтмакс
Затем считаем кросс-энтропи лосс для студента



# Задачи

Image retrieval
TODO

Segmentation
[[Semantic Segmentation]]
Self-attention maps
Может использоваться в качестве сегментационной маски

Zero-shot
[[Zero-Shot (ZSL)]] classification using kNN



