
Сравнение алгоритмов
Плюсы и минусы определенных моделей

Категории
- Чувствительность к выбросам

Points
- Sensitivity to outliers
- Sensitivity to preprocessing
- Interpretability
	- Feature Importance
	- [[Feature Selection]]
- High-dimensionality data

# Algorithms

kNN
Cons
- Плохо работает для данных высокой размерности

Naive Bayes
- Pros
	- Naive Bayes as online learning algorithm
	- Good if we don’t have much data
	- Fast
- Cons
	- Conditional independence of every other feature should be met

Random Forest
- Pros
	- Interpretability
	- Мало гиперпараметров
	- Не нужно мастшабировать признаки
	- Out of bag error
	- Работает из коробки
	- Outliers
	- Overfitting
- Cons
	- Accuracy

Boosting
- Pros
	- Точность
- Cons
	- Interpretability

SVM
- Pros
	- Margin
	- Kernels
	- Outliers
- Cons
	- Комментарий в cs4780 что страдает от проклятия размерности. Только с RBF ядром?

Logistic Regression
- Pros
	- Interpretability
		- Пример: интерпретируемость линейной регресси хорошая, но теряется если использовать ядровые методы.
	- High-dimensionality data
		- Хорошо работает с данными высокой размерности
	- Output come as probabilities
- Cons
	- Sensitivity to preprocessing
	- Hardly handle categorical features

Neural Networks
TBD


# Overview

SVM vs. Logistic Regression
- https://stats.stackexchange.com/questions/95340/comparing-svm-and-logistic-regression
- Unlike logistic regression, SVMs have means to prevent the model from being sensitive to outliers in the data
- The Support Vector Machines algorithm is much more geometrically motivated.
- LR gives calibrated probabilities
	- Is it true?
	- [[Probability Calibration]]

Random Forest vs. Boosting
- Random Forest vs. Boosting and when we need to use each
	- https://chatgpt.com/c/e8202a53-e3c5-47cb-ae8b-8c04717dfecb

Random Forest vs. Logistic Regression
- Random Forest vs. Logistic Regression and when we need to use each algorithm
	- https://chatgpt.com/c/e8202a53-e3c5-47cb-ae8b-8c04717dfecb
- Logistic Regression is good for high-dimensional data
	- [[mlcourse.ai]]