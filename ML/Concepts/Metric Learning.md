
Moved
https://www.notion.so/Metric-learning-11678a6f342d483e96566ca9e9926028


# External Links

dlcourse
[https://www.youtube.com/watch?v=ajEQ10s8XRg](https://www.youtube.com/watch?v=ajEQ10s8XRg)

pytorch metric learning
[https://github.com/KevinMusgrave/pytorch-metric-learning](https://github.com/KevinMusgrave/pytorch-metric-learning)

Open Set Learning
Open set problem

# Links

[[dlcourse.ai]]

[[Few-Shot Learning (FSL)]]

# Discussion

Когда нам нужен metric learning вместо обычного классификатора?
- Когда нужно сделать few-shot.

# Overview

Тренируем сеть таким образом чтобы расстояния между ембедингами удовлетворяли нашей задаче (метрике)
Например: лица могут быть разные но один и то же ракурс. Нужно чтобы ембединг был чувствителен именно к лицам.
Для такой тренировки используется Triplet Loss

Triplet Loss
- TODO