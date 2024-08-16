
Stereo
Stereo Imaging

multi-view stereo (MVS)
deep multi-view stereo (DMVS)

Structure from motion (SfM)

# External Links


# Terms

stereo rig
disparity map


# Links

[[Depth Estimation]]

[[COLMAP]]


# Overview

**Multi-View Stereo (MVS)**
Reconstructs 3D surfaces from multiple images taken at different viewpoints.

# Structure from motion (SfM)

Structure from Motion vs. Motion estimation

Static scene
_in a static scene, an image taken by a camera that has moved is no different than an image taken by a second camera_
static requirement is important

corresponding points
- optical flow techniques such as `cv::calcOpticalFlowPyrLK`
- SIFT

OpenCV
_opencv_contrib/modules/sfm_

# Traditional CV

[[COLMAP]]

OpenCV

# DL

[[MVSNet]]

Cost volume
- https://chatgpt.com/c/6f1c64aa-a750-4d4a-a7bb-00c2cdca0386
- Introduced by *Daniel Scharstein and Richard Szeliski. A taxonomy and evaluation of dense two-frame stereo correspondence algorithms.*
- cost volume stereo matching