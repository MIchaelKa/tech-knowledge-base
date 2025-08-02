
maximum likelihood estimation
maximum likelihood criterion

Принцип максимального правдоподобия

# Links

[[Bishop (BOOK)]]
- 1.2.4
- 3.1.1

# Overview

likelihood of the parameters vs. likelihood of the dataset

Неявно делаем два предположения
Данные распределены независимо и одинаково

А как получить оценки из MLE?
- Как мы из MLE получаем формулу для среднего?
- Минимизация лосса по отношению к параметру $\mu$

Limitations of the MLE
- systematically underestimates the variance of the distribution
- bias

Likelihood vs. Probability
- [[Spinning Up in Deep RL]]
- https://gemini.google.com/app/d8eb964149651d43
- **Probability** quantifies the chance of a particular **outcome** (like an action) given that the underlying parameters of a model (the policy) are known and fixed. You would ask: "Given this specific policy, what is the probability of taking this action?"
- **Likelihood** refers to the plausibility of a certain set of **model parameters** given that you have observed a particular outcome. You would ask: "I took this specific action. How likely is it that it came from this particular policy?"