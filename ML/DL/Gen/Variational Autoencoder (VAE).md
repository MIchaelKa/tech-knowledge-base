

# External

Notion
- https://www.notion.so/Variational-autoencoder-VAE-dd7e278650d24715b95da65523229854

Paper
- Auto-Encoding Variational Bayes
- Diederik P Kingma, Max Welling
- https://arxiv.org/abs/1312.6114

Tutorial on Autoencoders
- ?

Arxiv Insights
- https://www.youtube.com/watch?v=9zKuYvjFFS8

Raschka
- Sebastian Raschka
- https://www.youtube.com/watch?v=UnImUYOdWgk&list=PLTKMiZHVd_2KJtIXOW0zFhFfBaJJilH51&index=139
- https://github.com/rasbt/stat453-deep-learning-ss21/tree/main/L17

cs231n
- Notion
- [[cs231n]]

cs236
- [[cs236]]
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



Variational autoencoders.
- https://www.jeremyjordan.me/variational-autoencoders/
- intractable distribution
- variational inference



# Variational Inference

[[Variational Calculus]]

Variational Bayesian (VB)
Variational Inference (VI)

Variational Bayesian methods
- http://en.wikipedia.org/wiki/Variational_Bayesian_methods

Statistical inference
- https://en.wikipedia.org/wiki/Statistical_inference

chatgpt
- https://chatgpt.com/c/6935f46d-2878-8331-aee6-e500a36f05b8
- VI and VAE
- также схема с ELBO что и в VAE только в общем виде
- Variational Calculus vs. Variational Inference vs. Variational Bayesian

ELBO — What & Why
- https://yunfanj.com/blog/2021/01/11/ELBO.html
- decomposing a very complicated distribution
	- Where have you encountered something similar before?


Mixture of Gaussians

# A Beginner's Guide to Variational Methods: Mean-Field Approximation

- A Beginner's Guide to Variational Methods: Mean-Field Approximation
- Eric Jang
- https://blog.evjang.com/2016/08/variational-bayes.html

- statistical inference problems
- inference-optimization duality
- Problem Formulation
	- We could try to use sampling-based approaches like MCMC, but these are slow to converge.
- Forward KL vs. Reverse KL
	- [[KL-Divergence]]
	- see [[cs236]] - Lecture 4 - MLE
	- forward-KL will be large wherever Q(Z) fails to "cover up" P(Z)
	- If we are fitting a unimodal distribution to a multi-modal one, we'll end up with more false negatives
	- We use Reverse KL in VAE
	- We use Forward FL in MLE
	- Is it possible to use Reverse KL in VAE?
		- https://chatgpt.com/c/693dbb98-c4a0-832d-bc48-9fb53459fd9d
		- Mode-covering vs mode-seeking
		- This is not a modeling choice — it’s a computational constraint.



Q

- Можно ли применять ту же идею Variational Inference (VI) но для задачи классификации?


Q

- Why Is It Called “Mean-Field”?
- https://chatgpt.com/c/693c2ad4-365c-8327-be21-18b4502491d4

- The name comes from statistical physics
- Mean-field = the effect of the other variables summarized by their average influence.


Q

- Problem Formulation
- https://chatgpt.com/c/69396d0d-5324-832e-9a54-c66ecd4abd30

- Generative likelihood vs. Discriminative likelihood
- [[MLE]]
- MAP
- in complex tasks we often don’t know how to compute p(X|Z) or sample from p(Z|X)
	- if we cam sample from p(Z|X) then we can calculate p(X|Z) using decoder


Q

- Hidden Variables as Priors
- https://chatgpt.com/c/69395c41-28d0-832e-9bd3-4e053b96151a

- Why p(X) is NOT a prior to p(X|Z)
- p(X) cannot be a prior because “prior” refers to parameters or hidden variables, never to observed data
- in Bayesian modeling, a prior is always on parameters or latent causes, not on observations.
- p(X) is not part of the generative hierarchy; it’s just a normalization constant


