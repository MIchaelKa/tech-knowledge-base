

# Links

[[Backbones]]
[[Edge Devices]]


# External

notion
- https://www.notion.so/Quantization-9dba8e9dc7f4496a8cf99850eb3f436e

onnxruntime quantization
- https://onnxruntime.ai/docs/performance/model-optimizations/quantization.html
- per_channel / channel

onnxruntime quantization example
- https://github.com/microsoft/onnxruntime-inference-examples/tree/main/quantization/image_classification/cpu

huggingface
- https://huggingface.co/docs/optimum/concept_guides/quantization
- accumulation data type
- For instance the value of epsilon in `LayerNorm` is usually very small
- affine quantization scheme
- To learn how the quantization parameters `S` and `Z` are computed
	- blog post
	- papers
- Per-tensor and per-channel quantization
- Calibration
	- Post training dynamic quantization
	- Post training static quantization
	- Quantization aware training

# ChatGPT

ChatGPT
- https://chatgpt.com/c/691f1206-ea80-832d-87b0-2e4e98eca614
- QOperator vs. QDQ
- What’s the point of QuantizeLinear → DequantizeLinear pairs?
	- Enable QAT (Quantization-Aware Training)
- Runtime can fuse away the QDQ pairs

ChatGPT v2
- https://chatgpt.com/c/691f15eb-f608-8333-af36-2d72b8b98986
- In that case, you’re essentially simulating quantization noise but still computing in float32.
- Find patterns `DQ -> Conv -> Q` and fuse them into integer kernels using int8 weights and activations

Q

- QDQ is basically a way to annotate the graph with quantization information per tensor, while keeping the main ops (`Conv`, `MatMul`, etc.) in their original form.
- Thats's why you see 3 input DequantizeLinear for each operation, you need Dequantize weights also

- Why the size of the quantized model with QDQ is less than the original model if the main ops are saved in the original form?
- int8 is stored

- Why QDQ is preferred over QOperator for accuracy

- Am I right that after fusing at inference time we will use the same operators as in QOperator?

- What is Y_scale, Y_zp. What the difference between Y_scale, Y_zp and W_scale, W_zp?
- W - weights
- Y - outputs
- X - inputs

Storing quantization parameters

- Why we need to store W_scale, W_zp, Y_scale, Y_zp for weights in QOperator? Why we cannot convert them one time to int8 and forget about those values?
- After an int8 convolution, you get an **int32 accumulator**, which must be rescaled into the next layer’s quantization range. That requires **Y_scale, Y_zp**.

- `W_int8 = 51` tells you absolutely nothing unless you also know
- Why I need float32 weight for quantized operation if we always perform the operation in int8 space? Just to be able to dequantize the result? That if we do not need to dequantize it?

- Same int8 number → totally different fp32 meaning.
- Why it's important if scale and zero point should not change for the certain operator weight's once it calculated?


- Why we need to store W_scale, W_zp for weights in QOperator? Why the scheme on my picture do not work? 
- https://chatgpt.com/c/691f2259-5204-8326-93c4-0a4bb669bf19
- The matmul/conv using `x_q` and `W_q` has no idea what real numbers those ints correspond to.

- Why we cannot pre-compute (W_q​−z_W​) * s_W?
- Because precomputing that gives you float weights again

- Why we cannot pre-compute (W_q​−z_W​) and throw away z_W?
- W_q may no longer fits into int8
- All kernels assume standard (tensor, scale, zp) format

- Am I right that this is because we always need to get output in float32 first (which should approximate the output before quantization) and only than convert it to int8 using it's own Y_s and Y_z?
- This α is used to convert the accumulator to the next int8 tensor.



# Overview

MobileNetV3 and INT8
- https://chatgpt.com/c/6867cad2-2c58-8000-a92b-4e78191f4cb5
- MobileNetV3 heavily uses depthwise separable convolutions and swish/h-swish activations
- strong calibration dataset
- Why depthwise separable convolutions is a problem for int8 quantization?
	- INT8 quantization needs to map all these channels into the same fixed scale (or at best, one scale per tensor).
	- scale per tensor should work better for MobileNetV3?

Calibration dataset
- you do not need true labels for the calibration dataset.
- you can use train data for calibration dataset