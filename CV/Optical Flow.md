
Оптический поток

# External Links

Moved
https://www.notion.so/Optical-Flow-866880ee9a3f4965a294f0fe5940df0d

KLT Tracker
https://www.notion.so/KLT-Tracker-c847af26a71b4969a784e92e63b10c01

wiki
en.wikipedia.org/wiki/Optical_flow
ru.wikipedia.org/wiki/Оптический_поток

Смотреть заметки!

Две статьи на хабре
https://habr.com/ru/post/169055/
https://habr.com/ru/post/201406/

OpenCV
[https://docs.opencv.org/3.4/d4/dee/tutorial_optical_flow.html](https://docs.opencv.org/3.4/d4/dee/tutorial_optical_flow.html)
[https://docs.opencv.org/4.x/db/d7f/tutorial_js_lucas_kanade.html](https://docs.opencv.org/4.x/db/d7f/tutorial_js_lucas_kanade.html)

calcOpticalFlowPyrLK
https://docs.opencv.org/3.4/dc/d6b/group__video__track.html#ga473e4b886d0bcc6b65831eb88ed93323

# Paper

An Iterative Image Registration Technique with an Application to Stereo Vision
Bruce D. Lucas, Takeo Kanade
1981

Optical Flow Estimation. David J. Fleet, Yair Weiss.

# Links

[[Learning OpenCV]]

[[Tracking]]

[[Harris Corner Detection]]

[[Taylor Series]]
[[Divergence]]
- Related to?

# Discussion

Как бы ты хотел улучшить метод LK?
- В каким случаях он работает плохо?
- Находит неверные точки(там где их нет) если быстро сменить фрейм. Переключить картинку на мониторе.
- Улучшение с помощью фильтра Калмана чтобы трекать объект даже когда он ненадолго скрылся.
	- [[Kalman Filter]]


# Overview

Что мы раскладываем в ряд Тейлора?
- Функцию интенсивности пикселей изобраения в точке (x,y)

Optical flow works on several assumptions:
- The pixel intensities of an object do not change between consecutive frames.
- Функция интенисивности хорошо апроксимируется первой производной.
- Neighbouring pixels have similar motion.
	- LK Method

Предположения оптического потока
- Значения пикселей переходят из одного кадра в следующий без изменений
- Функция интенисивности хорошо апроксимируется первой производной


Brute force solution
- Поиск небольших фрагментов (патчей) между соседними изображениями
	- matchTemplate?
- Проблемы
	- как быстро отыскать нужный фрагмент, не перебирая весь кадр пиксель за пикселем?

# Lucas–Kanade

Lucas–Kanade method
LK Method

Алгоритм Лукаса-Канаде

Links
- ru.wikipedia.org/wiki/Алгоритм_Лукаса_—_Канаде

Summary
- Дифференциальный
	- Считаем производные кадра по горизонтали и вертикали
	- [[Image Gradient]]
- Local
- Patch-based

Patch-based
- An early example of a widely used image registration algorithm is the patch-based trans- lational alignment (optical flow) technique developed by Lucas and Kanade

Description
- Дифференциальный локальный метод вычисления оптического потока
- Основное уравнение оптического потока содержит две неизвестных и не может быть однозначно разрешено.
- LK делает третье предположение: соседние пиксели смещаются на одинаковое расстояние.
	- Пример с окном 5x5
	- Вместо одного уравнения мы получим сразу 25 уравнений
	- Система не имеет решения, ищем такое которое минимизирует ошибку
	- [[Least Squares]]
	- Используем двумерную гауссиану для задания весов уравнениям. Центральный пиксель имеет наибольий вес.
- Получим уравнение для решения МНК (в матричной форме)
	- Производные для нахождения минимума
	- Для нахождения решения (вектора смещения) матрица коэффициентов должна быть обратима
	- Check similarity of inverse matrix with Harris corner detector. It denotes that corners are better points to be tracked.
	- [[Harris Corner Detection]]

Уравнение оптического потока
- Gradient constraint equation
- Мы получили уравнение, которое говорит нам о том, что сумма частных производных должны быть равна нулю
- FLP
	- Уравнение Лапласа
	- Уравнение Пуассона


Solving system of linear equations
- When can this be solved? When $A^TA$ is invertible. And $A^TA$ is invertible when it has **full rank** (2), which occurs when it has **two large eigenvectors**.
	- Learning OpenCV


Implementation
- Поскольку в нахождении смещения каждого пикселя участвуют также соседние с ним пиксели, при реализации данного метода целесообразно предварительно посчитать производные кадра по горизонтали и вертикали.
- Pyramids


Pyramids
- Until now, we were dealing with small motions, so it fails when there is a large motion. To deal with this we use pyramids. When we go up in the pyramid, small motions are removed and large motions become small motions.
- OpenCV uses a more robust version of LK, which uses "pyramids".
	- https://lorenzopeppoloni.com/lkttracker/
- [[FPN]]

Warping
- Последовательное приближение
- Итеративное вычисление оптического потока.
- Используется для достижения требуемой точности, так как мы пренебрегаем вторыми производными при разложении в ряд Тейлора.
- Вычисляем поток, смещаем кадр до которого считали поток в соответствии с полученным смещением. Считаем поток еще раз и т.д. пока пиксели не совпадут с исходным кадром.
- Итоговое смещение - сумма смещений на всех итерациях.

Problems
- Barber’s pole
- Aperture problem