
# External Links


# Paper

VNect: Real-time 3D Human Pose Estimation with a Single RGB Camera
Dushyant Mehta, Srinath Sridhar, Oleksandr Sotnychenko, Helge Rhodin, Mohammad Shafiei, Hans-Peter Seidel, Weipeng Xu, Dan Casas, Christian Theobalt
https://arxiv.org/abs/1705.01583
Citations (780)

# Parent


# Links

Same authors
- Monocular 3d human pose estimation in the wild using improved cnn supervision


# Summary

single-image
real-time

# Overview

https://chatgpt.com/c/390b76fc-abf6-4d76-9a02-d867b9d39bff

MoCap
marker-less motion capture methods

RGB-D cameras
- valuable depth data

temporally consistent global 3D human pose


Model
- Pose Regression
	- network predicts 2D heatmaps and 3D location maps for each joint
	- 2D heatmaps
		- heatmap based methods
		- vs. 2.5D heatmap
			- [[AssemblyHands]]
	- 3D location maps
		- set of three maps
		- root-relative 3D coordinates
			- coordinates of the joint in 3D space relative to the root joint (typically the pelvis)
		- vs. direct regression
	- Reading from 3D Location Maps
		- first get 2d coordinate
- Kinematic Skeleton Fitting

Metrics
- 3D Percentage of Correct Keypoints (PCK)
- Mean Per Joint Position Error (MPJPE)
	- sensitive to outliers and large errors
- Area Under the Curve (AUC) for 3D PCK


Datasets
- MPI-INF-3DHP
- Human3.6M
- [[MPII Human Pose]]