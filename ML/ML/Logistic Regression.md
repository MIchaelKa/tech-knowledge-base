
# Overview

Сигмоида
- Логарифм шансов
- Моделирование логарифма шансов соответствует использованию сигмоиды для получения вероятности из предсказания модели.

MLE для логистической регрессии
- логистическая функция потерь
- [[MLE]]
- [[Cross Entropy Loss (CEL)]]

Margin
- отступ (margin)
- не путать с зазором (margin) в SVM

Применение
- NLP
- logreg + tf-idf
- Анализ отзывов IMDB к фильмам

Closed form solution
- No closed form solution
- Но при этом такое решение есть для линейной регрессии.

Как выбрать порог для вероятности?
- Например, сделать так, чтобы доля положительных и отрицательных классов примерно совпадала с реальной.
- [[Probability Calibration]]

# Верхние оценки

- zero-one loss
- perceptron
- hinge loss, [[SVM]]
- логистическая функция потерь
	- рассматриваем как функцию от отступа

mlcourse.ai
Картинка отражает общую идею, что в задаче классификации, не умея напрямую минимизировать число ошибок мы минимизируем некоторую ее верхнюю оценку.

# Derivation

Why there are two different logistic loss formulation / notations?
https://stats.stackexchange.com/questions/229645/why-there-are-two-different-logistic-loss-formulation-notations

Deriving the derivative of the loss function for logistic regression
https://chatgpt.com/c/4bf62a48-77a2-4e73-8577-4e44caaae3a0

Loss function check
- loss is not equal to -np.log(0.5)
- https://chatgpt.com/c/820a80b3-a789-4542-8c3d-eded4145da5a
- the mean of logs should be equal log of mean?
	- [[Jensen’s Inequality]]
- should loss of logistic regression function be equal to 0.69