
# Внешние ссылки

**Paper**
Med3D: Transfer Learning for 3D Medical Image Analysis
https://arxiv.org/abs/1904.00625

GH
https://github.com/Tencent/MedicalNet

PwC
https://paperswithcode.com/paper/med3d-transfer-learning-for-3d-medical-image
https://paperswithcode.com/dataset/3dseg-8

# Network arch

Using [[ResNet]] as a backbone
For both segmentation and classification tasks.

Do they use stride=2?

**DenseASPP** segmentation network

Using [[Dilated Convolution]] as in [[DeepLab]]

# Dataset

**3DSeg-8** dataset
Does it contain classification task?
No. Two reasons:
1 - Small number of classes comparing to ImageNet and other (_natural image domain_)
2 - Segmantation mask is a rich sourse of information, much better then a single label.

Example of different modalities: MRI and CT
magnetic resonance imaging (MRI)
computed tomography (CT)