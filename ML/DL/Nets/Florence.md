
# External

Paper
- Florence: A New Foundation Model for Computer Vision
- https://arxiv.org/abs/2111.11432
- Microsoft

gonzo_ML
- https://t.me/gonzo_ML/734
- 01.12.2021
	- времена после Yandex Cup
- про foundation models
	- [[Foundation Model]]
- И в очередной раз ощущение, что решили дорогую комбинаторную задачу по сбору правильного набора компонент. Кажется, именно в этом инженерная и научная ценность работы.

# Links

[[CLIP]]

ALIGN

# Overview

Dataset
- FLD-900M (FLorence Dataset)
- ALIGN

Сложности с описанием картинок
- Для одного и того же описания могут встречаться разные картинки
- Тренировка [[Contrastive Learning (CL)]] неявно подразумевает что такие пары уникальные, так как все остальные будут рассматриваться как негативные примеры
- Отрицательно сработает только если одинаковые описания попадут в один батч при тренировке
- Решение - UniCL

UniCL
- Unified contrastive learning in image-text-label space

Двунаправленная лосс функция
- t2i
- i2t

Models
- Text
	- 256М
- Vision
	- CoSwin-H Transformer
	- 637М
- Total
	- 893М

Training
- 10 дней на 512 A100-40Gb
- Большой батч 
	- для CL всегда нужны большие батчи

Дообучение
- [[Dynamic Head (DyHead)]]
- METER
- Решение большой комбинаторной задачи

# Discussion
