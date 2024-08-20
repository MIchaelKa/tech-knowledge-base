
# External Links


# Paper

HigherHRNet: Scale-Aware Representation Learning for Bottom-Up Human Pose Estimation
[https://arxiv.org/abs/1908.10357](https://arxiv.org/abs/1908.10357)

# Parent

[[HRNet]]

# Links


# Overview

Summary
- bottom-up pose tracking
	- [[Tracking]]
- bottom-up approach for human pose estimation
- scale variation problem
	- authors tackled the problem of scale variation in bottom-up pose estimation

Datasets
- CrowdPose

Solution for scale variation problem
- HRNet as the backbone
- multi-resolution heatmaps (2 heatmaps)
	- vs. [[FPN]]

CrowdPose
- authors state that this suggests bottom-up methods are more robust to the crowded scene over top-down methods

obscuration
- pose estimation even with obscuration

Tags
- output scalar tag
- close tag values form a group of keypoints which belongs to a specific person and distant tags values indicate belonging to keypoint groups of different persons
- The tags are calculated according to the “Associative Embedding” method
- Trained and predicted only for the lowest resolution heatmap

Associative Embedding
- Associative Embedding: End-to-End Learning for Joint Detection and Grouping
- https://arxiv.org/abs/1611.05424

Heatmaps
- high and low resolution
- during inference they are mean aggregated
- during training - loss aggregation from two heatmaps

Follow-Ups
- It possible to further improve the accuracy using approach from [[PointRend]]?

Issues
- Shirtless people with wooden background are not detected well in FasterRCNN