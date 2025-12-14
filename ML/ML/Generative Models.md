

# External

Notion
- https://www.notion.so/Generative-Models-3a6cad46759e474da25b4387eddcb51f


# Parent

[[Unsupervised Learning (UL)]]

# Links

[[Naive Bayes]]

[[Autoencoders]]
[[Variational Autoencoder (VAE)]]

[[Diffusion Models]]

[[Generative Adversarial Networks (GAN)]]

Normalizing Flows
- vs. Network Flows

Resources
- [[cs231n]]
- [[cs236]]


# Overview

При объяснении, что такое моделирование распределения.
Представим наши картинки состоят из одного пикселя.

Taxonomy
- Autoregressive models
	- Language models
	- PixelCNN
	- PixelRNN

Density estimation
- How to get probability scalar value from different models?
- Anomaly detection

Unsupervised Learning
- [[Unsupervised Learning (UL)]]


# Math

KL-Divergence
- [[Entropy]]
- [[KL-Divergence]]

Rules of multiplication of distribution
- What the meaning of it?
	- Just get the value of density
- Gaussian
- [[Normal Distribution]]

Матожидание по реальным данным
- https://chatgpt.com/c/6745f1fc-16e4-8000-8a08-1c56f5f7e933
- CEL using Expectation
- in practice, this expectation is approximated by sampling from the dataset

Запись функции потерь через Expected value
- https://chatgpt.com/c/6738ff1f-ad80-8000-951c-ebf9cda0a69e
- Запись CEL через Expected value
- Expected value for VAE loss function derivation

# Вероятность изображения

Как оценить вероятность изображения используя генеративную модель?
https://chatgpt.com/c/6745f1fc-16e4-8000-8a08-1c56f5f7e933
начинаем с PixelRNN
в VAE прямая оценка невозможна

Как получить P(x) с помощью обученного VAE?
[[Importance Sampling]]

Мы делаем предположение что p(x) is Gaussian для VAE?
Нет, но мы обычно предполагаем, что $p_\theta(x \mid z)$ — нормальное распределение.

Простое усреднение: $\frac{1}{K}\sum_k p_\theta(x \mid z^{(k)})$ — не является корректной оценкой

# Моделирование распределения
(Вероятность изображения)

Мы учим распределение, как это понимать?

Если модель учит распределение $P_{model}(x)$ где x это изображение, то и на вход должна принимать изображение. Таким образом мы можем оценить вероятность какого-то шума (будет низкая) или другой картинки (высокая).

Понятно как это делать для авторегрессионных моделей.
Для VAE смотри выше, напрямую нельзя, но можно прикинуть.

2D пример?

Что значит моделируем распределение нейронной сетью?
Можем сказать насколько вероятен данный пример.
Можем сгенерировать новый пример из этого распределения.
Знаем $\mu$ и $\sigma$ или другие параметры для нашего распределения.

Чтобы моделировать нормальное распределение достаточно выдавать вектора $\mu$ и $\sigma$.
Когда мы выдаем в результате картинку можно считать что это наше $\mu$
В случае ганов, почему нельзя считать что это параметр распределения?

VAE
Decoder network gives p(x|z)
Мы хотим максимизировать вероятность наблюдения x при заданном латенте z
Используем и сгенерированный x^ - среднее распределения, и тот х который подавался на вход. Сможем найти вероятность из формулы нормального распределения.
Максимизация этой вероятность приводит в L2 лоссу ||x^ - x||

# Как генерировать данные?

How to sample from distribution
Сэмплирование

Генерировавать попиксельно
PixelRNN and PixelCNN

Генерировать из latent variable z
VAE

From latent space
Почему сэплировать из распределения для latent variables легче, чем сэмплировать сразу из распределения для изображений?
Потому что мы значем это распределение, и компоненты вектора latent variable не зависят друг от друга. Можем просто сгенерировать n независимых нормальных переменных.


Как сгенерировать новый сэмпл если мы знаем $P_{model}(x)$?
В случае VAE мы умеем сэмплировать z, а дальше используем декодер.
В случае авто-регрессионных моделей, сначала сэмплируем первый пиксель(random generator), а дальше используем модель.


How do you sample data from a known distribution?
how to sample from known distribution
https://stats.stackexchange.com/questions/186065/how-do-you-sample-data-from-a-known-distribution
pseudo-random numbers generation


# Как определить модель?

Картинки: 28х28 (784 чисел), 0/1 пиксели

Как определить генеративную модель? 

Наивный подход – таблица из чисел, где мы присваиваем вероятность каждому возможному варианту.

Следующий подход

- Определим функцию которая принимаем на вход картинку (784 чисел) и возвращает число. Можем ли мы просто определить один линейный слой с 784 параметрами для этого?  
- Да можно. Это scoring function, а не распределение.

- Что если мы просто обернем последний слой произвольной сети в сигмодиду? Мы автоматически получим valid probability distribution?
- НЕТ!
- Но это сработает если семейство которое мы приближаем очень простое, например Bernoulli или Categorical для одного пиксели при использовании Autoregressive models и Сhain Rule. 

- Почему важно чтобы полученная функция представляла собой valid probability distribution?
- [[cs236]] - Lecture 11

- Можно ли использовать MLE не определяя valid probability distribution? И почему?
- модель может делать тривиальные вещи
- оптимум уходит в бесконечность
- MLE всегда подразумевает:
	- если ты повышаешь вероятность данных
	- ты обязан понизить вероятность где-то ещё

- Что если наша модель не будет определять valid probability distribution, но при этом будет выдавать более большие числа для настоящих изображений, чем для шума. Сможем ли мы использовать такую модель? Сможем ли мы обучать такую модель?
- Да сможем.
- Варианты
	- GAN
	- Score matching

Autoregressive
- Каким образом Сhain Rule помогаем установить valid probability distribution?
- Если каждый conditional — валиден, то всё произведение — валидное распределение.
- Для 


VAE
- А как задает это распределение VAE?
- VAE не учит “распределение картинок напрямую”.  
- Он учит “как картинки порождаются из шума”.

---

[[cs236]]
- Lecture 2
- Lecture 11

chatGPT
- https://chatgpt.com/c/693eafd8-9098-832f-bae9-7055466bae37