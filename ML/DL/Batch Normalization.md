
# External Links

Batch Norm Explained Visually
https://towardsdatascience.com/batch-norm-explained-visually-how-it-works-and-why-neural-networks-need-it-b18919692739

https://learnopencv.com/batch-normalization-in-deep-networks/

# Paper

Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift
https://arxiv.org/abs/1502.03167
Sergey Ioffe, Christian Szegedy

# Parent

[[Normalization]]

# Links

[[cs231n]]
[[How to Train Your ResNet]]


# Summary

Как считается среднее в случае картинок?
```
# x.shape = (N,C,H,W)
x_mean = x.mean(axis=(0,2,3))
```

# Overview

Batchnorm steps
- Normalize
- Allow the network to squash the range if it want to
	- Do we only need it for tanh activation?
	- The network can learn to recover the identity mapping.

PROS
- Improves gradient flow
	- TODO
- Allow higher learning rate so network can learn quickly
- Reduces the strong dependence on initialization
- Acts as a form of regularization.

At test time BN functions differently.

BatchNorm vs. DataNorm
- Do we need zero-centering and normalization for the data if we use batchnorm? Can we just have BatchNorm before the very first layer? More computationally expensive?

Freezing batch normalization
- https://stackoverflow.com/questions/63016740/why-its-necessary-to-frozen-all-inner-state-of-a-batch-normalization-layer-when


# ICF

Internal Covariate Shift (ICF)

[[Data Distribution Shifts (DDS)]]

Difference between Local Response Normalization and Batch Normalization
- Jun 19, 2019
- https://towardsdatascience.com/difference-between-local-response-normalization-and-batch-normalization-272308c034ac
- Local Response Normalization


Изменение в распределении входных данных для внутренних слоев сети, связанное с изменением параметров предыдущих слоев во время тренировки.

Распределение должно оставаться тем же самым.

Подобное изменение возможно и для самого первого слоя если входные данные не берутся случайным образом. Рандомное генерирование батча решает проблему, но только для первого слоя.