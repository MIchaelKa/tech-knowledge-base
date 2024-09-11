

https://www.notion.so/Training-Neural-Networks-TNN-96818468abca4df88befe3de3583b59e


# External Links

ConvNetJS
https://cs.stanford.edu/people/karpathy/convnetjs/

Deep Learning Tuning Playbook
https://github.com/google-research/tuning_playbook

Templates
- https://github.com/ashleve/lightning-hydra-template

# Links

[[cs231n]]
[[A Recipe for Training Neural Networks]]
[[How to Train Your ResNet]]


# Overview

[[Statistical Significance]]

[[Parameter Updates]]
[[Learning Rate Decays]]

[[TNN. Training Speed.]]

[[Crops]]

[[Label Smoothing]]

# Gradient

- [[Vanishing Gradients]]
- [[Exploding Gradients]]
- [[Gradient Clipping]]
- [[Gradient Accumulation]]

Визуализируем градиенты
- https://wandb.ai/ayush-thakur/debug-neural-nets/reports/Visualizing-and-Debugging-Neural-Networks-with-PyTorch-and-W-B--Vmlldzo2OTUzNA
- Искать взрыв градиентов или затухание градиентов

# Loss

[[Double Descent]]

track epochs vs. iterations
- epochs
	- track epochs rather than iterations since the number of iterations depends on the arbitrary setting of batch size
	- cs231n
- iterations
	- easy to train the same amount when dataset size changes

Steps
- Too straight line - better increase LR

Tips
- batch size
	- The amount of “wiggle” in the loss is related to the batch size.
- log domain
- Plot running average on the same noisy chart
	- [[Exponential Moving Average (EMA)]]

Plot loss functions in the log domain
- Вопрос: про какую ось идет речь?
- Paddle делает для логарифмическую ось для самого значения лосса
- Есть ли смысл делать логарифмическую ось для шкалы с номером итерации?