
Обучение с подкреплением
# External

Notion
- https://www.notion.so/Reinforcement-Learning-RL-86e8b0dae78041039e2e850a7200a2f0

Wiki
- https://en.wikipedia.org/wiki/Reinforcement_learning

gym
- https://github.com/openai/gym
- https://gym.openai.com/

Gymnasium
- https://github.com/Farama-Foundation/Gymnasium
- https://gymnasium.farama.org/
- import gymnasium as gym

Учебник по RL от Сергея Иванова - новая версия (исправленная), теперь на arxiv-е (на русском языке)
- https://t.me/smalldatascience/709
- https://arxiv.org/abs/2201.09746


https://karpathy.github.io/2016/05/31/rl/

библия Reinforcement Learning от Ричарда Саттона
- https://t.me/ai_newz/1666


Stable Baselines
- https://stable-baselines.readthedocs.io/en/master/index.html
- https://github.com/openai/baselines
- stable-baselines vs. spinningup
	- https://chatgpt.com/c/688c8b50-973c-8323-b462-4b91b8bae5ae

# Links

[[Training Neural Networks (TNN)]]

[[dlcourse.ai]]

[[Q-Learning]]

[[Spinning Up in Deep RL]]

[[LLM. RL]]
[[RLHF]]

# Overview

В контексте LLM почему люди говорят что только в 2025 RL наконец-то стал работать?
Почему только [[RLHF]] было не достаточно?

Policy Gradient Loss vs. [[Cross Entropy Loss (CEL)]]
- Policy Gradient Loss - получаем как градиент для ожидаемой награды за траекторию
- CEL - Получаем из принципа максимального правдоподобия [[MLE]]

Actor-Critic
- A2C
- MLP for baseline


Alternatives to Spinning up in Deep RL
- https://www.reddit.com/r/reinforcementlearning/comments/1drhci0/alternatives_to_spinning_up_in_deep_rl/
- rllib

# VPG

REINFORCE
- (Sutton & Barto)
- vanilla policy gradient
- Benchmarking Deep Reinforcement Learning for Continuous Control
	- https://arxiv.org/abs/1604.06778
- https://colab.research.google.com/drive/12SuRJvvey6PjR_Mw2TqPynNG-rLfESHM

baseline vs. advantage estimate

Discounted rewards
- Should the gamma depends on the episode length?

Cart pole
- reward для первых действий всегда значительно больше чем для последующих
	- действия которые мы производим в последствии менее важны?
	- это выполняется только для простых систем где reward за каждый шаг это 1 (cart pole)
- ожидаемый ревард сильно зависит от таймстемпа, сильный сигнал для обучения

Exploration vs. Exploitation
- update rule encourages it to exploit rewards that it has already found

# A2C

OpenAI Baselines: ACKTR & A2C
- https://openai.com/index/openai-baselines-acktr-a2c/
- https://stable-baselines.readthedocs.io/en/master/modules/a2c.html
- A2C is a synchronous, deterministic variant of Asynchronous Advantage Actor Critic (A3C)
- ACKTR
- we have not seen any evidence that the noise introduced by asynchrony provides any performance benefit.

Asynchronous Methods for Deep Reinforcement Learning
- https://arxiv.org/abs/1602.01783
- A3C


ChatGPT
- https://chatgpt.com/c/688c8d87-ef98-832f-9620-c5e901cb5a78
- Asynchronous Updates
- Encourages exploration by adding an entropy term to the loss
- Experience replay
	- DQN
	- random sampling of mini-batches
- Exploration
- Noise introduced by asynchrony
	- Stale parameters 
- When A3C was introduced in 2016, GPUs weren't as widely used for RL training. Asynchrony made it easy to scale on **CPU cores**, and helped decorrelate experiences.


# DQN

[[Q-Learning]]

Playing Atari with Deep Reinforcement Learning
- https://arxiv.org/abs/1312.5602


# Model

ReLu vs. Tanh