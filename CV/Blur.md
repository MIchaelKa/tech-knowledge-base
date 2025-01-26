
Terms
- Размытие
- Размытие по Гауссу
- Gaussian blur
- Smoothing
- Blur
- Боке

Notion
- https://www.notion.so/ImPr-Blur-2f61e3698c064882ac5a21f274801229

Laplacian
- [[Laplacian]]
- https://www.notion.so/Laplacian-3f37176f69eb4c1d905235f8669a6270

wiki
- ru.wikipedia.org/wiki/Размытие_по_Гауссу
- отличается от эффекта боке

Blur detection with OpenCV
- https://pyimagesearch.com/2015/09/07/blur-detection-with-opencv/
- Laplacian

awesome-defocus-detection
- https://github.com/elejke/awesome-defocus-detection


chatgpt
- https://chatgpt.com/c/67941a7c-bab4-8000-9358-6e817dfc67e6
- Gaussian blur vs. Боке
	- Боке обычно проявляется как мягкие, размытые световые круги
- Дефокусировка vs. Боке


# Overview

Типы размытия в реальных данных
- Motion blur
- Дефокусировка
	- размытие по глубине
- Шумоподавление камеры — иногда размытие может быть вызвано алгоритмами постобработки
- Боке

комбинация размытости и шумов (например, слабое освещение, высокий ISO)
- высокий ISO

DL
- размытое изображение и его чёткий аналог
	- насколько важно иметь такие пары?
- Augmentations
	- Gaussian Blur
	- Motion blur
	- Defocus blur
	- Additive noise: добавление шума для моделирования низкого качества камеры.


Гауссов шум vs. Gaussian Blur
