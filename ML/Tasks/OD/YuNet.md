
# Внешние ссылки

**Paper**
YuNet: A Tiny Millisecond-level Face Detector
[https://link.springer.com/article/10.1007/s11633-023-1423-y](https://link.springer.com/article/10.1007/s11633-023-1423-y)

**GH**
[https://github.com/ShiqiYu/libfacedetection.train/tree/master](https://github.com/ShiqiYu/libfacedetection.train/tree/master)


# Сводка

**Основные моменты**

**Количество параметров**

**Оценка**

**Данные для тренировки**

# Обзор

YuNet vs. YOLOX
anchor free
data sampling strategy for model training

**Contradiction**
1 - tiny faces in the background are normally not needed in many applications
2 - backbone should focus on small faces in face detection

**Float precision**
fp32
как fp16 работает для маленьких моделей?
[[Mixed precision training (MPT)]]
[[Quantization]]

Почему не изучается в статье?
Тема отдельного исследования.
Как поступать на практике?

**Layers**

>Large faces are easier to detect due to their rich information, so **it is not necessary to have too many channels in Layer 4**, or some deeper layers.

Хотя мы и предсказываем маленькие лица с фичамап большего размера и меньшей глубины (Layer 2), мы получаем эти фичамапы c более глубоких фичамап - так работает FPN. Посыл в том что более глубокий фичамапы всегда важны, даже для мелких деталей.

**Blocks**
depthwise convolution and pointwise convolution
[[Separable Convolution]]

**Backbone**
No skip connections?
[[ResNet]]



# Данные


# Архитектура


# Обучение


# Оценка

