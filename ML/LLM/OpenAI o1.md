
# Links

[[Reasoning]]

# External


OpenAI
- https://openai.com/index/learning-to-reason-with-llms/
- https://openai.com/index/introducing-openai-o1-preview/
- September 12, 2024

gonzo_ML
- https://t.me/gonzo_ML/3175
	- Test-time compute
	- Tailoring

buckwheat_thoughts
- https://t.me/buckwheat_thoughts/23
- я смотрю на это всё и понимаю, что это тупик и маркетинговый трюк

seeallochnaya
- о1: почему новая GPT от OpenAI — это не хайп, а переход к новой парадигме в ИИ
- https://habr.com/ru/companies/ods/articles/843250/
	- Strawberry
	- MATH Dataset
	- CoT
		- Проблема с тем как работают некоторые бенчмарки, где наоборот есть инструкция выдать ответ одним числом или буквой
		- После обнаружения этого эффекта разработчики нейросетей начали готовить данные в схожем формате и дообучать LLM на них — чтобы привить паттерн поведения
	- попросите модель перепроверить ей же сгенерированный ответ, выступить в роли критика.
	- Ниже я постараюсь описать **своё видение** того, что предложили OpenAI для решения вышеуказанной проблемы.
		- Так вот, исследователи заставили LLM... играть в игру.
		- RL
		- Если что — это и есть самый главный прорыв: обучение модели на своих же цепочках очень длинных рассуждений

seeallochnaya
- https://t.me/seeallochnaya/1775
- reasoning tokens
- CoT-SC

Request
- openai o1 how it works
- https://www.reddit.com/r/OpenAI/comments/1fjpk4l/how_openai_o1_works_in_a_simple_way_and_why_it/
	- you start multiple chains of thought at the same time

OpenAI o1 alternatives // reasoning (datasets) is all you need
- https://sbagency.medium.com/openai-o1-alternatives-reasoning-is-all-you-need-683677e2ecbe

Request
- o1 analogous technique from meta

TPO
- Meta
- Thought Preference Optimization
- New paper from Meta discloses TPO (Thought Preference Optimization) technique with impressive results
	- https://www.reddit.com/r/singularity/comments/1g51zqj/new_paper_from_meta_discloses_tpo_thought/


# Key words

Test-time compute
Strawberry
CoT

# Linked Papers

Measuring Mathematical Problem Solving With the MATH Dataset
- https://arxiv.org/abs/2103.03874
- AIME


AIME
- https://en.wikipedia.org/wiki/American_Invitational_Mathematics_Examination

# Overview

vs. ToT
vs. [[Ensembles]]