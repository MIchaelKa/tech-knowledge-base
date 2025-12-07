
# External Links


# Paper

AssemblyHands
https://arxiv.org/abs/2304.12301

# Parent

[[3D Human Pose Estimation (3DHPE)]]
[[Pose Estimation]]

# Links

Assembly101: A Large-Scale Multi-View Video Dataset for Understanding Procedural Activities
https://assembly-101.github.io/


# Summary

multi-image

Dataset generation pipeline
- Volumetric annotation network
- Learnable triangulation methods

AssemblyHands
- new dataset
- 3.0M annotated images
- 490K egocentric images


# Overview

egocentric and exocentric images
- https://chatgpt.com/c/1ebe7630-dbce-45c6-80ea-216d78b4c967

feeding a temporal sequence of states into a recognition model.

pose as the state representation in recognizing actions

graph convolutional networks
- treat joints as nodes and bones as edges


video frames as as input
- temporal
- multi-image pose estimation
- [[Tracking]]


Volumetric annotation network
- https://chatgpt.com/c/232920d3-398a-4512-b5b8-1f7ddd1f4f90
- hand pose annotation model
- MVExoNet
- learnable triangulation methods
	- Learnable Triangulation of Human Pose
- volumetric feature aggregation
	- projection
	- intrinsic and extrinsic parameters of each camera are used
	

# Data

Datasets
- Assembly101

large-scale datasets for understanding egocentric activities
- EPIC-KITCHENS
- Ego4D
- Assembly101


# Evaluation

PCK
PCKh

Single-view baseline
- heatmap-based hand pose estimators
	- Paper: Hand pose estimation via latent 2.5D heatmap regression.
- 2.5D heatmap