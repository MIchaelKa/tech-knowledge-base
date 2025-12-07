
# External Links


# Paper

PoseNet: A Convolutional Network for Real-Time 6-DOF Camera Relocalization
Alex Kendall, Matthew Grimes, Roberto Cipolla
https://arxiv.org/abs/1505.07427
Citations (88)

# Parent

[[3D Human Pose Estimation (3DHPE)]]
[[3D Reconstruction]]


# Links

[[DeepPose]]

[[Camera Calibration]]

[[SLAM]]
- links to the related papers


[[PnP]]

# Overview

6-DOF
- https://chatgpt.com/c/f1c8471d-7634-49ec-a25f-ce91e6766a37
- PoseNet is designed for 6-DOF camera pose estimation, but it can be applied to human pose estimation tasks as well. The network directly regresses the camera's 3D pose from RGB images. While primarily focused on camera pose, the architecture and approach have influenced subsequent human pose estimation work.


Overview
- monocular camera relocalization
- works in complex conditions where [[SIFT]] registration fails

Localization
- related to [[SLAM]]?

Method
- CNN
- regress the 6-DOF camera pose from a single RGB image

SfM
- structure from motion to automatically generate training labels
- [[Stereo Imaging]]


continuous pose
- ?


pose vector
- position x
- [[Quaternion]] q
- 7 dimensions in total

loss
- RMSE for x
- RMSE but q is normalized


Reference position for the pose vector
- https://chatgpt.com/c/a7c43aa2-811e-4011-b8b3-bd9967fa0c96
- arbitrary global reference frame
- Format for 3D in [[Pose Estimation]]
- *works only with known scenes that it seen during training?*
- [[NeRF]]
