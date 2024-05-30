
# Внешние ссылки

**Paper**
PointRend: Image Segmentation as Rendering
https://arxiv.org/abs/1912.08193


YT
https://www.youtube.com/watch?v=yvNZGDZC3F8
# Сводка

**Основные моменты**
Efficient representation

**Количество параметров**

**Оценка**

**Данные для тренировки**


# Ссылки


Subdivision strategy

Bilinear interpolation

# Обзор


**Efficient representation**
efficient representation for high-resolution output

more efficient representation than regular grid

3D
- mesh
- point cloud
- implicit functions
- octree

rendering in computer graphics
- implicit function
- sampling based representations

такие эффективные представление не были распространены в области 2D image recognition

**Подход**
Subdivision strategy
Постепенно увеличиваем разрешение делая предсказания для пикселей в который мы уверены меньше всего
[[Active Learning]]

**Upsampling**
Используем bilinear interpolation
После bilinear interpolation появляются пиксели с неуверенным/uncertain значением.
Свойство bilinear interpolation? Похоже на score от NN?

**Prediction**
Для каждой выбранной(неуверенной) точки делаются независимые предсказания с помощью легкого MLP

Во время тренировки точки для уточнения сэмплируются случайным образом
Во время инференса используется подход Subdivision strategy


# Данные


# Архитектура


# Обучение


# Оценка


# Вопросы