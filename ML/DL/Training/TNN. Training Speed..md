
https://www.notion.so/TNN-e0987b21f1d742cfba3bcb2e04472c03

# Parent

[[Training Neural Networks (TNN)]]
[[ML Accelerating (MLA)]]
# Links

[[How to Train Your ResNet]]

[[CPU - Disk Bottleneck]]
[[DataLoader]]
[[Determinism]]

[[GPU Environment]]

[[Mixed precision training (MPT)]]

# Overview

What can slow down your training
- Pre-processing
	- [[Resize]]
	- High resolution resizing takes a lot of time.

# PyTorch

cudnn.becnhmark
- `torch.backends.cudnn.benchmark = True`
- https://discuss.pytorch.org/t/what-does-torch-backends-cudnn-benchmark-do/5936
- benchmark mode is good whenever your input sizes for your network do not vary.

cudnn.deterministic
- [[Determinism]]