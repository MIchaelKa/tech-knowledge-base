

# External

Notion
- https://www.notion.so/Variational-autoencoder-VAE-dd7e278650d24715b95da65523229854

Paper
- Auto-Encoding Variational Bayes
- https://arxiv.org/abs/1312.6114

Tutorial on Autoencoders
- ?

Variational autoencoders.
- https://www.jeremyjordan.me/variational-autoencoders/
- intractable distribution
- variational inference

Arxiv Insights
- https://www.youtube.com/watch?v=9zKuYvjFFS8

Raschka
- Sebastian Raschka
- https://www.youtube.com/watch?v=UnImUYOdWgk&list=PLTKMiZHVd_2KJtIXOW0zFhFfBaJJilH51&index=139
- https://github.com/rasbt/stat453-deep-learning-ss21/tree/main/L17

cs231n
- Notion
- [[cs231n]]
- https://deepgenerativemodels.github.io/notes/vae/

# Parent

[[Unsupervised Learning (UL)]]
[[Generative Models]]
[[Autoencoders]]

# Links

[[dlcourse.ai]]
[[cs231n]]

[[PCA]]
[[Entropy]]
[[KL-Divergence]]

 variational
- [[Variational Calculus]]
- variational bayesian (VB)
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


# Blogs

From Autoencoder to Beta-VAE
- Links
	- https://lilianweng.github.io/posts/2018-08-12-vae/
- images - high dimensional input with high redundancy
- Sparse Autoencoder
	- vs. Dropout
		- Same effect but using loss function?
	- KL-divergence between two Bernoulli distributions
- VAE
	- variational bayesian (VB)
	- Marginalization over z
		- fundamental during training, not necessarily during inference
		-  the training objective considers the contribution of all possible latent codes z
	- ELBO
- Beta-VAE
- VQ-VAE
- VQ-VAE-2
	- hierarchical latent variables

A Beginner's Guide to Variational Methods: Mean-Field Approximation
- https://blog.evjang.com/2016/08/variational-bayes.html
- Variational Bayeisan (VB)
- If we can sample from z∼P(Z|X), we can use this to make a cat classifier that tells us whether a given image is a cat or not.

# Reparametrization trick

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

GPT
- https://chatgpt.com/c/66e17e9e-0054-8000-947d-35d830b66ee7

Loss
- Consist of two parts: Reconstruction loss and Regularization term
- This two parts should balance each other, it also can make our training instable.
- Both comes from data likelihood.

Regularization term
- N(0,I)
- KL divergence between $N(\mu, \sigma)$ and $N(0, I)$
- Why we want our distribution to be close to N(0,I), and what's the distribution we want to be N(0,I)
	- See GPT
	- Distribution of latent variable
- Applied to encoder output

Reconstruction loss
- BCE
- MSE

Using BCE as reconstruction loss
- Normalizing image to (0,1) range
- Why it may be not a good idea?
	- Different losses depending on pixel value. For example predicting right 0.2 value gives less loss then predicting 0.4

NLL loss wrt. term to encoder distribution
- Как это возможно, что является в этом случае GT?

The [[KL-Divergence]]
- How to get loss function?
- https://github.com/rasbt/stat453-deep-learning-ss21/blob/main/L17/helper_train.py#L175C43-L175C52
- https://chatgpt.com/c/673501dc-89ec-8000-bd7a-219625f2bda4
- Instead of calculating the loss in the closed from can we explicitly calculate it as difference of two logarithms?
	- Yes, using Monte Carlo estimation

ELBO
- Evidence lower bound (ELBO)
- Links
	- wiki
		- https://en.wikipedia.org/wiki/Evidence_lower_bound
	- forward vs. reverse DKL
		- https://blog.evjang.com/2016/08/variational-bayes.html
	- 4o
		- https://chatgpt.com/c/6735060a-fe68-8000-a4c3-c4faac0dd069
	- o1
		- https://chatgpt.com/c/67351c80-4140-8000-9f28-792ef764dec1
- Tractable lower bound on data likelihood
- Lower bound on the log-likelihood
- Верхние оценки
	- [[Logistic Regression]]
- upper-bound
	- minimizing lower-bound == maximizing upper-bound - ?
		- Минимизация upper-bound это более _жесткое_ обучение?
	- maximizing lower-bound == minimizing upper-bound - better
	- we want maximize lower bound
	- we want minimize loss
	- we are minimizing upper-bound
- [[Jensen’s Inequality]]
- how approximating p(z|x) will allows us to calculate p(x)?
- why we are sure that we can optimize lower bound?

# Questions


Q1
- Зачем нам нужно учить вектор дисперсии, а затем стремиться в лосс функции чтобы распределение стремилось к нормальному, если мы могли бы зафиксировать вектор дисперсии состоящим из единиц (как в нормальном распределении к которому мы стремимся) и предсказывать только среднее и просто каждый раз делать сэмпл из такого распределения?
- GPT
	- https://chatgpt.com/c/672a1186-6bd0-8000-80ef-213deaac8ae6
- Про мотивацию для некоторых изображений выдавать увеличенную дисперсию в начале статьи
	- https://www.jeremyjordan.me/variational-autoencoders/
	- улыбка мона лизы