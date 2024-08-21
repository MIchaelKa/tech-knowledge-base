
high-resolution network
# External Links

https://denred0blog.super.site/human-pose-estimation/papers/hrnet

https://github.com/HRNet

https://github.com/leoxiaobin/deep-high-resolution-net.pytorch

Overview of Human Pose Estimation Neural Networks — HRNet + HigherHRNet, Architectures and FAQ — 2d3d.ai
https://towardsdatascience.com/overview-of-human-pose-estimation-neural-networks-hrnet-higherhrnet-architectures-and-faq-1954b2f8b249


# Paper

Deep High-Resolution Representation Learning for Human Pose Estimation
[https://arxiv.org/abs/1902.09212](https://arxiv.org/abs/1902.09212)
Ke Sun, Bin Xiao, Dong Liu, Jingdong Wang
Citations (3341)

# Parent

[[Pose Estimation]]
[[2D Human Pose Estimation (3DHPE)]]

# Links

[[HigherHRNet]]

[[CPN]]

# Linked papers

Deep High-Resolution Representation Learning for Visual Recognition
[https://arxiv.org/abs/1908.07919](https://arxiv.org/abs/1908.07919)

High-Resolution Representations for Labeling Pixels and Regions
[https://arxiv.org/abs/1904.04514](https://arxiv.org/abs/1904.04514)

DeepCut: Joint subset partition and labeling for multi person pose estimation.

Flownet 2.0: Evolution of optical flow estimation with deep networks.


# Terms

**FM**
Feature Maps
high-resolution feature maps
high-resolution **representations**

OHKM
online hard keypoint mining
[[CPN]]

# Datasets

- [[PoseTrack]]
- [[MPII Human Pose]]
- [[COCO]]

# Metrics

AP
PCKh@0.5

# Overview

high-to-low resolution network
top-down approach

Architecture
- Feature maps of high-resolution is kept during forward pass. Low-resolution FM processed in parallel. There is exchange of information between parallel paths (subnetworks).
	- Q: Is it computationally heavy network? Is high-resolution FM has low number of layers?
- HRNet is not recover the high-res FM from low-res FM.
	- Q: What the difference from UNet, just increasing number of high-res FM layers?
	- A: No any interruptions with processing of high-res FM.
	- A: Increasing number of layers with process high-res FM

Channels
- Two types of the network **HRNet-W32 and HRNet-W48.**
- 32 and 48 is the number of channels in high-resolution FM.
- One of the most important parameter.
- Q: Is the number of channels preserved in each subnetwork?


FM?
- top-down approach
- input: cropped image with human
- rectangular feature maps: 4:3 AR

Input image
- Input image is either 256 x 192 or 384 x 288

Heatmaps
- [[CenterNet]]
- One heatmap for each keypoint.
- Heatmap output size: 64 x 48 or 96 x 72

Loss
- MSE (mean square error)

GT
- GT generation with 2D Gaussian
- standart deviation: 1 pixel
- mean: gt coordinate


# Tracking

[[Tracking]]
[[Tracking Metrics]]

average time to track all bounding boxes in a frame: 1.14 sec

Propagation
- propagate the detected box into nearby frames by propagating the predicted keypoints according to the optical flows computed by FlowNet 2.0
- [[Optical Flow]]