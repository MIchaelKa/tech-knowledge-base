
non-linearity

# External Links

https://chatgpt.com/c/66e4146e-7304-8000-aed8-13bcb407296f

# Links

[[cs231n]]

# Discussion

Why we need them?
- Allowing neural net to learn and model complex data patterns
- Without activation functions, a neural network would simply behave like a linear regression model

When to use Tanh over Relu?
- RNNs

Modern Activation Functions
- Swish
- GELU

# Overview

Sigmoid
Sigmoid is not great activation function to use.
Problems
- Saturated neurons kill the gradient.
	- Gradient is zero for large positive or negative number.
- Output is not zero centered.
	- Zig zag path.
	- ReLU is also not zero centered
- exp() is expensive to compute

tanh
tanh instead of sigmoid
- tanh push the values to be between −1 and 1
- scaled and shifted Sigmoid
- Still kills the gradient when saturated
- Zero centered!


ReLU
Rectified Liner Unit
$f(x)=max(0,x)$
Default recommendation but still have some problems
- Not zero-centered output
- Kills the gradient for negative input

Dead ReLU
- 26:00 cs231n winter 2016 lecture 5
- We can try to track it to run all your train dataset after some training and look at statistics of every single neuron.
- ~15-20% of neurons will never activates (for any sample in the dataset)
- Be careful with your learning rate!

Leaky ReLU
$f(x)=max(0.01x,x)$
Will not die!

PReLU
Parametric Rectifier ReLU
$f(x)=max(a*x,x)$
- a - learnable parameter
- Every neuron has its own alpha as it has its own bias.

Maxout neuron
$max(w_1^T*x+b_1,w_2^T*x+b_2)$
Problem
- doubles the number of parameters