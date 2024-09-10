
Moved
https://www.notion.so/M-Data-Normalization-94149dbe355f42d2b4ae8351e556aab8
https://www.notion.so/Subtract-the-mean-and-divide-by-std-c67e5ef3f4a34a37a52d3832db298f8e

Масштабирование
Стандартизация

Centering

Normalization
Scaling

Subtract the mean and divide by std

# External Links


Dataset processing examples
- https://www.kaggle.com/c/siim-covid19-detection/discussion/239918
- https://www.kaggle.com/c/rsna-miccai-brain-tumor-radiogenomic-classification/discussion/253000
- https://www.kaggle.com/iafoss/panda-16x128x128-tiles

min-max normalization
- https://en.wikipedia.org/wiki/Feature_scaling


# Links

[[Normalization]]

[[cs231n]]

# Summary

Centering
- Subtract the mean

Normalization
- Scaling
- Types
	- divide by std
	- min-max


# Overview

Which values to use?
- Should we use values from pertained dataset (ImageNet) or we need to compute these values(mean and std) using train dataset?
- Something in between?
- What about grayscale case where we have only one mean and one std for one channel?


How deviding by std work?
- Our variance becoming equal to 1
- $var(\sigma X) = \sigma^2 var(X)$
- [[Probability Theory]]

Какие значение использовать если не хотим считать статистику по датасету?
```
transforms.Normalize(mean=[.5], std=[.5])
```
https://github.com/MedMNIST/MedMNIST/blob/main/examples/getting_started.ipynb