
Grouped Convolutions

# Внешние ссылки

Moved
https://www.notion.so/Separable-Convolution-e0c770830f19446c9b9c22e215f6e03e

[https://towardsdatascience.com/a-basic-introduction-to-separable-convolutions-b99ec3102728](https://towardsdatascience.com/a-basic-introduction-to-separable-convolutions-b99ec3102728)

Groups, Depthwise, and Depthwise-Separable Convolution (Neural Networks)
https://www.youtube.com/watch?v=vVaRhZXovbw

# Parent

[[Convolution]]

# Термины

Groups

# Spatial

Spatial Separable Convolutions
- Split conv kernel (n,n) into two kernels (1,n) and (n,1)
- The main issue with the spatial separable convolution is that not all kernels can be “separated” into two, smaller kernels.

How can we tell if a given kernel K is indeed separable?
- more direct method is to treat the 2D kernel as a 2D matrix K and to take its [[Singular Value Decomposition (SVD)]]

# Depthwise

Depthwise separable convolutions
- Separate conv operation into two part depthwise and pointwise
- Depthwise - do not change the depth of an image, number of channels stay the same.
- Then use pointwise convolution using 1x1 kernel, we have them as many as many channels we need.


**Groups**

Plain Conv layer
Doubling number of features quadruple computations

9x times faster
depends on feature count

# Pytorch

depthwise convolution pytorch

How to modify a Conv2d to Depthwise Separable Convolution?
[https://discuss.pytorch.org/t/how-to-modify-a-conv2d-to-depthwise-separable-convolution/15843](https://discuss.pytorch.org/t/how-to-modify-a-conv2d-to-depthwise-separable-convolution/15843)

`groups` parameter
https://pytorch.org/docs/0.3.1/nn.html#torch.nn.Conv2d

v2
At groups=in_channels, each input channel is convolved with its own set of filters (of size out_channels // in_channels).

v1
The configuration when groups == in_channels and out_channels = K * in_channels where K is a positive integer is termed in literature as depthwise convolution.

Question
- Let's look at torch.nn.Conv2d layer
- Here is the documentation: https://pytorch.org/docs/0.3.1/nn.html#torch.nn.Conv2d
- If we make groups equal to in_channels, it's called Depthwise Separable Convolution, why in this case number of out_channels should be multiple of in_channels or this is not true, and the number of out_channels can be any?
Answers
- https://chatgpt.com/c/66e32dfb-8ab4-8000-aa99-8b1ebffe78f6
	- No such requirements anymore?
- Мы хотим получать нужно количество выходных каналов не используя pointwise
- Мы хотим чтобы размерность pointwise 1x1 сверток равнялась out_channels
- Почему размерность 1x1 сверток не может быть любой, а из количество не может просто равняться out_channels?