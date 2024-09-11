
Stereo
Stereo Imaging

multi-view stereo (MVS)
deep multi-view stereo (DMVS)

Structure from motion (SfM)

# External Links

[[Learning OpenCV]]

# Parent

[[Depth Estimation]]

# Terms

stereo rig
disparity map


# Links


[[COLMAP]]


# Overview

Multi-View Stereo (MVS)
Reconstructs 3D surfaces from multiple images taken at different viewpoints.

MVS methods
- depthmap-fusion based
	- [[DTU]]


# Structure from motion (SfM)

Structure from Motion vs. Motion estimation

Static scene
_in a static scene, an image taken by a camera that has moved is no different than an image taken by a second camera_
static requirement is important

corresponding points
- optical flow techniques such as `cv::calcOpticalFlowPyrLK`
- [[SIFT]]

OpenCV
_opencv_contrib/modules/sfm_

# Traditional CV

[[COLMAP]]

OpenCV

Rectification
- TODO

# DL

[[MVSNet]]

