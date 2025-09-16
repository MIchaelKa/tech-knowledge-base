
# External

AndrejKarpathy
- Deep Dive into LLMs like ChatGPT

GH
- https://github.com/deepseek-ai/DeepSeek-R1

DeepSeek moment
- https://t.me/gonzo_ML/3239
- DeepSeek-R1-Zero
	- обучена чистым RL (Group Relative Policy Optimization, GRPO — вариант PPO из другой их статьи, https://arxiv.org/abs/2402.03300), без SFT

Open R1
- https://github.com/huggingface/open-r1


R1-Lite
- https://t.me/ai_newz/3445
- 20.11.2024
- бесплатный конкурент o1, который скоро релизнут в опенсорс
- inference time scaling заставили работать за пределами OpenAI

# Links

[[LLM]]
[[Reinforcement Learning (RL)]]
[[Reasoning]]
[[DeepSeek]]

# Papers

DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning
- https://arxiv.org/abs/2501.12948

# News

A shocking Chinese AI advancement called DeepSeek is sending US stocks plunging
- https://edition.cnn.com/2025/01/27/tech/deepseek-stocks-ai-china/index.html
- R1

# External

DeepSeek-R1
- https://t.me/gonzo_ML/3319
- Также можно сказать, что в NLP снова начинает работать RL.
- В качестве базовой модели взята DeepSeek-V3-Base, модель после Pre-training, но до Post-training, то есть без SFT и RL.
- SFT vs. RL for Reasoning
	- авторы показали, что для обучения ризонингу не обязательно иметь 100500 примеров для SFT, эти способности неплохо выучиваются с помощью large-scale RL, и можно вообще обойтись без “человеческих демонстраций” в виде SFT.
	- Но если помочь cold start’у небольшим количеством SFT с хорошими примерами, то всё ещё лучше.
- Rule-based RM
	- Accuracy rewards
		- легко получить для математики и программирования
	- Format rewards
		- следит за соответствием формата “мыслительного процесса”, он должен быть внутри тегов `<think>` и `</think>`
- DeepSeek-R1-Zero
	- Для обучению ризонингу применяется GRPO, который использовался еще в DeepSeek-V3
	- Reward моделируется через систему на правилах, аналогично Rule-based RM из пост-обучения DeepSeek-V3
	- Используют довольно прямолинейный промпт с CoT, который требует от модели сначала подумать, а потом выдать ответ.
	- Подход Zero с чистым RL без SFT позволяет пронаблюдать, как модель эволюционирует по ходу обучения
		- модель сама выучивает, что думать дольше полезно
- DeepSeek-R1
	- constitutional AI
- дистилляция
	- [[Knowledge Distillation]]
	- дистилляты обучаются без RL на чистом SFT
	- если хочется обучить хорошую маленькую модель, то лучше это делать через дистилляцию хорошей большой, чем убиваться, обучая её через RL.


Про магию DeepSeek, RL и GRPO
- https://t.me/gonzo_ML/3289
- https://t.me/buckwheat_thoughts/104
- RLHF в виде PPO
	- при наличии ревард-модели (классификатора), обучать модель генерациям можно на неразмеченных данных.
	- PPO — это штука сложная, нестабильная и требовательная к качеству ревард модели
	- reward hacking
	- skill issue
		- ?
- DPO
	- [[DPO]]
	- Следующий шаг после PPO
	- полностью избавились от отдельной ревард модели, используя саму обучаемую модель для оценки генераций
	- Это, по сути, стало стандартом для преференс-тюнинга моделей.
- GRPO
	- DeepSeekMath
- сфт колдстарт == SFT pre-train
- Это что, получается, рл, наконец-то заработал?


The Illustrated DeepSeek-R1
- https://t.me/gonzo_ML/3266
- https://newsletter.languagemodels.co/p/the-illustrated-deepseek-r1
- thinking tokens
- CoT
- reasoning tasks
	- reasoning-related benchmarks
	- what the example of the task what do not required reasoning?
- R1-Zero
	- Large-Scale Reasoning-Oriented RL
	- No labeled SFT training set
	- Automatic Verification of a Reasoning Problem
		- Code problems
		- Other examples?
- General RL
	- it extends to non-reasoning applications
		- How?
		- General RL with reward models(Safety, Helpfulness) based on DeepSeek-V3
		- How to get those reward models?
- Arch
	- [[Mixture of Experts (MoE)]]


Толока
- R1 is not on par with o1, and the difference is qualitative, not quantitative
	- https://toloka.ai/blog/r1-is-not-on-par-with-o1-and-the-difference-is-qualitative-not-quantitative/
- External
	- https://t.me/boris_again/3084
		- [[Confidence Interval]]
	- https://t.me/seeallochnaya/2405
- Тесты на задачах из длинного хвоста

# Overview

Мы можем автоматически создавать примеры для Reasoning используя автоматически проверяемые задачи такие как математика и программирование. 
Как получить такие примеры для других областей? 
Нужен ли Reasoning вообще в тех областях где это невозможно сделать?
Если оставить примеры с Reasoning только для математики и программирования научиться ли модель включать Reasoning только для этих задач?

reasoning and non-reasoning problems/tasks

reasoning
- math
- programming

non-reasoning
- summary
- translation
- creative writing