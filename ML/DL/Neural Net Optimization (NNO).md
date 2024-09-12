
Edge device inferencing

# External Links

https://developer.apple.com/machine-learning/models/

https://www.notion.so/B-MLSD-Projects-3302e6e03f2b46e6b6e0baef9a9a863c

# Links

[[Edge Device Inference]]

# Overview

Summary
- Fusing of layers
- Using layers that supported by the platform/GPU/ANE

Compressing
- [[Quantization]]
- [[Pruning]]
- [[Knowledge Distillation]]

Quantization
- Do not quantize the first conv layer

Libs
- Quantization и pruning редко делают в ручную, обычно используют библиотеки.
	- [[Курс по ML System Design]]
- [enot.ai](http://enot.ai)
- OpenVINO
- ONNX
- NVIDIA Triton


Arch
- [[MobileNet]]
	- inverted residual modules
- [[Separable Convolution]]
	- depth-wise convolutions

