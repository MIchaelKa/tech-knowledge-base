
DINO: DETR with Improved DeNoising Anchor Boxes for End-to-End Object Detection
https://arxiv.org/abs/2203.03605

GH
https://github.com/IDEA-Research/DINO

# Сводка

**Основные моменты**

**Количество параметров**
DINO-SwinL - 218M

**Benchmarks**
COCO

**Данные для тренировки**
Objects365



# Ссылки

[[ViT]]
[[SAM]]
[[Swin Transformer]]

HTC++
Hybrid task cascade for instance segmentation

---

**DETR-like models**
[[DETR]]
Ссылки на вариации архитектуры DETR

---

**Сравнивают точность**
[[GLIP]]

# Термины


# Вопросы

Очень много вариаций DETR
DINO одна из вариаций но назвали по другому, DETR как часть аббревиатуры
Удачный маркетинговый ход?


# Обзор

DAB-DETR + [[DN-DETR]] + Deformable DETR

**Масштабируемость**
[[Scalability]]
scaling to a large backbone and a large-scale data set
В статье говорится о том что масштабируемость DETR-like моделей не была изучена.

contrastive denoising training
mixed query selection
look forward twice



# Данные

**Objects365**
Objects365: A large-scale, high-quality dataset for object detection


# Архитектура


# Обучение


# Оценка

COCO

**ResNet-50 backbone**
49.4AP in 12 epochs
51.3AP in 24 epochs
[[ResNet]]

**SwinL backbone**
pre-training on the Objects365
val2017 (63.2AP)
test-dev (63.3AP)