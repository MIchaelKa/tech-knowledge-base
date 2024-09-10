
Moved
https://www.notion.so/M-Weight-Initialization-327aa53c228440a69f67770723e5da43

# External Links

[https://cs231n.github.io/neural-networks-2/#init](https://cs231n.github.io/neural-networks-2/#init)

# Links

[[cs231n]]

# Overview

vs. normalization
- [[Normalization]]
- Почему нам все еще нужна нормализация?
- Почему нельзя просто каждый выход делить на квадратный корень соответствующей размерности?
	- Нужно также центрировать
- networks that use Batch Normalization are significantly more robust to bad initialization

Variance
- https://en.wikipedia.org/wiki/Variance
- $Var(c*A) = c^2*Var(A)​$

Symmetry Breaking

Initialization with zeros
- We need to break the symmetry

Initialization with small random numbers
- What the problems can arise here?
- https://chatgpt.com/c/9a6f42f0-aa0f-4baf-afc6-9deb561ce2af
- Vanishing Gradients
- Variance that grows with the number of inputs

cs231n example is using tanh nonlinearity.
- Vanishing gradients if init with random small numbers from gaussian distribution N(0,0.01)
- If init with N(0,1) almost all neurons completely saturated (either -1 and 1). Gradient will be all zero.
- If you getting unit gaussian data as input and you want to the linear neuron have a variance of one then you should initialize your weights with this amount
	- w = np.random.randn(n) / sqrt(n)
	- where n is the number of its inputs

**Xavier initialization**
- Better for tanh or sigmoid?
- Considers number of units in the previous layer and the next layer

**Kaiming He initialization**
- For ReLU we need to use additional factor of 2
```
# nn.init.kaiming_normal_
w = np.random.randn(n) / sqrt(2.0 / n)
```

Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification
https://arxiv.org/abs/1502.01852

**Initializing the biases**
- See below YuNet example


# PyTorch


**Why we need this call?**
- nn.init.kaiming_normal_
- https://colab.research.google.com/drive/1kLdAnk439XbTCSvn_QpsZKYW-i_oVKpw#scrollTo=UHM7Jk89lQAO
- https://chatgpt.com/c/9ced676c-a251-4437-9d43-3b7eb27dfe2a
- LeCun uniform initialization vs. Xavier initialization
- Uniform vs. Normal
	- nn.init.kaiming_normal_ vs. init.kaiming_uniform_

```
init.kaiming_uniform_(self.weight, a=math.sqrt(5))
```
https://pytorch.org/docs/stable/_modules/torch/nn/modules/linear.html#Linear


**Init weights in PyTorch**
- Pytorch should we initialize weights or we can use default?
- https://stackoverflow.com/questions/49433936/how-do-i-initialize-weights-in-pytorch
- `torch.nn.init`
- `torch.nn.init.xavier_uniform`
- self.apply pytorch
- [[YuNet]]
	- https://github.com/ShiqiYu/libfacedetection.train/blob/master/mmdet/models/dense_heads/yunet_head.py
	- https://chatgpt.com/c/9ced676c-a251-4437-9d43-3b7eb27dfe2a
	- nn.init.xavier_normal_
		- Why not Kaiming if it use ReLU?
		- The use of Xavier initialization in a network designed with ReLU activations does not necessarily indicate a mistake or oversight.
	- m.bias.data.fill_(0.02)
		- Initializing the bias to a small constant like 0.02 rather than zero can help avoid initial dead neurons in case of using ReLU activations or its variants.
