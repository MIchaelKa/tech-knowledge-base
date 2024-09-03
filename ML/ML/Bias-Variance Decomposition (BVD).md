Bias-Variance Tradeoff (BVT)


# External Links

Bias–variance tradeoff
https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff

mlcourse.ai
Тема 4. Линейные модели классификации и регрессии
https://habr.com/ru/companies/ods/articles/323890/
20 мар 2017 в 17:38

cs4780
https://www.cs.cornell.edu/courses/cs4780/2018fa/lectures/lecturenote12.html


# Overview

**Proof**
Regression setting: $y_i \in R$
All 3 terms are quadratic, we don’t want to make large any of them.

**Noise**
from data

**Variance**
from algorithm
Measures the extent to which the solution for individual dataset vary around their average.
drawing dataset == drawing classifier

**Bias**
(bias)^2
from algorithm
Noise is no longer matter (is no longer the issue)
Not depended from data.
What the error if we have infinite dataset. How then we will differ from desired regression function.

# How to deal with these errors?

High variance
=? overfitting
- [[Bagging]]
- More training data
- Reduce model complexity

Why bagging will help, if we will train using the same data?

High bias
=? underfitting
- [[Boosting]]
- More complex model
- Add features
- Kernels

**High noise**
- Remove outliners
- Add more features
	- ?

vs.
- https://chatgpt.com/c/fd2058ed-405b-4c78-a380-640ca84b5398
High variance vs. overfitting
- Overfitting is a specific instance of high variance.
- What are other options?
	- Poor Cross-Validation
	- Bad hyperparameters
High bias vs. underfitting
- Underfitting is a specific instance of high bias.
