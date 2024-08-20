
# External Links

https://t.me/ai_newz/999
- camera drift in ARKit?

[https://zju3dv.github.io/neuralrecon/](https://zju3dv.github.io/neuralrecon/)

# Paper

NeuralRecon: Real-Time Coherent 3D Reconstruction from Monocular Video
Jiaming Sun, Yiming Xie, Linghao Chen, Xiaowei Zhou, Hujun Bao
https://arxiv.org/abs/2104.00681
Citations (230)


# Parent

[[3D Reconstruction]]

# Links\

[[COLMAP]]

TSDF

visual-inertial SLAM systems
- tracking camera motion
- ORB-SLAM3

RGB-D
KinectFusion

# Linked papers

[[MVSNet]]

Reconstruction
- Atlas: End- to-End 3D Scene Reconstruction from Posed Image

# Summary

- dense 3D geometry
- real-time

Datasets
- ScanNet
- 7-Scenes

# Overview

previous methods
- estimate single-view depth maps separately on each key-frame
- fuse them later

this method
- TSDF fusion module
- sparse TSDF volumes
- GRU - gated recurrent units

previous depth map fusion approach
 - steps
	- get single-view depth maps from each key frame
	- fuse into a TSDF volume
	- Marching Cubes algorithm
		- reconstructed mesh can be extracted from the fused TSDF
- drawbacks
	- single-view depth maps are estimated individually on each key frame
		- even the view-overlapping is substantial
	- depth inconsistencies
	- redundant computation


this method
steps
- input sequence of images
- input corresponding camera poses estimated by a [[SLAM]] system
- unprojects the image features to form a 3D feature volume
- sparse convolutions to process the feature volume to output a sparse TSDF volume
	- sparse convolutions is the sane as [[Dilated Convolution]]
	- why TSDF volume is sparse?
- GRU
	- https://chatgpt.com/c/2dd1d6b8-7a46-4037-9a29-87696de294b5
	- way to aggregate 3D feature volume / TSDF volumes
		- Instead of simply averaging or linearly combining the features from different frames, the GRU selectively integrates information from the current frame with the accumulated information from previous frames
	- maintaining temporal consistency