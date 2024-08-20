

# Links

Point Clouds


[[3D Human Pose Estimation (3DHPE)]]

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

DL
- [[MVSNet]]
- [[Pix2Vox]]
- [[Mesh-R-CNN]]


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