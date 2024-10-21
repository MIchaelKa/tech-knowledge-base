
# External

Paper
- Dynamic Head: Unifying Object Detection Heads with Attentions
- https://arxiv.org/abs/2106.08322
- Microsoft
- Citations (416)


# Links

[[Attention]]

[[FCOS]]
- proposed to use center representations
	- ?

[[EfficientDet]]

New papers
- Bridging the gap between anchor-based and anchor-free detection via adaptive training sample selection.
- Centernet: Keypoint triplets for object detection.

# Overview

Benchmarks
- [[COCO]]

Model
- ResNeXt-101-DCN backbone
	- Good for production?

DCN
- Deformable Convolutional Networks
- [[Deformable Convolution]]

Summary
- focus on improving object detection head
- multiple self-attention mechanisms
- unified head

Results
- 1/20 training time

Challenges
- Types
	- scale-awareness
	- spatial-awareness
	- task-awareness
- unified head that can address all these problems simultaneously


task-awareness
- different representation of objects
	- representations
		- bb
		- center
		- corner points
			- TODO
	- various representations of objects could potentially improve the performance
- classification vs. detection
	- ?

Tensor
- output of a backbone
- input of a head
- dimensions
	- level × space × channel
	- space = h x w
- self-attention mechanism over this tensor
	- high computational cost
- solution
	- deploy attention mechanisms separately on each particular dimension of features

Attention
- level-wise
	- scale-awareness
- space-wise
	- spatial-awareness
	- [[ViT]]
- channel-wise
	- task-awareness
	- [[SENet]]

multiple self-attention mechanisms
- applied sequentially