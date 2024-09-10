

# Links

[[Transformer]]
[[ResNet]]

[[Identity Mappings in Deep Residual Networks]]


# Activation function

Pre-Activation Residual
- https://habr.com/ru/articles/599057/
- https://www.researchgate.net/figure/Architecture-of-normal-residual-block-a-and-pre-activation-residual-block-b_fig2_337691625
- https://towardsdatascience.com/resnet-with-identity-mapping-over-1000-layers-reached-image-classification-bb50a42af03e

pre/post activation residuals
- post activation residuals
	- in original resnet activation comes after residual
- pre activation residuals
	- improved
	- improved gradient flow w/o ReLU
- Но какая разница если после выхода блока то что подается в сумму уже прошло через ReLU?
	- Разница есть так как будет меньше обнулений


Why original ResNet place ReLU after residual, why ReLU not inside the block?
- https://chatgpt.com/c/66df2c56-1640-8000-be8e-45f03decb21b

# Normalization

pre/post normalization
- pre is better
- normalization before or after activation
	- https://chatgpt.com/c/66dedef4-c824-8000-a3c4-f8e26e8e2e27
- batch normalization should be applied before or after activation?
	- https://chatgpt.com/c/66e082b7-66e0-8000-8437-b1ab9cde8057
- pre pros
	- prevents saturation of non-linearities
		- preventing exploding or vanishing gradients
		- valid only for sigmoid?
		- valid for ReLU also, imagine shift when all activations is negative
- normalization before or after residual
	- [[Transformer]]


