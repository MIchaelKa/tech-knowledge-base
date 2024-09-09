

https://www.notion.so/Normalization-b57f0cbcba854c04a4e205682a5cb4a6

Instance Normalization
[[Batch Normalization]]
[[Group Normalization]]
[[Layer Normalization]]


# External Links

PyTorch
https://pytorch.org/docs/stable/nn.html#normalization-layers

cs231n
- Batch Normalization
- Layer Normalization
	- assignment2/BatchNormalization.ipynb
	- https://colab.research.google.com/drive/1seNty-KhftHcgQiCMeeiB91PfNvAohi_
- Spatial Batch Normalization
- Group Normalization
	- assignment2/ConvolutionalNetworks.ipynb
	- https://colab.research.google.com/drive/10fmaBgZ_7J2A8G1qfDgpL98afzPHhpmn#scrollTo=K6-rDAvodZHd

# Links

[[NFNet]]

До или после активации?
- [[Network Topology]]

# Discussion

Можем ли мы уменьшить мантиссу?
- Нормализация приводит к тому что выходы слоев распределены внутри небольшого промежутка (например от -1 до 1). Как это может способствовать использованию меньшее float precision? Можем ли мы уменьшить **мантиссу** в данном случае?
- [[Floating-point Arithmetic]]


# Comparison

layer normalization vs. batch normalization
layer normalization vs. batch normalization vs. group normalization

x.shape = (N,C)

batch normalization
- Нормализуется каждая фича вдоль всех примеров (батча)
- mean.shape = (C,)

layer normalization
- Нормализуется каждый пример вдоль всех фичей
	- mean.shape = (N,)

# Small batch size and normalization

Как файтюнить обджект детекшн с батчем размера 1?
- batch_size=1
- Фризить батч-норм - переводить в eval mode
	- same as Frozen batch norm ?
	- see Freezing batch normalization
- Использовать [[Group Normalization]]?

Почему это может быть актуально для задачи детекции?
- (Использование GroupNorm в FCOS). 
- Детекция тренируется на маленьких батчах?
- [[FCOS]]

Использование [[Group Normalization]] в задачах детекции
- https://chatgpt.com/c/66df3841-8424-8000-9003-318b7caaf23d
- Object detection models often require large input resolutions, meaning they typically use smaller batch sizes to fit in memory.