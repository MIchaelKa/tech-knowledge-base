

# Parent

[[Neural Net Inference (NNI)]]

# Overview

Selective loading
- selective loading of the model based on the device's capabilities
- https://chatgpt.com/c/40d92b2b-4104-4aa8-a460-974efbaec4bf

Options
- Apple ML stack
- coreml vs. custom framework
- onnx runtime vs. alibaba frameworks
- CPU vs. ANE vs. GPU

Inference on CPU
- 3rd party frameworks faster than Apple?
- Infer on cpu vs gpu in case of neural nets or on mobile
- How much gpu will faster and by how in ms, flops?

## Capacity


BOTEC
Supporting of old devices
Computational capacity on target devices

[[FLOPS]]

When you need to support old devices such as iPhone 7
How many networks we can infer at the same time on iPhone 7?
Devide the final value as the phone will be really hot, which factor?

Important moments
- Efficient algorithms
- Monitoring
	- [[Monitoring]]
    - Device models
    - Statistics of user's device models


# Example

iPhone7 object detector
- https://chatgpt.com/c/e6556f7c-5a4e-4ee8-9aae-616095dc9183
- GPU
    - iPhone 7's GPU can process up to 230 GFLOPS (single precision).
    - Rough estimate for a MobileNet SSD model could be around 1 billion FLOPs per inference.
    - inference time 1 / 230 = 4ms
- Sequential inference
    - Sum of the times taken by each layer
    - Do we need to consider this sequential nature at all? For GPU, for CPU?
- CPU
    - The Apple A10 Fusion CPU can deliver approximately **80 GFLOPS**
- Preprocessing
    - preprocessing on CPU!

iPhone 15 GFLOPS
- https://nanoreview.net/en/phone/apple-iphone-15
- ANE?
- CPU?
    - 1789.4 _**GFLOPS**_