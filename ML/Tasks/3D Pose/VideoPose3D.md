
# External Links


# Paper

3d human pose estimation in video with **temporal convolutions** and semi-supervised training
Dario Pavllo, Christoph Feichtenhofer, David Grangier, Michael Auli
https://arxiv.org/abs/1811.11742
Citations (855)


# Parent

[[3D Human Pose Estimation (3DHPE)]]

# Links


# Linked Papers

[[Coarse-to-fine volumetric prediction for single-image 3D human pose]]
- not e2e?

lifting
- [[SimpleBaseline3D]]

e2e
- [[Structured prediction of 3d human pose with deep neural networks]]

# Summary

Method
- [[SimpleBaseline3D]] + Video(CNN for sequence modeling)

# Overview

Datasetes
- [[Human3.6M]]
	- Has it video data?
- HumanEva-I

Metrics
- ?

Loss
- MPJPE Loss

Overview
- video
- back-projection
- 2D->3D lifting

problem of 2D->3D lifting
- multiple 3D poses can map to the same 2D key-points

video
- 3D poses in video
- temporal information from video
- temporal convolutions
- temporally consistent global 3D human pose
	- [[VNect]]

temporal
- [[SAM-2]]
- modeling temporal information with recurrent neural networks
- dilated temporal convolutions over 2D key-points
	- [[Dilated Convolution]]
- CNN vs. RNN
	- sequence modeling by CNN

unlabeled video
- [[Self-Supervised Learning (SSL)]]
- scheme to leverage unlabeled video
- back-projection
- machine translation
	- method is inspired by cycle consistency in unsupervised machine translation
	- round-trip translation into an intermediate language and back
- require camera intrinsic parameters
	- intrinsic parameters, which are often available for commercial cameras

# Related works

lifting
- Two-step pose estimation
- why lifting works better?
- benefit from intermediate supervision
- approaches
	- k-nearest neighbour search
	- simply predicting their depth
	- [[SimpleBaseline3D]]

video
- approaches
	- HoG features of spatio-temporal volumes
		- Paper: Direct prediction of 3d body poses from motion compensated sequences
	- learn from 2D keypoint trajectories
		- this paper
		- LSTM
			- Paper: Exploiting temporal information for 3d pose estimation
			- vs. TSDF

SSL
- GAN


# Method

Keys
- Do not uses heatmaps
	- allows the use of efficient 1D convolution over coordinate time series, instead of 2D convolutions over individual heatmaps

Architecture
- Do not uses [[Hourglass]]
- Mask R-CNN
- [[CPN]]

Input
- sequence of 2D poses

CNN vs. RNN
- CNN enable parallelization over both the batch and the time dimension
- RNNs cannot be parallelized over time.

# SSL

auto-encoding problem on unlabeled data
2D -> 3D -> 2D

two objectives are optimized jointly
- superwised
- unsuperwised

Trajectory model