
Moved
https://www.notion.so/FCOS-b6d5b1f05b7f423383671bc89a10a718

# External Links

`torchvision.models.detection.fcos_resnet50_fpn`
https://pytorch.org/vision/main/models/generated/torchvision.models.detection.fcos_resnet50_fpn.html#torchvision.models.detection.fcos_resnet50_fpn

GH
https://github.com/yqyao/FCOS_PLUS

# Paper

v1
FCOS: Fully Convolutional One-stage Object Detection
https://arxiv.org/abs/1904.01355
Zhi Tian, Chunhua Shen, Hao Chen, Tong He
Citations (3363)

v2
FCOS: A simple and strong anchor-free object detector
[https://arxiv.org/abs/2006.09214](https://arxiv.org/abs/2006.09214)


# Links

[[CenterNet]]
[[Group Normalization]]

DenseBox
https://arxiv.org/abs/1509.04874
Одна из первых попыток anchor-free?

# Overview

Summary
- Использует NMS, CenterNet не использует NMS.
- Novel center-ness branch.
- Shared Heads Between Feature Levels

FCOS vs. CenterNet
- Различный Map Encoding
	- (про Map Encoding смотреть ниже)
- NMS

FCOS vs. YOLOv1
- FCOS takes advantages of all points in a ground truth bounding box.
- Далее в статье: It is worth noting that FCOS can leverage as many foreground samples as possible to train the regressor.

BPR (best possible recall)
Upper bound of the recall rate that a detector can achieve

When we encode the ground truth, it is possible that a few ground truths may have encoded representation in the training sample due to encoding algorithm limitations.
- ?

GT Encoding
- we also have a 4D real vector t∗ = (l∗, t∗, r∗, b∗) being the regression targets for the location.
- в каких координатах вычисляется вектор t∗, в координатах фича мапы или в коодинатах картинки?

# Paper Explaned

FCOS - Anchor Free Object Detection Explained
https://learnopencv.com/fcos-anchor-free-object-detection-explained/

Keys
- solve object detection in a per-pixel prediction fashion, analogue to semantic segmentation
- The most popular anchor-free detector might be YOLOv1

GT Map Encoding
- Each output feature needs a corresponding label. The label should come from the ground truth.

GT to Classification Map Encoding
- If two bounding boxes overlap, the label of the smaller bounding box will be the label for classification. The smaller bounding box has fewer representations in the classification map. So it makes sense to prioritize it.
- [[Label Assignment]]

GT to Regression Map Encoding
- The model predicts the bounding box for the point where the class label is one.
- Среди всех каналов возможна только одна единичка?
- However, in the case of multi-level outputs, overlapping on the same feature map will be rare.
- All bounding boxes need not be encoded at all levels. Roughly, smaller bounding boxes will be encoded at larger feature maps and vice versa.

GT to Center-ness Map Encoding
- TBD

# Implementation

`torchvision.models.detection.fcos`

Разбираемся как распределяются gt между фича мапами.
Генерируем анкоры?
Каждый анкор соответствует пикселю в фичамапе

Почему анкоры не отцентрированы? Левый верхний анкор имеет центр в точке (0,0)