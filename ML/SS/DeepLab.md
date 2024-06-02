
# Внешние ссылки


DeepLab: Semantic Image Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs
https://arxiv.org/abs/1606.00915
DeepLabv2?

**Авторы**
Liang-Chieh Chen, George Papandreou, Iasonas Kokkinos, **Kevin Murphy**, Alan L. Yuille

How DeepLabV3 Works
https://developers.arcgis.com/python/guide/how-deeplabv3-works/

**MLT __init__ Session #2: DeepLab — Semantic Image Segmentation**
https://www.youtube.com/watch?v=HTgvG57JFYw

**DeepLab: Semantic Image Segmentation (How it works)**
Supervisely
https://www.youtube.com/watch?v=b6jhopSMit8

# Ссылки

[[DeepLabV3]]

Bilinear interpolation

AC
Atrous Convoltion (Dilated Convolution)
[[Dilated Convolution]]
Разряженные свертки
Игнорируем верхние частоты
Можем увидеть только нижние частоты

[[Separable Convolution]]

ASPP
Atrous Spatial Pyramid Pooling

RF
receptive field

FM
feature map

FoV
Field of view

# Обзор

**Основные моменты**
Полностью убираем pooling слои и оставляем только AC

**Pipeline**
Backbone
ASPP
Upsample - x8
CRF

**Spatial invariance**
Общее свойство CNN
Когда речь идет о конкретных фичах в FM то для задачи сегментации это плохо если пиксели на FM обладают SI

**We want both**
Нам нужно и сохранить широкий RF и при этом получить FM с высоким разрешением.

**Вопрос**
Почему архитектура стандартной CNN противоречит этому если мы просто уберем из нее pooling или свертки со страйдом? RF растет даже при применении обычных сверток. Нам действительно нужны AC? RF будет расти недостаточно быстро без них?

**Решение без AC**
Большая свертка
Больше параметров - overfitting
Вычислительно дорого

# Downsampling

Не используется downsampling для FMs после определенного момента.
Начинают использоваться AC

*smaller resolution feature map is not useful for semantic segmentation tasks that require detailed spatial information* 

Чтобы не делать downsampling нужно убирать из сети pooling, просто применение сверток само по себе не уменьшает пространственное разрешение.
Pooling также увеличивает в итоге RF каждого пикселя?
Чтобы оставить RF на прежнем уровне используются AC

**Вопрос**
Действительно ли нужно так сильно увеличивать RF?
После нескольких блоков RF разве не равен размеру исходного изображения?

# ASPP

Atrous Spatial Pyramid Pooling

Сравнение с архитектурой [[Inception]]

Применяется на FMs извлеченных с помощью backbone
Atrous Convoltion применяются параллельно с различными atrous rates

Применяется как замена FPN
Позволяет работать с объектами различных размеров


# CRF

[[Conditional Random Field (CRF)]]

Old segmentation method
Treat image as graph
Short-range / Local CRF
Fully-connected CRF

**Проблема**
Финальные пиксели классифицируются независимо
Это приводит к проблемы неконсистентных предсказаний маски

Графическая вероятностная модель
Граф модель

[[Joint probability]]
Разложение формулы совместной вероятности
Экспоненциально меньше параметров при использовании графической модели

Мы должны выбрать наиболее вероятную раскраску
[[Graph]]

Формула для потенциалов
Штрафуем соседние пиксели у которых разные значения
Potts model

Gaussian kernel
Свертка с гауссовским ядром
Теорема Котельникова
