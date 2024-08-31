

Q
- Задача классификации. На выходе линейного слоя сигмоидная активация.
- Можно ли использовать MSE лосс?
- Зачем тогда нужен BCE?

A
- MSE лосс будет штрафовать сильнее при ошибке на разных классах

MSE loss assumes that the data has normal distribution, this is not the case for the classisfication task when the data has bearnoulli distribution.

https://towardsdatascience.com/why-using-mean-squared-error-mse-cost-function-for-binary-classification-is-a-bad-idea-933089e90df7

Можно также обратить внимание на задачу ординальной регрессии, к которой снова применение MSE может быть хорошей идеей.
- [[Ordinal Regression]]