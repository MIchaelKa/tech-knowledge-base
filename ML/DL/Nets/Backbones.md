

ChatGPT
- https://chatgpt.com/c/6867c322-f908-8000-8210-8ad4d4c512aa

timm
- https://github.com/huggingface/pytorch-image-models
- https://huggingface.co/docs/timm/quickstart
- https://huggingface.co/spaces/timm/leaderboard
- https://timm.fast.ai/


# Edge


Links
- [[Neural Net Inference (NNI)]]
- [[Neural Net Optimization (NNO)]]
- [[Edge Device Inference]]

ML Tools
- https://www.notion.so/ML-Tools-b2242bc562cc4d86ac0e80e078e92e26

YUNet
- https://www.notion.so/SD-Object-detection-7467b0387f2546a9b260f08ddf08d2ed
- base - Params: 73.606K
- st4_l - Params: 0.238M
- [[YuNet]]
- https://github.com/ShiqiYu/libfacedetection.train/blob/master/mmdet/models/backbones/yunet_backbone.py

MobileNet
- https://pytorch.org/vision/0.20/models.html#table-of-all-available-classification-weights
- mobilenet_v3_large - 5.5M
- mobilenet_v3_small - 2.5M
- [[MobileNet]]

TFLite
- https://github.com/PINTO0309/onnx2tf
- https://github.com/omerferhatt/torch2tflite
- If the accuracy of the INT8 quantized model degrades significantly

MobileNetV3 and INT8
- https://chatgpt.com/c/6867cad2-2c58-8000-a92b-4e78191f4cb5
- MobileNetV3 heavily uses depthwise separable convolutions and swish/h-swish activations
- strong calibration dataset
- Why depthwise separable convolutions is a problem for int8 quantization?
	- INT8 quantization needs to map all these channels into the same fixed scale (or at best, one scale per tensor).
	- scale per tensor should work better for MobileNetV3?

calibration dataset
- you do not need true labels for the calibration dataset.
- you can use train data for calibration dataset

Architectures
- https://github.com/huggingface/pytorch-image-models
- https://chatgpt.com/c/6867cad2-2c58-8000-a92b-4e78191f4cb5
- [[MobileNet]]
- EdgeNeXt
	- https://arxiv.org/abs/2206.10589
- LCNet
	- https://arxiv.org/abs/2109.15099