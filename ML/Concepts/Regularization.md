
Moved
https://www.notion.so/M-Regularization-bd48dfeeee054e1f9ee846ef25d7e6df

# External Links

LASSO
https://en.wikipedia.org/wiki/Lasso_(statistics)

# Overview

Common pattern
1. add some kind of randomness
2. average out randomness

Regularizations
- L1 / L2
- [[Dropout]]
- [[Data Augmentation]]

Other ideas
- DropConnect
- Fractional Max Pooling
- Stochastic depth

# L1 / L2

L1 / L2
Restricts your weights to become an arbitrary large values.
If the network can arbitrary change the weights it can lead to overfitting.

L1
sparse solution
[[Feature Selection]]

# Questions


https://chatgpt.com/c/0ce49f17-d4d7-4ec9-8f0d-84318c444583

- It common practice in machine learning to use regularization techniques like L1 and L2 to avoid overfitting. Actually this techniques are just restricts the weights to become an arbitrary large values. Why when model is overfitted the values of the weight are large?
- Can you explain in more details why L1 Regularization can drive some weights to exact zeros but L2 cannot?
- Why the dropout is also reffered to the group of regularization techiques?
- What is pros of L2 to compare to L1?
- Why not to use L1 everytime?
- Why we need both?


Large weight values and overfitting
- Why large weight values leads to overfitting?
- [[Linear Regression]]
- [[Bishop (BOOK)]]
	- page 8.
- https://chatgpt.com/c/a58ef827-65ed-4c13-9ea4-6d9aebff5756
	- model is placing significant importance on specific features