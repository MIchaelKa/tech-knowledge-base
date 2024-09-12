
vs. Dead ReLU

[https://en.wikipedia.org/wiki/Vanishing_gradient_problem](https://en.wikipedia.org/wiki/Vanishing_gradient_problem)

[https://www.educative.io/answers/what-is-the-vanishing-gradient-problem](https://www.educative.io/answers/what-is-the-vanishing-gradient-problem)


# Links

[[cs231n]]
- ?

[[Weight Initialization]]
[[Activation Functions]]

# Overview

Reason
- Vanishing gradients on sigmoids.
- tanh problems
- Initialization with small random numbers
- RNN
- Deep networks

Solutions
- residual blocks
- LSTM
- Batch normalization\

Deep networks
- gradient (error signal) decreases exponentially
- effect of multiplying n of small numbers to compute gradients of the early layers in an n-layer network
- early layers train very slowly