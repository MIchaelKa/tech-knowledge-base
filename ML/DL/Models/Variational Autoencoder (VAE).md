
https://www.notion.so/Variational-autoencoder-VAE-dd7e278650d24715b95da65523229854

# External Links

https://www.jeremyjordan.me/variational-autoencoders/

Arxiv Insights
https://www.youtube.com/watch?v=9zKuYvjFFS8

Tutorial on Autoencoders

auto-encoding variational bayes
https://arxiv.org/abs/1312.6114

Raschka
- Sebastian Raschka
- https://www.youtube.com/watch?v=UnImUYOdWgk&list=PLTKMiZHVd_2KJtIXOW0zFhFfBaJJilH51&index=139
- https://github.com/rasbt/stat453-deep-learning-ss21/tree/main/L17


# Parent

[[Unsupervised Learning (UL)]]
[[Generative Models]]
[[Autoencoders]]

# Links

[[dlcourse.ai]]

[[PCA]]
[[Entropy]]


# Overview

dlcourse.ai
- Решает проблему с оверфитом обычного автоэнкодера.
	- Автоэнкодер может оверфитится в том смысле что будет хорошо восстанавливать исходную картинку только для каких-то отдельных точек latent space и плохо справляться с задачей если мы чуть чуть подвигаем эту точку в пространстве.
- VAE вместо одной точки выдает среднюю и дисперсию и затем на декодер передается один сэмпл полученный из этого распределения.
- В добавок к L2 лоссу автоэнкодера дополнительный лосс для того чтобы эти распределения были как можно шире чтобы лучше покрыть пространство внутреннего представления.
	- как можно шире -> стремились к нормальному?
- Операции с полученным latent space
	- Вектор улыбки для лиц
	- Вектор добавления очков

Главные плюсы
- (по сравнению с обычными автоэнкодерами)
- smooth latent state representations of the input data

Независимость скрытых переменных
- Latent space disentanglement
- Latent perturbation
- Мы хотим чтобы все элементы скрытой переменной были независимы друг от друга.
- Используем вектор $\sigma$ вместо [[Covariance Matrix]]
	- считаем что все коэффициенты вне главной диагонали равны нулю
	- уже это само по себе не усиливает/приводит к независимости?
- Каждый элемент в векторе, каждая переменная имеет свое значение.

How to sample from distribution
- How to sample from normal distribution.
- $z=\mu+\sigma*\epsilon$
- В общем случае нужно использовать [[Covariance Matrix]] $\Sigma$
- $\epsilon = N(0,I)$

Reparametrization trick
- We can’t sample directly from $N(\mu, \sigma)$ because we need to backprob through these layers.
- But how to sample from $N(\mu, \sigma)$ in general?
	- See above

# VAE loss function

Links
- L17.4 VAE loss function

Evidence lower bound (ELBO)
https://en.wikipedia.org/wiki/Evidence_lower_bound

Loss
- Consist of two parts: Reconstruction loss and Regularization term
- This two parts should balance each other, it also can make our training instable.
- Both comes from data likelihood.

Regularization term
- N(0,I)
- KL divergence between $N(\mu, \sigma)$ and $N(0, I)$
- Why we want our distribution to be close to N(0,I), and what's the distribution we want to be N(0,I)
	- https://chatgpt.com/c/66e17e9e-0054-8000-947d-35d830b66ee7
- Applied to encoder output

Reconstruction loss
- BCE
- MSE

Using BCE as reconstruction loss
- Normalizing image to [0,1] range
- Why it may be not a good idea?
	- Different losses depending on pixel value. For example predicting right 0.2 value gives less loss then predicting 0.4

NLL loss wrt. term to encoder distribution
- Как это возможно, что является в этом случае GT?

Lower bound
- Tractable lower bound on data likelihood
- Lower bound on the log-likelihood
- Верхние оценки
	- [[Logistic Regression]]
- minimizing lower-bound == maximizing upper-bound
- Минимизация upper-bound это более _жесткое_ обучение?
- Jensen’s inequality
	- [[Logistic Regression]]

