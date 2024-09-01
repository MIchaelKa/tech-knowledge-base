

# External Links

https://paperswithcode.com/dataset/dtu

DTU Robot Image Data Sets
https://roboimagedata.compute.dtu.dk/?page_id=36

# Summary

2014

# Links

[[3D Reconstruction]]

[[Stereo Imaging]]

[[COLMAP]]

# Paper

Large Scale Multi-view Stereopsis Evaluation

# Overview


indoor DTU dataset
aimed at multiple view stereo (MVS) evaluation

- 80 scenes of large variability
- 49 or 64 accurate camera positions and reference structured light scans
- all acquired by a 6-axis industrial robot
- rectified images
	- 30000 rectified images


Structured Light Scanning
- structured light scans
- structured light scanner
- https://chatgpt.com/c/c47f190a-a2b4-462f-add3-2e919c28b032
- How it works
	- Projection of Patterns
		- light patterns (usually stripes or grids)
	- Deformation Measurement
	- 3D Reconstruction


# Evaluation

Metrics
- Accuracy and Completeness

Missing data
- observability mask

Sampling
- more 3D points around strongly textured surface regions
- bias in the evaluation

Meshed surfaces