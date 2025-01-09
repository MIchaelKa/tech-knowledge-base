
Parameter Efficient Finetuning (PEFT)

Low-Rank Adaptation of Large Language Models
# External

[LLM] Finetuning
https://www.notion.so/LLM-Finetuning-b1cdf8de096d4346ab31d3e99a2046f5

GH
https://github.com/microsoft/LoRA

MoRA
https://www.linkedin.com/posts/sebastianraschka_its-always-exciting-when-a-new-paper-with-activity-7200121844291559424-1CMu?utm_source=share&utm_medium=member_desktop

instruction finetuning and continued pretraining

# Overview

What is Low-Rank Adaptation (LoRA) | explained by the inventor
- Links
	- https://www.youtube.com/watch?v=DhRoTONcyZE
- Full finetuning is prohibitively expensive
- Checkpoint for 175B parameters in 1TB large
- Generalization of finetuning
	- Update all parameters
	- Full rank updates
- Matrix
	- d x d - full
	- 2 x d x r - lora
- LoRA result
	- point near origin perform just as well as in top-right corner
- How to choose the rank R?
	- Test and move from top-right to bottom-left
- Efficient task-switching during deployment
- No cost during inference
- RAM
	- cache LoRA in RAM
	- RAM much larger than VRAM
- Modularity
	- LoRA modules are additive
	- Adapted model forms a tree.


**Кто же такая это ваша LoRA**
- https://habr.com/ru/articles/747534/
- Это отдаленно напоминает градиентный бустинг, где мы учим каждое следующее решающее дерево исправлять ошибки прошлого.
- утверждают что "внутренняя размерность" (intrinsic rank) больших текстовых моделей очень низкая, и большинство параметров, проще говоря, "не работают".
	- ак это соотносится с тем постулатом что больше параметров - выше точность. Зачем сети больше парметров если она потом их не использует?
- Дообучать на новой информации или подать ее в промт?