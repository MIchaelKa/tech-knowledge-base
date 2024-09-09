
Group Norm

# Paper

Group Normalization
[https://arxiv.org/abs/1803.08494](https://arxiv.org/abs/1803.08494)
Yuxin Wu, Kaiming He

# Parent

[[Normalization]]


# Links

Та самая картинка
[https://arxiv.org/pdf/1803.08494.pdf](https://arxiv.org/pdf/1803.08494.pdf)

Yannic Kilcher
[https://www.youtube.com/watch?v=l_3zj6HeWUE](https://www.youtube.com/watch?v=l_3zj6HeWUE)


# Overview

Multivariate normal distribution
Чем ближе наши данные к этому распределению тем лучше работает МЛ.

Distributed machine learning
- Smaller batches on each machine
- [[Distributed Training]]

Почему это может быть актуально для задачи детекции?
- (Использование GropNorm в FCOS). 
- Детекция тренируется на мальньких батчах?
- [[FCOS]]

vs. батчнорм
- И все-таки как нормализуем батчнорм? 
- Яник говорит что статистика для каждого пикселя?
	- NO

Group Norm - mix between layer norm and instance norm.
Normalize across the single datapoint.

Статистика
- Don’t need running mean statistic at test time!
- Почему это нужно было в батчнорме?
	- Потому что на инференcе размер батча может быть равен 1.