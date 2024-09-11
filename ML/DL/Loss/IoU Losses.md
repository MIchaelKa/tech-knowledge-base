
# External Links

Distance-IoU Loss: An Improvement of IoU-based Loss for Object Detection Bounding Box Regression
https://medium.com/nodeflux/distance-iou-loss-an-improvement-of-iou-based-loss-for-object-detection-bounding-box-regression-4cbdd23d8660

IoU Loss Functions for Faster & More Accurate Object Detection
https://learnopencv.com/iou-loss-functions-object-detection/


# Parent

[[Loss. SS and OD]]

# Overview

Why MSE/MAE losses is bad?
- Same error for large and small objects.
- Relative Error
	- Относительные координаты не спасают положение.
		- Почему?
	- [[Учебник по машинному обучению (Яндекс)]]
	- Can we use similar on MAPE approach?
		- https://chatgpt.com/c/66e1d628-e1b0-8000-82d4-a78c1b257089
		- It doesn't account for the shape or aspect ratio of the predicted box versus the ground truth box.


## GIOU

Paper
- Generalized Intersection over Union: A Metric and A Loss for Bounding Box Regression
- [https://arxiv.org/abs/1902.09630](https://arxiv.org/abs/1902.09630)
- Hamid Rezatofighi, Nathan Tsoi, JunYoung Gwak, Amir Sadeghian, Ian Reid, Silvio Savarese

Summary
- If IOU is 0, the loss is not fixed; instead, it depends on how far the prediction and ground truth boxes are.
	- Это преимущество перед обычным IOU лоссом.
	- Нам это не нужно в случае Multibox loss, где лосс считается только для позитивных прайоров?
- C denotes the smallest box that can enclose predicted and ground-truth bounding box

## DIoU

Paper
- Distance-IoU Loss: Faster and Better Learning for Bounding Box Regression
- [https://arxiv.org/abs/1911.08287](https://arxiv.org/abs/1911.08287)
- Zhaohui Zheng, Ping Wang, Wei Liu, Jinze Li, Rongguang Ye, Dongwei Ren

Summary
- Distance IoU
- DIoU loss pushes the prediction center to the ground truth center.
- GIoU loss generally increases the size of predicted box to overlap with target box

## CIoU

Paper
- Enhancing Geometric Factors in Model Learning and Inference for Object Detection and Instance Segmentation
- [https://arxiv.org/abs/2005.03572](https://arxiv.org/abs/2005.03572)
- Zhaohui Zheng, Ping Wang, Dongwei Ren, Wei Liu, Rongguang Ye, Qinghua Hu, Wangmeng Zuo

Summary
- Centric IoU
- Accounts for aspect ratio

## EIoU

Paper
- A Systematic IoU-Related Method: Beyond Simplified Regression for Better Localization
- [https://arxiv.org/abs/2112.01793](https://arxiv.org/abs/2112.01793)
- Hanyang Peng, Shiqi Yu

Summary
- Extended-IoU Loss
- [[YuNet]]
- https://github.com/ShiqiYu/libfacedetection.train/tree/master