- When we already know p(x), p(x|z) is not a generative process, this is inference on observed variables

- Bayesian generative hierarchy

- Discriminative reasoning direction


Q

- sample from a distribution vs. calculate the distribution mean

- https://chatgpt.com/c/69389307-a4a8-8330-81e5-0b602d043cc5
	- X
- https://chatgpt.com/c/693897fd-92f0-8328-ba31-06bc9d0bcf8c
	- Y

- If we can sample from z∼P(Z|X), we can use this to make a cat classifier that tells us whether a given image is a cat or not.

- Just evaluating the mean (like the mean of a decoder neural net) would give you a blurry average image, not a realistic sample.

- sampling adds structured randomness instead of averaging everything
- you mean we can get sharper image just adding some noise (with learned variance)?

- The mean does NOT define the full distribution
- The learnable variance is also important for VAE and used during generation?
- Realistic VAEs depend on noise injection through the learned variance.

# ELBO

ELBO
Evidence lower bound (ELBO)

Links
- wiki
	- https://en.wikipedia.org/wiki/Evidence_lower_bound
- 4o
	- https://chatgpt.com/c/6735060a-fe68-8000-a4c3-c4faac0dd069
- o1
	- https://chatgpt.com/c/67351c80-4140-8000-9f28-792ef764dec1

Links
- [[Jensen’s Inequality]]


Overview
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
- why we are sure that we can optimize lower bound?


Evidence in this case is p(x)


# Derivations


cs231n
- https://chatgpt.com/c/6738ff1f-ad80-8000-951c-ebf9cda0a69e
- в формуле мы хотим оценить вероятность для одной картинки
- это сложно сделать напрямую (p(x) - intractable) и мы вносим дополнительно переменную в виде z и оцениваем эту вероятность через мат ожидание с сэмплированием различных z
- как будет меняться вероятность p(x) в зависимости от различных z и должна ли она это делать?
- Формула из картинки — формально корректна, но тривиальна и бесполезна



# Questions


Q3

- how approximating p(z|x) will allows us to calculate p(x)?
- first we will sample z
- then we can calculate p(x|z)
- in that case p(x) = p(x|z)


Q2

- Как меняется лосс функция при переходе от обычного автоэнкодера к VAE?
- https://chatgpt.com/c/6935fb39-3080-832b-81eb-eff7476cacb2
- КЛЮЧЕВОЕ ДОПУЩЕНИЕ: шум в данных — гауссовский
- Если шум нормальный → оптимально уменьшать квадрат отклонений → L2
- Машинное обучение = максимизация правдоподобия с разными предположениями о распределениях.

- мы хотим максимизировать вероятность наблюдения x при заданном латенте z
- почему при этом важно именно максимизировать p(x|z) ведь наша конечная цель это максимизировать вероятность p(x)? С помощью автоэнкодера мы можем посчитать p(x) оставляя z внутри модели и не думая о нем?


Q1

- Зачем нам нужно учить вектор дисперсии, а затем стремиться в лосс функции чтобы распределение стремилось к нормальному, если мы могли бы зафиксировать вектор дисперсии состоящим из единиц (как в нормальном распределении к которому мы стремимся) и предсказывать только среднее и просто каждый раз делать сэмпл из такого распределения?
- https://chatgpt.com/c/672a1186-6bd0-8000-80ef-213deaac8ae6


- Про мотивацию для некоторых изображений выдавать увеличенную дисперсию в начале статьи
- https://www.jeremyjordan.me/variational-autoencoders/
- улыбка мона лизы


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


# Implementation

## Loss Function

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

## Reparametrization Trick

How to sample from distribution
- How to sample from normal distribution.
- $z=\mu+\sigma*\epsilon$
- В общем случае нужно использовать [[Covariance Matrix]] $\Sigma$
- $\epsilon = N(0,I)$

Reparametrization trick
- We can’t sample directly from $N(\mu, \sigma)$ because we need to backprob through these layers.
- But how to sample from $N(\mu, \sigma)$ in general?
	- See above