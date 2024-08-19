
# Overview

MoCap
marker-less motion capture (MoCap) technology
animation

Localization of human joints in
- 2D
- 3D

Input
- single image(monocular) 
- multi-image pose estimation


Human Pose Estimation
- https://denred0blog.super.site/human-pose-estimation
- [[3D Human Pose Estimation (3DHPE)]]
- [[2D Human Pose Estimation (3DHPE)]]

Human mesh recovery
Human mesh recovery from images
[[Mesh-R-CNN]]

# Hands

Towards Accurate Alignment in Real-time 3D Hand-Mesh Reconstruction
https://arxiv.org/abs/2109.01723
https://t.me/ai_newz/731

[[AssemblyHands]]

Hand pose estimation via latent 2.5D heatmap regression.
https://arxiv.org/abs/1804.09534

# Metrics

AP / mAP
- Similarity metrics
	- OKS
	- PCKh?

PCKh
- head-normalized probability of correct keypoint
- Good explanation of metric in [[PoseTrack]] paper
- Introduced in [[MPII Human Pose]]

OKS
- See [[COCO]] for details

PCK
- 3D Percentage of Correct Keypoints

MPJPE
- Mean Per Joint Position Error
- sensitive to outliers and large errors

AUC
- Area Under the Curve (AUC) for 3D PCK

# Datasets

2D
- [[MPII Human Pose]]
	- 3D?
- [[COCO]]
- [[PoseTrack]]
- CrowdPose

3D
- [[Human3.6M]]
- MPI-INF-3DHP
- H3WB

more datasets
https://github.com/open-mmlab/mmpose

Format for 3D
https://chatgpt.com/c/f11aacbf-7459-496d-a274-9ef652293f6f

