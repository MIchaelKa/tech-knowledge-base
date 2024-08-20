simultaneous localization and mapping


# External Links

https://chatgpt.com/c/6a4c250a-406a-4228-81ee-f55b69bf2e51

# Links

[[3D Reconstruction]]
[[COLMAP]]

[[Kalman Filter]]


Methods
- EKF-SLAM
	- https://chatgpt.com/c/0904a982-2719-4a41-9f8f-dd2b1155b499
	- Extended Kalman Filter SLAM
- FastSLAM
- Graph-Based SLAM

Implementations
- ORB-SLAM

# Datasets

Odometry
- [[KITTI]]

# Terms

camera pose == robot pose

# Tutorial

SLAM opencv
- https://learnopencv.com/monocular-slam-in-python/
- [[COLMAP]]
- ORB-SLAM
	- [[ORB]]
- Fundamental matrix computation
	- 8 correspondence
	- [[SVD]]
	- [[RANSAC]]
- Triangulation
- Bundle Adjustment
	- similar to gradient descent
	- optimization techniques aimed at minimizing an error metric
	- minimizes reprojection error\
- Trajectory
	- ?

# Overview

SLAM vs. [[3D Reconstruction]]

SLAM
- Performance
	- prioritizes efficiency and real-time updating over high fidelity
- Sensor Fusion
	- SLAM combines data from multiple sensors (e.g., cameras, LiDAR, IMUs, odometry) to estimate both the device’s pose and the map.

Loop closure

Input
- Set of images

Output
- Find, the trajectory of the camera
	- set of camera poses
- Map environment


Feature matching
- Feature tracking can be used to replace feature matching
- [[OpticalFlow]]

