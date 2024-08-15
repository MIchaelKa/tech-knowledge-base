Karlsruhe Institute of Technology and Toyota Technological Institute

kitti dataset
kitti 360

2012-2015

# External Links

https://www.cvlibs.net/datasets/kitti/

https://paperswithcode.com/dataset/kitti

https://chatgpt.com/c/4431778b-8f6f-4ccf-a493-8b297e2bbca2

# Papers

Are we ready for Autonomous Driving? The KITTI Vision Benchmark Suite (CVPR 2012).

Vision meets Robotics: The KITTI Dataset

Object Scene Flow for Autonomous Vehicles (CVPR 2015).

# Linked papers

Depth Map Prediction from a Single Image using a Multi-Scale Deep Network
https://arxiv.org/abs/1406.2283
Citations (3604)
SILog

# Summary


# Links

Tasks
- Stereo
	- [[Stereo]]
	- [[Depth estimation]]
- Optical Flow
- Visual Odometry
	- GPS
- 3D Object Detection
	- [[3D Object Detection (3DOD)]]
- 3D tracking
	- [[Tracking]]

DNB
- Middlebury

[[Kubric]]

Bird’s-Eye-View Transform
- calculated?

# Overview

Domains
- mobile robotics
- autonomous driving

Collecting the data
- stereo camera rig
- hours of traffic scenarios recorded with variety of sensor modalities
- the dataset itself does not contain ground truth for semantic segmentation

Sensor modalities
- high-resolution RGB
- grayscale stereo cameras
- 3D laser scanner
	- vs LIDAR

Tasks
- stereo
- optical flow
- visual odometry
- 3D Object Detection
- 3D tracking

Details
- stereo
- optical flow
	- 200 image pairs for train and test
	- challenges
		- Non Lambertian surfaces
		- Reflecting surfaces
		- Large feature displacements
	- Occluded objects ?
- visual odometry
- 3D Object Detection
	- 3D bounding boxes
		- visible
		- occluded
		- truncated
	- classes
		- cars
		- vans
		- tracks
		- pedestrian
- 3D tracking

Metrics
For each task evaluation metrics are provided

# Stereo
Stereo Evaluation

ground truth has been established in a semi-automatic process

rectified image pairs along with ground truth disparity maps generated using a LiDAR sensor

**Input**
two images

**Metric**
percentage of pixels with a disparity error greater than a certain threshold <3px or <5%

## Methods

**Paper**
OpenStereo
A Comprehensive Benchmark for Stereo Matching and Strong Baseline
https://arxiv.org/abs/2312.00343
Citations (5)

[[PANet]]

# Flow
Optical Flow Evaluation


# Depth


Depth Completion vs. Depth Evaluation in KITTI benchmark
Depth Completion vs. Depth Prediction in KITTI benchmark

# Depth Completion

filling in sparse depth maps with missing data to create dense depth maps

**Metrics**
- iRMSE
	- Root mean squared error of the inverse depth
- iMAE
- RMSE
- MAE

Why we want error of the inverse depth?

# Depth Prediction

- 93 thousand depth maps
- LiDaR scans
- RGB image

**Paper**
Sparsity Invariant CNNs (THREEDV 2017).

depth vs. stereo ?

DL
- large amount of training data
- training of complex deep learning models
- tasks
	- depth completion
	- single image depth prediction

**Input**
one image

## Metric

- Relative squared error (percent)
- Relative absolute error (percent)
- iRMSE
- SILog
	- scale invariant logarithmic error (SILog)
	- square root of the scale invariant logarithmic error (SILog).

Q:
Why we cannot use RMSE and MAE for evaluation of Depth Prediction task?
- **RMSE and MAE** are sensitive to the absolute scale of the depth values.
- relative errors are more important

**Logarithmic Differences**
*Depth perception is naturally more aligned with logarithmic differences rather than linear differences.*

logarithmic differences vs. relative or proportional differences

SILog

Q:
What is the benefits of using scale invariant logarithmic error (SILog) over Relative squared error (percent) or Relative absolute error (percent)?


# Comparison

Stereo Evaluation vs. Depth Evaluation in KITTI benchmark

- inputs: two or one image
- output: disparity map vs. depth map

*Stereo Evaluation focuses on disparity maps, which can be converted to depth, while Depth Evaluation focuses directly on depth maps.*

# Tracking

Metrics
HOTA, CLEAR MOT and MT/PT/ML

Multi-Object Tracking and Segmentation (MOTS)
[[SAM-2]]
21 training sequences and 29 test sequences
