
# External

Moved
https://www.notion.so/YuNet-193cd0687206418faceec55b358caf89

Paper
YuNet: A Tiny Millisecond-level Face Detector
https://link.springer.com/article/10.1007/s11633-023-1423-y
2023

GH
https://github.com/ShiqiYu/libfacedetection.train/tree/master


# Integration

Links
- https://www.notion.so/SD-Object-detection-7467b0387f2546a9b260f08ddf08d2ed
- https://github.com/ShiqiYu/libfacedetection.train/blob/master/mmdet/models/backbones/yunet_backbone.py

Model
- base - Params: 73.606K
- st4_l - Params: 0.238M

OpenCV
- https://github.com/opencv/opencv_zoo/tree/main/models/face_detection_yunet
- https://docs.opencv.org/4.x/d0/dd4/tutorial_dnn_face.html

FaceDetectorYNImpl
- https://github.com/opencv/opencv/blob/master/modules/objdetect/src/face_detect.cpp

ChatGPT
- https://chatgpt.com/c/696a7523-bc98-8326-b543-c06a64a805f3
- YuNet normalization
	- YuNet really is trained and run on raw 0–255 images, and this is a deliberate design choice, not an oversight.
- точность keypoints

# Overview

YuNet vs. YOLOX
anchor free
data sampling strategy for model training

**Contradiction**
1 - tiny faces in the background are normally not needed in many applications
2 - backbone should focus on small faces in face detection

**Float precision**
fp32
как fp16 работает для маленьких моделей?
[[Mixed precision training (MPT)]]
[[Quantization]]

Почему не изучается в статье?
Тема отдельного исследования.
Как поступать на практике?

**Layers**

>Large faces are easier to detect due to their rich information, so **it is not necessary to have too many channels in Layer 4**, or some deeper layers.

Хотя мы и предсказываем маленькие лица с фичамап большего размера и меньшей глубины (Layer 2), мы получаем эти фичамапы c более глубоких фичамап - так работает FPN. Посыл в том что более глубокий фичамапы всегда важны, даже для мелких деталей.

**Blocks**
depthwise convolution and pointwise convolution
[[Separable Convolution]]

**Backbone**
No skip connections?
[[ResNet]]

