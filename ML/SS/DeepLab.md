
# Внешние ссылки

DeepLabv2? 
DeepLab: Semantic Image Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs
https://arxiv.org/abs/1606.00915

**Авторы**
Liang-Chieh Chen, George Papandreou, Iasonas Kokkinos, **Kevin Murphy**, Alan L. Yuille

How DeepLabV3 Works
https://developers.arcgis.com/python/guide/how-deeplabv3-works/

**MLT __init__ Session #2: DeepLab — Semantic Image Segmentation**
https://www.youtube.com/watch?v=HTgvG57JFYw

# Ссылки

[[Conditional Random Field (CRF)]]

Bilinear interpolation

AC
Atrous Convoltion (Dilated Convolution)
[[Dilated Convolution]]
[[Separable Convolution]]

ASPP
Atrous Spatial Pyramid Pooling
Сравнение с Inception

RF
receptive field

FM
feature map

FoV
Field of view

# Обзор

**Pipeline**
Backbone
ASPP
Upsample - x8
CRF

**CRF**
Old segmentation method
Treat image as graph
Short-range / Local CRF
Fully-connected CRF


# Downsampling
Не используется downsampling для FMs после определенного момента.
Начинают использоваться AC

*smaller resolution feature map is not useful for semantic segmentation tasks that require detailed spatial information* 

Чтобы не делать downsampling нужно убирать из сети pooling, просто применение сверток само по себе не уменьшает пространственное разрешение.
Pooling также увеличивает в итоге RF каждого пикселя?
Чтобы оставить RF на прежнем уровне используются AC

Действительно ли нужно так сильно увеличивать RF?
После нескольких блоков RF разве не равен размеру исходного изображения?

# ASPP
Atrous Spatial Pyramid Pooling

Применяется на FMs извлеченных с помощью backbone
Atrous Convoltion применяются параллельно с различными atrous rates

Применяется как замена FPN
Позволяет работать с объектами различных размеров
