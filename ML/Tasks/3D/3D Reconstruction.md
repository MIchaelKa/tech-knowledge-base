

# Links

Relation to [[3D Human Pose Estimation (3DHPE)]]

# Terms

Point Cloud
- How to align two point clouds?
	- See Metrics on this page

# Methods

General
- Active
- Passive

Input
- single-image
- multiple-images

Techniques
- Structure from Motion (SfM)
- Multi-View Stereo (MVS)
- Volumetric Methods
	- voxel grids
	- signed distance functions (SDF)

[[Depth Estimation]]
[[Stereo Imaging]]

[[COLMAP]]

DL
- [[MVSNet]]
- [[Pix2Vox]]
- [[Mesh-R-CNN]]


Indoor
- [[NeuralRecon]]

# Datasets

[[KITTI]]

[[DTU]]

Tanks and temples

Middlebury

ShapeNet

# Metrics

https://chatgpt.com/c/c47f190a-a2b4-462f-add3-2e919c28b032

Chamfer Distance (CD)
- mesh
- Why DTU is not using Chamfer Distance (CD)?
- Accuracy + Completeness

Accuracy and Completeness
- point cloud
- more granular evaluation of the quality of the reconstruction then CD

Outliers
- Chamfer Distance (CD) vs. Accuracy and Completeness
- Accuracy and Completeness
	- handle outliers independently in each direction
- Use median or a trimmed mean

2D Depth Metrics
- [[KITTI]]
- Absolute Relative Error (Abs Rel)
- Squared Relative Error (Sq Rel)

3D Geometry Metrics
- Completeness (Comp)
- Accuracy (Acc)
- Precision (Prec)
- Recall (Recall)

# Overview


Cost volume
- https://chatgpt.com/c/6f1c64aa-a750-4d4a-a7bb-00c2cdca0386
- Introduced by *Daniel Scharstein and Richard Szeliski. A taxonomy and evaluation of dense two-frame stereo correspondence algorithms.*
- cost volume stereo matching
- source: [[A Practical Stereo Depth System for Smart Glasses]]

TSDF vs. Cost volume

TSDF
- https://chatgpt.com/c/56f55d58-cddb-4b0e-840a-58906f4dc515
- Truncated Signed Distance Function (TSDF)
- KinectFusion
- Surfase extraction
	- the surface of the object is extracted from the TSDF by finding the zero-crossing points
- Format
	- TSDF values are typically stored in a 3D voxel grid
- Purpose
	- used primarily for representing the geometry of a 3D scene
- Volumetric Fusion
	- How to get TSDF data from depth data for Volumetric Fusion?


# Feature search

Linear feature search
Algorithms in OpenCV vs. algorithms from COLMAP
COLMAP
- [https://chatgpt.com/c/7c48434c-cbc4-4e43-9c61-dddefad39803](https://chatgpt.com/c/7c48434c-cbc4-4e43-9c61-dddefad39803)
- Semi-Global Matching (SGM) or PatchMatch
OpenCV
- semi-global block matching (SGBM)


# Merging

Q: How to merge depth maps from different images?

Steps
- Camera Pose Information
- Transform
	- Convert each depth map from its camera-centric coordinate system to a common world coordinate system.
- Redundancy
	- Redundant points in the point cloud
	- Outliers

Volumetric methods
- Truncated Signed Distance Function (TSDF)