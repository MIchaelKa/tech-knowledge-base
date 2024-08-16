2016

# External Links


[https://github.com/colmap/colmap](https://github.com/colmap/colmap)

[https://colmap.github.io/](https://colmap.github.io/)

https://demuc.de/colmap/

https://paperswithcode.com/paper/structure-from-motion-revisited

Johannes L. Schönberger
https://demuc.de/

https://chatgpt.com/c/7c48434c-cbc4-4e43-9c61-dddefad39803

# Links

[[Depth Estimation]]
[[Stereo Imaging]]

# Gaussian Splatting

Using COLMAP with Gaussian Splatting
[[Neural Rendering]]

COLMAP-Free 3D Gaussian Splatting
https://arxiv.org/abs/2312.07504


# Papers

Structure-from-Motion Revisited
2016

Pixelwise View Selection for Unstructured Multi-View Stereo
2016

# Datasets

DTU
- 3D Reconstruction
- indoor DTU dataset

Tanks and Temples
- Point Clouds

# Overview

Software

COLMAP is a general-purpose, end-to-end image-based 3D reconstruction pipeline

3D reconstruction pipeline
- Structure-from-Motion (SfM)
- Multi-View Stereo (MVS)

SfM strategies
- incremental
- hierarchical
- global

Incremental Structure-from-Motion

Unordered images and Multi-view matching
- Unordered image collections
- unordered Internet photo collections
- Multi-view matching
- Structure-from-Motion (SfM) from unordered images
- Papers
	- Multi-view matching for unordered image sets, or How do I organize my holiday snaps?


# Pipeline


Step 1. Image Features
- Feature Extraction
	- SIFT
	- DL
		- Paper: *Discriminative learning of local image descriptors.*
	- binary features
		- ORB
- Feature Matching
	- tests every image pair
		- prohibitive for large image collections
		- Feature Matching can be a problem if we test every image pair and every image descriptor.
	- scalable and efficient matching
		- KD-Trees
			- their efficiency diminishes in higher dimensions, such as with SIFT descriptors
		- FLANN
			- [[Appropriate Nearest Neighbors (ANN)]]
		- Graph-Based Matching
	
- Geometrical Verification
	- RANSAC
	- Essential and Fundamental Matrices estimation
	- part of Step 2?
	- related to Two-View Geometry Estimation?

Step 2. SfM
Sparse Reconstruction
- Initial Pair Selection
	- select an initial pair of images with a high number of feature matches
	- Two-View Geometry Estimation
	- basic 3D structure
	- camera positions
		- [[Camera Calibration]]
- Incremental Reconstruction
	- incrementally adds more images
	- estimating their camera positions
		- [[Camera Calibration]]
	- Output
		- sparse 3D point cloud
		- camera poses for each image
	- Methods
		- solving the Perspective-n-Point (PnP)
		- 2D-3D correspondences
- Bundle Adjustment (BA)
	- non-linear optimization process that minimizes the reprojection error across all images
	- refine previous output
	- Levenberg-Marquardt

Step 3. Dense Reconstruction
- Depth Map Estimation
	- multi-view stereo (MVS) techniques
		- Semi-Global Matching (SGM)
		- PatchMatch Stereo
		- Can we benefit from using [[MVSNet]]?
	- vs. 3D structure from Step 2?
		- we need to get dense 3D point cloud
	- [[Depth Estimation]]
	- Can we benefit from using Monocular Depth Estimation (MDE) ?
- Fusing Depth Maps
	- Output: dense 3D point cloud
- Surface Reconstruction
	- Using dense point cloud to reconstruct a surface, represented as a 3D mesh
	- [[Mesh-R-CNN]]

Step 4
Texturing

Step 5
Automatic Camera Calibration
COLMAP automatically estimates both intrinsic parameters and extrinsic parameters during the SfM process.
[[Camera Calibration]]


Q:
- Depth Map Estimation on Step 3 (Dense Reconstruction) vs. getting 3D structure on Step 2 (SfM)
	- sparse 3D point cloud vs. dense 3D point cloud
- Why we cannot apply Step 3 (Dense Reconstruction) straightaway, without making Step 2 (SfM) since both of them use multiple images to find correspondences?
	- Camera Pose Estimation
		- Needed for rectification step.
		- We need rectified images before applying triangulation in depth estimation step
	- sparse 3D point cloud - starting point or reference for dense reconstruction
	- reduces the computational complexity of dense reconstruction
		- epipolar line searching?
- Can we benefit from using Monocular Depth Estimation (MDE) on Step 2
	- YEs
- Which algorithm they use on Step 2 for simultaneously getting 3D coordinated and camera positions?
	- Bundle Adjustment (BA) - ?
- Which algorithm they use on Step 2 to establish a basic 3D structure and camera positions
	- Two-View Geometry Estimation
- Does COLMAP use rectified images on the Step 3. Dense Reconstruction?
	- YES



3D structure on Step 2. SfM.
- sparse
	- Only key points are reconstructed
- points in the sparse cloud are generally very accurate, as they are derived from robust feature matches

Depth Map Estimation on Step 3. Dense Reconstruction.
- dense
- accuracy can vary depending on the quality of depth estimation

Two-View Geometry Estimation
- Essential and Fundamental Matrices estimation
- Rectified images are not typically required
- Triangulation
- Direct linear transformation (DLT)