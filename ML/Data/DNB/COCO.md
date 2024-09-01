
# External Links

cocodataset
[https://cocodataset.org/#download](https://cocodataset.org/#download)
[https://cocodataset.org/#format-data](https://cocodataset.org/#format-data)

# Paper

Microsoft COCO: Common Objects in Context
[http://arxiv.org/abs/1405.0312](http://arxiv.org/abs/1405.0312)

# Parent


# Links


# Overview


# Keypoints

COCO keypoint detection
COCO test-dev split

200K images
250K person instances
17 keypoints

Year?

## Keypoints fromat

(x, y, v)
v is a visibility flag

**scale**
Each ground truth object also has a scale s which we define as the square root of the object segment area.

## OKS

Object Keypoint Similarity

[https://cocodataset.org/#keypoints-eval](https://cocodataset.org/#keypoints-eval)

Core idea
- Mimic the evaluation metrics used for object detection: average precision (AP) and average recall (AR)
- Similarity measure
	- At the heart of these metrics is a similarity measure between ground truth objects and predicted objects.
	- OKS plays the same role as the IoU in object detection

Formula
- d - Euclidean distances between each corresponding ground truth and detected keypoint
- pass the d through an unnormalized Guassian with standard deviation $s*k$
	- s - object scale
	- k - per-keypont constant that controls falloff.

**Tuning**
*we measured the per-keypoint standard deviation σi with respect to object scale s*

Q:
how it was calculated?

A:
redundantly annotated images in val
different annotations from different annotators?

