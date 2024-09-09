

https://www.notion.so/Normalization-b57f0cbcba854c04a4e205682a5cb4a6


[[Batch Normalization]]
[[Group Normalization]]
Instance Normalization
Layer Normalization


# External Links

PyTorch
https://pytorch.org/docs/stable/nn.html#normalization-layers

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
- https://arxiv.org/abs/1607.06450
- Нормализуется каждый пример вдоль всех фичей
	- mean.shape = (N,)
- Используется в NLP задачах, в трансформере.
- Вводим layer normalization потому что не достаточно примеров чтобы точно подсчитать статистику вдоль батча?