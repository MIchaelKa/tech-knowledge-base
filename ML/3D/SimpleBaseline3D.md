
# External Links


A Simple Yet Effective Baseline for 3D Human Pose Estimation
https://arxiv.org/abs/1705.03098
Citations (1186)

v1
https://chatgpt.com/c/6dda032c-35fd-4b9d-8d80-83adb8fd3b14

v2 + paper
https://chatgpt.com/c/5587f998-d763-4bb7-8ba3-98968b7a1568


# Links

[[3D Human Pose Estimation (3DHPE)]]

2d
- Stacked hourglass networks for human pose estimation.

e2e approaches
- Coarse-to-fine volumetric prediction for single-image 3D human pose.
- Structured prediction of 3d human pose with deep neural networks.
- VNect?
- 3d human pose estimation from a single image via distance matrix regression
	- distance matrix (DM)

# Data

Human3.6M

# Previous works

Depth
- [[Depth Estimation]]

# Overview


3d human pose estimation from a single image

Lifting
- Introduce the idea of lifting 2D keypoints to 3D
- e2e approaches, where is error come from?
- decoupling 3d pose estimation

decoupling 3d pose estimation
- 2d pose estimation
- 3d from 2d


# Camera coordinates

camera coordinate frame

Relation to the camera frustum
- [[MVSNet]]

Estimating 3D joints directly in the camera coordinate frame.
What does it mean "*estimating 3d joints in the camera coordinate frame*"?
- camera at the origin (0, 0, 0)
- define X, Y, Z axis
- 3D joint coordinates are expressed as (X, Y, Z) relative to this frame

Pre-processing
- *rotating and translating the 3d ground-truth according to the inverse transform of the camera*
- in some datasets, the ground truth (GT) coordinates for 3D joints are provided in a global coordinate space
- Camera's Position and Rotation
	- In datasets like Human3.6M or other motion capture datasets, this information is typically provided as part of the metadata



# Model

Linear layer
- *applied directly to the input, which increases its dimensionality to 1024*
	- applied directly to 2d coordinates
	- can we use embedding instead?
	- See 2d detections
- 4 - 5 million trainable parameters
- input
	- only set of 2d joint coordinated
	- no information from the image

2d detections
Cons
- carry less information
Pros
- low dimensionality makes them very appealing

vs. PnP
Can we apply PnP method instead of using liner layer?
- PnP generally assumes that the 3D model is fixed and known.
- To use if for 3DHPE we would need to have known joint coordinates for all possible poses.
- We can use it for pose estimation of object as a whole.