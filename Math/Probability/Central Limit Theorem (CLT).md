
Центральная предельная теорема
ЦПТ


# External Links

https://en.wikipedia.org/wiki/Central_limit_theorem

[https://ru.wikipedia.org/wiki/Центральная_предельная_теорема](https://ru.wikipedia.org/wiki/%D0%A6%D0%B5%D0%BD%D1%82%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F_%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F_%D1%82%D0%B5%D0%BE%D1%80%D0%B5%D0%BC%D0%B0)

3Blue1Brown
https://www.youtube.com/watch?v=zeJD6dqJ5lo

# Links

[[Convolution]]

# Overview

[[Binomial Distribution]] -> [[Normal Distribution]]
Every Distribution -> [[Normal Distribution]]



## ENG

Definitions
- Distribution of a sum of a random variables converges to the [[Normal Distribution]]
- The distribution of a normalized version of the sample mean converges to a standard normal distribution
- sum of the r.v. vs. sample mean

What we can do with the help of CLP
- Calculating 95% [[Confidence Interval]]


3 Assumptions
- ?

Properties
- we can start from any distribution
- some distributions converges faster than another

Summing things up
- Distribution more and more spread out
- Distribution more and more shifted to the right
- Normalization
	- mean
	- std

mean
- mean of the sum of r.v. is sum of the mean
	- is it always true?
	- linearity properties of expectation
	- [[MIT 6.041SC. Probability Theory.]]
variance
- also adds
- $n* \sigma$
std
- $\sqrt{n}*\sigma$

## RUS

Сводка
- Распределение суммы случайных величин стремится к нормальному.
- Изначальное распределение случайной величины может быть любым.
- При суммировании распределение все больше и больше растет в ширь. Нужно нормализовывать распределение таким образом чтобы дисперсия равнялась единице.

e - is not special?
- Но с ним мы получаем очень удобную интерпретацию когда добавляем в формулу стандартное отклонение

Сигма
- Стандатное отклонение
- [https://ru.wikipedia.org/wiki/Среднеквадратическое_отклонение](https://ru.wikipedia.org/wiki/%D0%A1%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BA%D0%B2%D0%B0%D0%B4%D1%80%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5_%D0%BE%D1%82%D0%BA%D0%BB%D0%BE%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5)
- Почему сигма появляется в формуле для нормального распределения именно с таким коэфициентом? Потому что в таком виде она будет являться стандартным отклонением такого распределения.

Spike
- spiking bell curve
- Сумма одних распределений, сходятся к нормальному быстрее чем другие.

Доказательство
???