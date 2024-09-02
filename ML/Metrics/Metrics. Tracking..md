
# External Links

https://github.com/cheind/py-motmetrics

MOTChallenge
https://motchallenge.net/

# Parent

[[Tracking]]

# Papers

Evaluating multiple object tracking performance: the CLEAR MOT metrics.
Keni Bernardin and Rainer Stiefelhagen
2008
CLEAR MOT

[[MOTChallenge]]
?

Performance Measures and a Data Set for Multi-Target, Multi-Camera Tracking
https://arxiv.org/abs/1609.01775
Citations (2295)
ID

# Metrics

CLEAR MOT
- MOTP
- MOTA

HOTA
- https://chatgpt.com/c/75d9d2f5-fb6d-4172-a40a-c50abd340996
- vs. MOTP and MOTA
- separates and jointly evaluates detection accuracy and association accuracy

CLEAR MOT vs. ID
- https://github.com/cheind/py-motmetrics
- Both metrics attempt to find a minimum cost assignment between ground truth objects and predictions.
- ID
	- solves the bipartite graph matching by finding the minimum cost of objects and predictions over all frames

ID
- Types
	- ID-MEASURE
	- IDF1
- https://chatgpt.com/c/0fd0579a-cef6-4134-87f8-f8f6e27f035a
- when to use
	- maintaining the identity of tracked objects across frames is crucial