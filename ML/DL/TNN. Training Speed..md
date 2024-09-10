
https://www.notion.so/TNN-e0987b21f1d742cfba3bcb2e04472c03

# Links

[[How to Train Your ResNet]]

[[CPU - Disk Bottleneck]]
[[DataLoader]]
[[Determinism]]

# Overview


cudnn.becnhmark
- `torch.backends.cudnn.benchmark = True`
- https://discuss.pytorch.org/t/what-does-torch-backends-cudnn-benchmark-do/5936
- benchmark mode is good whenever your input sizes for your network do not vary.

cudnn.deterministic
- [[Determinism]]