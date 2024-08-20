

# Links

Relation to [[3D Human Pose Estimation (3DHPE)]]

# Terms

Point Cloud
- How to align two point clouds?
	- See Metrics on this page

# Methods

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


# Overview


Cost volume
- https://chatgpt.com/c/6f1c64aa-a750-4d4a-a7bb-00c2cdca0386
- Introduced by *Daniel Scharstein and Richard Szeliski. A taxonomy and evaluation of dense two-frame stereo correspondence algorithms.*
- cost volume stereo matching

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

