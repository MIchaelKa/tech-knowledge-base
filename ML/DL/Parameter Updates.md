
Moved
https://www.notion.so/M-Parameter-Updates-9e848203000d40b597a1b6cfc72a1455

# External Links

[https://cs231n.github.io/neural-networks-3/#update](https://cs231n.github.io/neural-networks-3/#update)

[https://pytorch.org/docs/stable/optim.html](https://pytorch.org/docs/stable/optim.html)


# Links

[[cs231n]]

# Discussion


Can we switch between optimizers during training?

Why we need LR decay for Adagrad/Adam at all? Adagrad already decays lr.
- See **LR decay and Adam** in this note

При градиентном спуске после каждого обновления весов получается уже немного другая функция?
- Нет. Веса которые мы обновляем задают не саму функцию а точку этой функции.

Но что если мы получим точку которая не принадлежит этой поверхности?
- Это невозможно так как функция определена на всех значениях
# Overview

first-order methods
second-order methods

# Momentum

Momentum update
```
# Momentum update
v = mu * v - learning_rate * dx # integrate velocity
x += v # integrate position
```

Nesterov Momentum
- lookahead gradient step, since we already know the momentum vector (mu * v)
- there is a trick with implementation

Преимущества
- Помогает проходить седловые точки
	- How?


# Per-parameter adaptive learning rate methods

**Adagrad**
```
# Assume the gradient dx and parameter vector x
cache += dx**2
x += - learning_rate* dx/ (np.sqrt(cache)+ eps)
```
can result in a premature and excessive decrease in the effective learning rate

**RMSprop**
```
cache = decay_rate * cache + (1 - decay_rate) * dx**2
x += - learning_rate * dx / (np.sqrt(cache) + eps)
```

Adagrad + momentum for cache?
NO, Adagrad + moving average

last gradients (dx) have more influence on the actual update
leaky counter?
unlike Adagrad the updates do not get monotonically smaller

# Adam
```
m = beta1*m + (1-beta1)*dx
v = beta2*v + (1-beta2)*(dx**2)
x += - learning_rate * m / (np.sqrt(v) + eps)
```

Summary
- RMSprop with momentum
	- What about Nesterov momentum (the above looks like vanilla momentum) ?
- bias correction mechanism
- Adam is a good default choice in most cases

AdamW
https://www.notion.so/AdamW-10a66fa1f99748bfb926ab7767c07eb2


# Second-order methods

L-BFGS
```
torch.optim.LBFGS
```

Newton’s method
- Анализировать квадратичную форму на каждом шаге градиентного спуска?
- Taylors approximation


# Practice

LR decay and Adam
https://stackoverflow.com/questions/39517431/should-we-do-learning-rate-decay-for-adam-optimizer

SGD vs. Adam
- well-tuned SGD will almost always slightly outperform Adam, but the optimal learning rate region is much more narrow and problem-specific
	- [[A Recipe for Training Neural Networks]]
- SGD likes more higher LR than Adam

# LR Range test

FastAI

Learning rate range test
- Finding Good Learning Rate and The One Cycle Policy
	- https://towardsdatascience.com/finding-good-learning-rate-and-the-one-cycle-policy-7159fe1db5d6
- Estimating an Optimal Learning Rate For a Deep Neural Network
	- https://towardsdatascience.com/estimating-optimal-learning-rate-for-a-deep-neural-network-ce32f2556ce0
- Setting the learning rate of your neural network
	- https://www.jeremyjordan.me/nn-learning-rate/