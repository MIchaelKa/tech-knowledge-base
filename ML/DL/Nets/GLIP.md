
microsoft

Grounded language-image pre-training
https://arxiv.org/abs/2112.03857

GH
[https://github.com/microsoft/GLIP](https://github.com/microsoft/GLIP)

# Ссылки

[[CLIP]]

[[Dynamic Head (DyHead)]]


# Данные

**Evaluation**
evaluated on COCO and LVIS
[[Visual Genome (VG)]]

Для работы необходим какой-либо текстовый запрос?
Как минимум классы перечисленные через точку.

Как подготавливать данные для тренировки такого пайплайна?
У каждого токена в текстовом запросе должен быть GT бокс?
soft labels as in [[MDETR]]?

# Обзор

## Reformulating detection

**Phrase grounding**
Unifying detection and grounding by reformulating object detection as phrase grounding

*effective and scalable pre-training task*

Можно использовать любой анкор-фри детектор.

>Instead of classifying each region/box into c classes, we reformulate detection as a grounding task, by grounding/aligning each region to c phrases in a text prompt

>For example, the text prompt for COCO object detection [37] is a text string that consists of 80 phrases, i.e., the 80 COCO object class names, joined by “. ”

>we can convert any detection model into a grounding model
>3.1

## Остальное

**vs. zero-shot**
Our setting differs from zero-shot detection
open-vocabulary object detection

**prompt tuning**
???

**Language model**
BERT?

**deep cross-modality fusion**
Different from CLIP

**Data**
teacher - student
GLIP can leverage massive image-text pairs by generating grounding boxes in a self-training fashion
automatically generating grounding boxes for massive image-text-paired data

Pseudo annotations
[[Pseudo Labeling]]

enables the use of grounding and massive image-text-paired data