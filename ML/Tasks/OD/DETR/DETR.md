
# Внешние ссылки

**Paper**
End-to-End Object Detection with Transformers
[https://arxiv.org/abs/2005.12872](https://arxiv.org/abs/2005.12872)
Meta

**GH**
https://github.com/facebookresearch/detr

**Yannic Kilcher**
[https://www.youtube.com/watch?v=T35ba_VXkMY](https://www.youtube.com/watch?v=T35ba_VXkMY)

**Artgor RUS**
https://habr.com/ru/companies/ods/articles/507880/

**HF**
https://huggingface.co/docs/transformers/model_doc/detr

**Modern Object Detection: from YOLO to transformers**
Mak Gaiduk
https://www.youtube.com/playlist?list=PL1HdfW5-F8AQlPZCJBq2gNjERTDEAl8v3

# Ссылки

[[Transformer]]

Segmentation
[[Semantic Segmentation]]
Panoptic segmentation

# DETR-like models

Efficient DETR
Conditional DETR

[[MDETR]]

[[Deformable DETR]]
[[DAB-DETR]]
[[DN-DETR]]

[[DINO-DETR]]

[[Dynamic Head (DyHead)]]
- Is it also DETR-like ?


# Термины

Object Queries (OQ)


# Вопросы


# Обзор



# Limitations

**feature maps**
lack of high-resolution feature maps
problems with small objects
Solved by [[Swin Transformer]] ?

**slow training convergence**
*slow training convergence issue of DETR introduced by decoder cross-attention*
*DINO Paper*

# Bipartite matching loss

instead of NMS?

always predicting N objects
no_object class, algorithm can predict it, pad target objects count to N
мы не хотим чтобы один и тот же объект детектировался несколько раз

[[Hungarian Algorithm]]
what the complexity?

**Как мы считали лосс в SSD?**
Как соблюдали порядок предсказанных и таргет боксов?
Мы делали предсказания для каждого анкора, из нескольких таргет боксов также получали таргеты для каждого анкора.

# Архитектура

CNN→Transformer
Can we use ViT instead of CNN?

Positional encoding.

Encoder-Decoder
Unroll processed by CNN image of size (C, H, M) into array of vectors (C, HxM) and feed it to the transformer.

**Object queries**
Object queries. Learnable. N vectors.
Q in transformer architecture.

Use K and V from encoder

Object queries can communicate with each other
Кроме Cross-attention используется еще и Self-attention ?

Num of object queries == num of max predicted boxes?

**Cross-attention**
Каждый q использует взвешенную комбинация v из энкодера.
Так каждый q соответствует какому-то ббоксу, он решает как визуальная информация ему нужна, чтобы определить ббокс для объекта или сказать что объект отсутствует.

**Attention matrix**
*Transformers are uniquely well conducive for object detection task*
YK
Quadratic attention mechanism.
Два вектора(две последовательности в данном случае) умножаются таким образом чтобы получить матрицу.


# Данные


# Обучение


# Оценка

