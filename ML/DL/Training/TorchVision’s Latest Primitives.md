
# Links

[[PyTorch]]
[[How to Train Your ResNet]]

# Papers


Bag of Tricks for Image Classification with Convolutional Neural Networks
- https://arxiv.org/abs/1812.01187


# Overview

How to Train State-Of-The-Art Models Using TorchVision’s Latest Primitives
- https://pytorch.org/vision/0.20/models.html
- https://pytorch.org/blog/how-to-train-state-of-the-art-models-using-torchvision-latest-primitives/
- November 18, 2021
- prototype API
	- from torchvision import prototype as P
- Along with the weights, we store useful meta-data (such as the labels, the accuracy, links to recipe etc) and the preprocessing transforms necessary for using the models.
- newly introduced primitives of TorchVision
- The Training Recipe
- Methodology
	-  greedy search vs. grid search
	- There is a risk of overfitting the validation dataset
- Incremental improvements
	- LongTraining gives the largest improvement (can be misleading, see below)
- LR optimizations
	- SequentialLR scheduler
- Augmentations
	- “Automatic-Augmentation” techniques
	- TrivialAugment
- Longer training
	- Longer training cycles are beneficial when our recipe contains ingredients that behave randomly.
	- Just increasing the number of epochs on top of the old baseline won’t yield such significant improvements.
- Random Erasing
	- https://chatgpt.com/c/685fd045-92c0-8000-b389-b0c0a4d723b4
	- Random Erasing vs. CutOut
- Label Smoothing
	- PyTorch’s newly introduced CrossEntropyLoss label_smoothing parameter
- FixRes
	- Fixing the train-test resolution discrepancy
		- https://arxiv.org/abs/1906.06423
		- existing augmentations induce a significant discrepancy between the typical size of the objects seen by the classifier at train and test time
	- reduce the training resolution
- EMA
	- [[Exponential Moving Average (EMA)]]
	- EMA of the model weights
	- PyTorch’s AveragedModel class

