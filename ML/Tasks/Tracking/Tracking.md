
# External Links


# Papers


# Links

[[Tracking Metrics]]

Video datasets
- Tracking and pose estimation on video
- Tracking and multiple-image pose estimation
- [[VideoPose3D]]
- [[AssemblyHands]]

# Datasets

https://chatgpt.com/c/1255df35-35cb-4bf4-b6fe-e507a187a883

[[MOTChallenge]]

LTFT
https://github.com/hertasecurity/LTFT

PETS dataset

[[PoseTrack]]

# Overview

SOT
MOT

[[SORT]]
[[DeepSORT]]

[[FairMOT]]

Flow-based pose tracking
- [[PoseTrack]]
- [[SimpleBaseline]]
- [[HRNet]]

# System

Multiple Object Tracking (MOT) system components
https://chatgpt.com/c/ae04d296-250d-4f3e-a9e3-354ccaf0bab9

Detector
- YoloX
Temporal tracking
- [[Optical Flow]]
- [[Kalman Filter]]
- SOT
	- KCF
- DL
	- LSTM networks
	- DL for Temporal tracking
Correspondence
- [[Hungarian Algorithm]]
- Network Flow
- Greedy bipartite matching
	- [[SimpleBaseline]]
- DL
	- [[DeepSORT]]
	- DL for Correspondence

Functional requirement
- Saving and tracking ID
- Re-id

Non-functional requirement
- Accurate location tracking
- Real time performance
- Edge devices


Temporal tracking
- Kalman Filter vs. Optical Flow
- Kalman Filter vs. KCF
    - Can we use SOT as a part of MOT (temporal tracking for MOT)

Optical Flow
- dense vs. sparse
- Dense optical flow calculations can be computationally intensive, which might be challenging for real-time applications.

# DL

Correspondence
- [[DeepSORT]]

Temporal tracking
- LSTM
- Temporal Convolutional Networks (TCNs)
	- convolutional layers along the temporal dimension
	- RNN vs. CNN
	- [[VideoPose3D]]

Tracking Everything Everywhere All at Once
https://arxiv.org/abs/2306.05422
Citations (78)


# Challenges

occlusion
- [[Kalman Filter]]
- [[PoseTrack]]


# Other

Why we need tracking-by-detection?
- Simply applying a detector designed for single image level (e.g. Faster-RCNN, R-FCN) to videos could lead to missing detections and false detections due to motion blur and occlusion introduced by video frames.
- [[SimpleBaseline]]
