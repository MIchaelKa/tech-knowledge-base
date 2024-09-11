
# External Links

https://research.facebook.com/publications/a-practical-stereo-depth-system-for-smart-glasses/

# Paper

A Practical Stereo Depth System for Smart Glasses
https://arxiv.org/abs/2211.10551

# Parent

[[Stereo Imaging]]

# Links

SotA networks
- RAFT-stereo
- GA-Net

computational photography
- 3D photography
- 3D computational photography effects
- [https://en.wikipedia.org/wiki/Computational_photography](https://en.wikipedia.org/wiki/Computational_photography)

The technology behind Cinematic photos
[https://research.google/blog/the-technology-behind-cinematic-photos/](https://research.google/blog/the-technology-behind-cinematic-photos/)

Online stereo calibration and rectification papers

# Linked papers

A taxonomy and evaluation of dense two-frame stereo correspondence algorithms
Daniel Scharstein and Richard Szeliski.

census
- Ramin Zabihand, John Woodfill. Non-parametric local transforms for computing visual correspondence. 1994
- Learning OpenCV? - Not found.

# Terms

deep multi-view stereo (MVS)

cost volume

[[MobileNet]]
MobileNetV2
inverted residual modules

stereo rig
disparity map

# Summary

- e2e

# Overview

Datasets
- [[KITTI]]
- [[Middlebury]]
- ETH3D

Task
- stereo disparity estimation
- e2e system

end-to-end system
- productionized end-to-end stereo depth sensing system
- smart glasses are paired with a mobile phone
- still not real-time?

end-to-end system steps
- pre-processing
- online stereo rectification
    - novel online rectification algorithm
- stereo depth estimation
	- fast disparity prediction via neural networks
	    - cost volume
    - fallback to monocular depth estimation if rectification failed

contributions
- design of e2e system
- novel online rectification algorithm
- novel robust online calibration and rectification algorithm
- identical downstream processing
    - co-design a stereo network and a monocular depth network

# Depth

Stereo and monocular depth neural networks
[[Depth Estimation]]

Stereo
- need rectification
- stereo matching
    - replace handcrafted features such as census
    - MC-CNN
- end-to-end deep learning stereo
    - 2D CNN
    - 3D CNN
        - 2 image for making volume?
        - [[MVSNet]] here?
    - RNN
        - RAFT-stereo
        - impractical to run on device


Monocular depth
- Vision transformers for dense prediction.
- Depth anything ?
- encoder-decoder architecture

# System

pre-processing steps
- factory calibration
- undistortion
- downsamling
    - resize?
- HDR bracketing
    - TODO

novel online rectification algorithm
- novel robust online calibration and rectification algorithm
- online calibration
    - _extrinsics can vary significantly_
    - how calibration is done?
    - focal lengths change with temperature

co-design
- identical downstream processing
- relative disparities normalized to 0..1


# Online rectification

[[Camera Calibration]]
calibration

TODO


# Networks

Monocular depth network architecture
UNet

Stereo network architecture
- cost volumes
    - Three-dimensional cost volumes
    - compare left and right feature distances via the cosine distance