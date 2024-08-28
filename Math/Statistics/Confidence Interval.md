Доверительный интервал


# External Links

https://www.graphpad.com/guides/prism/7/statistics/stat_more_about_confidence_interval.htm


# Links

[[P-value]]

mlcourse.ai
- https://mlcourse.ai/book/topic05/topic5_part1_bagging.html
- bootstrap method
- Since our dataset is small, we would not get a good estimate by simply calculating the mean of the original sample. We will be better off applying the bootstrap method. Let’s generate 1000 new bootstrap samples from our original population and produce an interval estimate of the mean.
- Давайте сгенерируем 1000 новых подвыборок из нашей генеральной совокупности и сделаем интервальную оценку среднего

# Overview

95% доверительный интервал - показывает что этот интервал с 95% вероятностью содержит среднее генеральной совокупности.

Неверно говорить о том что среднее генеральной совокупности с 95% вероятностью принадлежит доверительному интервалу, так как это не случайная величина, хотя мы ее и не знаем. Напротив доверительный интервал зависит от наших данных.


# Calculation

Вычисление

Как вычислить доверительный интервал?
- Все что у нас есть это выборка из генеральной совокупности. Мы можем подсчитать ее среднее плюс у нас есть количество элементов в этой выборке. Этого достаточно?
- Нужно ли вычислить медиану?
- Нужно ли вычислять стандартное отклонение?

Bootstrap
- Пользуемся бутстрап выборками + `np.percentile`
- Будем ли мы получать слишком широкие доверительные интервалы в таком случае?

np.percentile
- https://numpy.org/doc/stable/reference/generated/numpy.percentile.html
- [[Quantile]]

np.percentile confidence interval
- How to calculate a Confidence Interval using numpy.percentile() in Python
- https://stackoverflow.com/questions/55857722/how-to-calculate-a-confidence-interval-using-numpy-percentile-in-python

confidence interval python
- scipy.stats
- https://stackoverflow.com/questions/15033511/compute-a-confidence-interval-from-sample-data