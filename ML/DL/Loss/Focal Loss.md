
Moved
https://www.notion.so/Focal-Loss-b440289b7e45407384a0cbb9384dd55c

# External Links

[https://paperswithcode.com/method/focal-loss](https://paperswithcode.com/method/focal-loss)

focal loss pytorch
https://pytorch.org/vision/main/_modules/torchvision/ops/focal_loss.html

# Paper

Focal Loss for Dense Object Detection
https://arxiv.org/abs/1708.02002
Tsung-Yi Lin, Priya Goyal, Ross Girshick, Kaiming He, Piotr Dollár

# Parent

[[Loss. SS and OD]]

# Links

RetinaNet

od_sanbox
- https://github.com/MIchaelKa/od_sandbox/blob/main/criterion.py

# Overview

Focal loss is a modified version of cross-entropy loss
- https://www.linkedin.com/advice/3/what-pros-cons-different-loss-functions-object-detection
- Is it true? Should we say it’s modified version of L1/L2 loss?
- No. Focal loss is for objectness loss.

Paper
- In contrast, one-stage detectors that are applied over a regular, dense sampling of possible object locations

**Возводим в степень число меньшее единицы**

Вопрос:
Когда мы возводим в степень число меньшее единицы оно только уменьшается. Почему более высокие значения для параметры гамма тогда действует как более жесткая фокусировка ~~или это не так и самая сильная фокусировка при гамма равном единице~~?

Ответ:
Считаем $(1-p)^\gamma$, для $\gamma = 2$
Пусть предсказанная вероятность класса 1, p = 0.9
- $0.1*0.1 = 0.01$ - x100 раз меньше чем CE
Пусть предсказанная вероятность класса 1, p = 0.4
- $0.6*0.6 = 0.36$ - x2.7 раз меньше чем CE