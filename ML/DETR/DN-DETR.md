
# Внешние ссылки

**Paper**
DN-DETR: Accelerate DETR Training by Introducing Query DeNoising
https://arxiv.org/abs/2203.01305

# Сводка

**Основные моменты**

**Количество параметров**

**Оценка**

**Данные для тренировки**



# Ссылки

The Stable Marriage Problem
[[Hungarian Algorithm]]


# Термины


# Вопросы


Координаты ббокса подаются вместе с OQ?

# Обзор

**Denoising training**
DETR detectors
CNN-based detectors

**Problems with bipartite matching loss**
instability of bipartite graph matching
discrete bipartite matching
inconsistent update of anchors

Схожая проблема с [[Label Assignment]] ?
Если мы рассматриваем несколько похожих OQ только у одного из них будет матч с GT
На разных эпохах, для одного и того же GT, может быть матч у разных OQ

**Denoising Queries (DQ)** 
Применяются только во время тренировки
Несколько групп для каждого GT бокса
Получаем больше сигнала во время тренировки с каждого изображения

**Decoder**
Не различает отдельные OQ между собой
Задача для OQ и DQ похожие

**OQ**
Состоят из анкор бокс прайора и tgt (нули для первого слоя)
tgt - target - indicator feature (0/1, normal/denoising query)

**Label Denoising**
class embeddings


# Данные


# Архитектура


# Обучение


# Оценка

