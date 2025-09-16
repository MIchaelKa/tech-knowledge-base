
Group Relative Policy Optimization (GRPO)

[[Reinforcement Learning (RL)]]
[[RLHF]]

DeepSeekMath: Pushing the Limits of Mathematical Reasoning in Open Language Models
- https://arxiv.org/abs/2402.03300
- Introduction of GRPO?

Сегодня обсудим процедуру обучения DeepSeek-V3.
- https://t.me/gonzo_ML/3313
- Group Relative Policy Optimization (GRPO), вариант Proximal Policy Optimization (PPO),
- GRPO позволяет избавиться от отдельной value model, которая обычно такого же размера, что и policy model
- Вместо value function используется средний reward на множестве сэмплов, сгенерённых по одному и тому же входному запросу.
- Reward model при этом сохраняется
- KL лосс (который нужен, чтобы модель не уходила в сильно другой и нечитаемый текст) в такой схеме тоже упрощается, но делается не между reward и полиси, а напрямую между референс моделью и полиси. Advantage в GRPO по сути вычисляется как z-score.
	- упрощается по сравнению с чем? по сравнению с PPO?
	- But if used, KL is still policy vs reference, not reward vs policy.
	- There is no KL “between reward and policy” — that’s an imprecise way of describing the PPO setup.

Про магию Deepseek, RL и GRPO
- https://t.me/buckwheat_thoughts/104
- Вместо per-prompt оптимизации, в GRPO сначала семплится батч из промптов, потом для каждого ответа считается ревард, потом из каждого реварда вычитается среднее по всем ревардам в батче и нормируется на std, так получаем advantage. Дальше мы считаем частное между предсказаниями новой и старой моделей и вычитаем KLD, чтобы модель не сильно уходила от изначальных ответов.

KL лосс
- [[RLHF]]
- [[KL-Divergence]]

chatgpt
- https://chatgpt.com/c/68bff06d-5dd8-8333-9028-ac45a7119f0e


Questions

1
- Problem with PPO in RLHF for LLMs. High variance in rewards: prompts/responses can differ a lot
- Why we cannot just force the reward model to output reward from 0 to 1 for example? For example we could use sigmoid for that.

1.1
- reward model is trained on pairwise comparisons (“A is preferred over B”), not absolute ratings
- but the reward model outputs a rational score right? so the training was the regression problem right? how we get those regression values from pair-wise comparison?
- Instead of regression, we usually train it as a binary classification problem using a Bradley–Terry / logistic preference model
- This is like ranking loss (pairwise logistic loss).

1.2
- The raw outputs are unconstrained scalars. Absolute values don’t matter.
- Then how initially we use such a reward model with PPO? Did it work?

2
- Instead of advantage = reward – baseline, GRPO uses a group baseline
- Why we use the above formula in RLHF with PPO when we only have reward model which gives us the reward right away?
- This trick is called a control variate.
- value head trained alongside the policy
- GRPO removes the need for a separate value head by using a group baseline

3
- How KL loss is changed in GRPO related to old setup with PPO?
- Some implementations drop KL entirely

4.
- For a prompt, generate a _group of responses_ and use their relative ranking or average reward to compute advantage.
- For which of generated responses the loss is computed? How we get exact reward values for each of the responses?
- Loss can be computed for all the responses
- Final for each of the responses: advantage = reward – baseline

