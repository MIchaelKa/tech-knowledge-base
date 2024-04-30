
NoisyStudent

# Внешние ссылки

**Paper**
Self-training with Noisy Student improves ImageNet classification
https://arxiv.org/abs/1911.04252

**Обзор архитектуры Swin Transformer**
https://habr.com/ru/post/599057/

# Ссылки

[[Self-Supervised Learning (SSL)]]
[[Knowledge Distillation]]
Transfer Learning (TL)

# YK

https://www.youtube.com/watch?v=q7PjrmGNx5A

**TL**
Big dataset w. or w/o labels
Small dataset w. label
Finetune on small dataset

TL w/o labels
Autoencoders

TL for ImageNet dataset
Even larger unlabeled dataset

Reverse TL process

Step 1.
Train SL on ImageNet
Get teacher model

Step 2.
Label unlabeled images
[[Pseudo Labeling]]

Step 3.
Train student on big dataset labeled with teacher model
Better result on original ImageNet dataset

Noise and augmentation in big dataset
Student model larger than teacher

Step 4.
Train new teacher model

Cycle!
diminishing **returns**

---

**Noise**
Data augmentation
[[Dropout]]
Stochastic depth

**Noise for teacher**
No noise?
No noise at labeling time.

**Noise for student**
Max noise?
Should able to reproduce teacher model w/o dropout and SD?
YK says we do use dropout and SD on student model

Почему Data augmentation == Noise ?
С аугментациями модели сложнее предсказывать
Трейн лосс обычно увеличивается
Пример на 32:20

---

**pseudo-labels**
soft or hard pseudo-labels

> I think it is very important that they reject images with high entropy soft-pseudo-labels

Стандартный кросс-энтропи лосс в PyTorch работает с софт метками?
[[Soft Labels]]

---

**How noise is working**

Студент должен по аугментированной картинке воспроизвести ту псевдометку которую сгенерировала модель учителя.

**Tricks**
Larger batch size
Filter high entropy soft-pseudo-labels

---

**Results**
Final model more robust to adversarial attacks
[[Adversarial Attacks]]
