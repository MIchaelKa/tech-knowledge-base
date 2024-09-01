
Primer of Biostatistics
Stanton A. Glantz

Медико-биологическая статистика
Стентон Гланц

# External Links

http://localhost:8888/notebooks/notebooks/glantz_problems.ipynb

PDF
http://medstatistic.ru/articles/glantz.pdf


# 1. Введение

Не правильное использование статистических методов
- Критерий Стьюдента
	- Большинство ошибок связано с неправомерным использованием критерия Стьюдента.
	- Нужен дисперсионный анализ.
	- Критерий Стьюдента - частный случай дисперсионного анализа
- Умение сравнивать результаты полученные по нескольким группам
	- Методы множественного сравнения
	- [[AB Tests]]

Вероятностный характер выводов статистики.

Простейшие ошибки
- отсутствие контрольной группы
	- контрольная группа - плацебо
- использование неслучайных выборок

Статистическая проверка гипотез.
- Какой критерий был использован?

# 2. Как описать данные

Описательная статистика

2 типа задач
- как описать данные
- проверка гипотез

Правило трех сигм
- Нормальное распределение
- 68% примеров лежит в пределах одного стандартного отклоения.
- 95% примеров лежит в пределах двух стандартных отклонений.
	- Между 2.5 и 97.5 процентилями.

Несимметричное распределение
- Если распределение не является нормальным, а значения распределены несимметрично относительно среднего, то для описания данных некорректно пользоваться значением среднего и стандартного отклонения.
- Пример с зарплатами и Биллом Гейтсом.

Описание нессиметричного распределения
- Для описания таких данных лучше всего подходит медиана и процентили
- Медиана и процентили, в отличие от среднего и стандартного отклонения, не дают полного описания распределения

Проверка распределения (выборки) на нормальность.
- Если например 25-й процентиль ближе к медиане чем 75-й, это говорит о несимметричности распределения.

Зачем на проверять данные на нормальность?
- Важно понимать является ли распределение нормальным чтобы знать чем лучше пользоватсья для его описания средним и стандартным отклонением или 25 и 75 процентилями. Как раз вычисление процентилей и позволяет понять с каким распределением мы имеем дело.
- Многие методы проверки гипотез, основаны на предположении что распределение близко к нормальному

## Выборочные оценки

Стандартная ошибка
- Стандартная ошибка среднего
- Распределение выборочных средних стремится к нормальному
	- Среднее этого распределения стремиться к среднему генеральной совокупности.
	- Стандартное отклонение этого распределения называется стандартной ошибкой среднего.
		- Меньше стандартной ошибки генеральной совокупности
	- [[Central Limit Theorem (CLT)]]

Так как возможные значения выборочных средних стремятся к нормальному распределению, истинное значение среднего лежит с 95% вероятностью в пределах 2х стандартных ошибок выборочного среднего.
- [[Confidence Interval]]

Стандартное отклонение vs. Стандартная ошибка среднего

Standard error
- can be calculated for any statistics, not only the mean

Standard error of the mean (SEM)
- standard deviation of means of random samples of size 10 drawn from the original population


# 3. 

How to Test for Differences between Groups


tests of significance
метод оценки статистической значимости
критерии значимости

Дисперсионный анализ
analysis of variance
ANOVA

[[P-value]]

To describe a difference between groups we need to compare
- variability among sample means
- variability within each sample.
- use variance as a measure of variability

Parametric statistical methods
Параметрические методы
- Дисперсия правильно говорит о разбросе данных только в том случае если они нормально распределены.
- valid only when the real population approximately follows the normal distribution

Nonparametric statistical methods
- does not require normal distribution assumption

Two estimates of population variance
 - within-groups variance
 - between-groups variance
 - F-test statistic
 - F distribution
 - F-критерий значимости?

F distribution
- Эсперимент мысленно проводим для всех возможных выборок из одного распределения каждый раз получая значение F
- Почему распределение F имеет максимум не в 1 если извлекать тестовые выборки из одного и того же нормального распределения?
- What is the type of this distribution?
	- https://chatgpt.com/c/9c36cf7f-c28e-49c7-af01-7aa639630ed5
	- The F-distribution is derived from the ratio of two independent chi-squared distributions
	- [[Chi-Square]]

How big F-value should be to reject null hypothesis?
- Critical value of F
- We need to convert F-value to P-value and compare with alpha
- alpha - level of significance

[[P-value]]
- Вероятность ошибочно отвергнуть верную нулевую гипотезу обозначается P.
- The probability to reject null hypothesis by mistake

Степени свободы
degree-of-freedom parameters


one way or single factor analysis of variance

Если мы обнаружили статистическую значимость, то как узнать какие конкретно группы вносят этот вклад?


# 4.

The Special Case of Two Groups: The t Test

[[T-test]]

Эффект множественных сравнений
- Multiple Comparisons
- T-test is not suitable for pairwise comparison of multiple groups.

Объединеннная оценка дисперсии
- Зачем?

Критерий t

t = разность выборочных средних / стандартная ошибка разности выборочных средних

# 5.

Анализ качественных признаков

[[Chi-Square]]

Доля для качественных признаков - эквивалент среднего для количественных

Что понимать под разбросом если значения признака всего два?
- Уже используем one-hot
- [[Bernoulli Distribution]]
- Стандартное отклонение полностью определяется средним значением

Выборочная оценка доли
Estimate of the population proportion

Стандартная ошибка доли
Standard error of the proportion

Критерий z, аналогичный критерию Стюдента t