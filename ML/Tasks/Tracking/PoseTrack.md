
# External Links


# Paper

Posetrack: Joint multi-person pose estimation and tracking.
https://arxiv.org/abs/1611.07727
Citations (198)
# Parent

[[Tracking]]
[[2D Human Pose Estimation (2DHPE)]]

# Links

DeepCut: Joint subset partition and labeling for multi person pose estimation.

# Summary

No re-identification
Video
Tracking + Pose

Datasets
- PoseTrack2017

Metrics
- Pose
	- PCKh
	- mAP
- Tracking
	- [[Tracking Metrics]]
	- CLEAR MOT
	- trajectory-based measures

# Overview

Metrics
- Pose
	- PCKh
		- good explanation in this paper
	- mAP
		- as it done in DeepCut
- Tracking
	- CLEAR MOT
		- good explanation in this paper
	- trajectory-based measures
		- ?

Evaluation
- New protocol
	- Derived from DeepCut?
- Occlusion handling

PoseTrack2017
- based on the raw videos provided by the popular MPII Human Pose dataset
	- [[HRNet]]
- keyframe
	- keyframe from the MPII Pose dataset
- Unique ID
	- We assign a unique identity to every person appearing in the video.
- No re-identification


# Method

*In contrast to previous works, we aim to solve the association of each person across the video and the pose estimation together.*

spatio-temporal graph
- densely connected spatio-temporal graph
- connecting body joint candidates spatially as well as temporally

ILP
The optimization problem is formulated as a constrained Integer Linear Program (ILP)
[[Linear Programming]]