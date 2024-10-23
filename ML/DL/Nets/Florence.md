
# External

Paper
- Florence: A New Foundation Model for Computer Vision
- https://arxiv.org/abs/2111.11432
- Microsoft

gonzo_ML
- https://t.me/gonzo_ML/734
- 01.12.2021
	- времена после Yandex Cup 21
	- https://www.notion.so/Yandex-Cup-21-41c804c8e40645f5921d6b7d676cde4c
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
- Адаптеры
	- [[Dynamic Head (DyHead)]]
	- METER
- Только для того чтобы получить более универсальные веса?
- Когда производят бенчмарки для конкретных задач, сразу после конкретного дообучения или после всех дообучений?


Tasks
- classification
	- zero-shot
	- linear probe
		- ?
- image-text retrieval
- object detection
- VQA