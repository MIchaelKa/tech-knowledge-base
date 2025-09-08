
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

Andrej Karpathy
- https://karpathy.github.io/2016/05/31/rl/

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

[[Spinning Up in Deep RL]]

[[RLHF]]
[[Reasoning]]

# Overview

В контексте LLM почему люди говорят что только в 2025 RL наконец-то стал работать?
Почему только [[RLHF]] было не достаточно?
Потому что RLHF вытеснил [[DPO]], который убрал RL из обучения.
RL снова заработал только когда появились "думающие" модели

Policy Gradient Loss vs. [[Cross Entropy Loss (CEL)]]
- Policy Gradient Loss - получаем как градиент для ожидаемой награды за траекторию
- CEL - Получаем из принципа максимального правдоподобия [[MLE]]

Actor-Critic
- A2C
- MLP for baseline

Alternatives to Spinning up in Deep RL
- https://www.reddit.com/r/reinforcementlearning/comments/1drhci0/alternatives_to_spinning_up_in_deep_rl/
- rllib

Exploration vs. Exploitation

OpenMPI
- parallelization

 Generalized Advantage Estimation (GAE)
 - https://arxiv.org/abs/1506.02438


Model
- ReLu vs. Tanh


# Rewards

Discounted rewards
- Should the gamma depends on the episode length?

Does it make sense to use discounted(cumulative) rewards for any environments?
- https://chatgpt.com/c/68ab5b00-5880-832e-811e-0eacf6049f87
- Pendulum-v1, what if we just use the immediate reward?

# VPG

vanilla policy gradient

Classic
- [Policy Gradient Methods for Reinforcement Learning with Function Approximation](https://papers.nips.cc/paper/1713-policy-gradient-methods-for-reinforcement-learning-with-function-approximation.pdf)
- Sutton et al. 2000
- (Sutton & Barto)

REINFORCE
- Benchmarking Deep Reinforcement Learning for Continuous Control
	- https://arxiv.org/abs/1604.06778
- https://colab.research.google.com/drive/12SuRJvvey6PjR_Mw2TqPynNG-rLfESHM

baseline vs. advantage estimate

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
- A2C is a synchronous, deterministic variant of Asynchronous Advantage Actor Critic (A3C)
- ACKTR
- we have not seen any evidence that the noise introduced by asynchrony provides any performance benefit.

Stable baselines
- https://stable-baselines.readthedocs.io/en/master/modules/a2c.html

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
- Noise introduced by asynchrony
	- Stale parameters 
- When A3C was introduced in 2016, GPUs weren't as widely used for RL training. Asynchrony made it easy to scale on CPU cores, and helped decorrelate experiences.
- A2C = VPG + baseline + parallel rollout + entropy + minibatching

Implementation
- Train single network for actor and critic

# DQN

[[Q-Learning]]

Playing Atari with Deep Reinforcement Learning
- https://arxiv.org/abs/1312.5602

Experience Replay
Target Network

Properties
- Off-policy
- Past experiences are reused many times.

ChatGPT
- https://chatgpt.com/c/68931abf-4ef4-8333-9647-1eea52bf36be
- Implementation
- exploration strategy (e.g., ε-greedy)
	- You typically use ε-decay to reduce exploration over time
- Online Q-learning with the MLP (no table)
- DQN-style training with replay buffer
	- Neural nets generalize over continuous state space (your table won't)
- Table-based Q-learning approach
	- You must apply quantization (discretization) to your states
	- We do not use target network here

DQN-style training with replay buffer
- Collect rollouts, store [state, action, reward, next_state, done]
- Train every 10 rollouts
- Do several epochs with current collected data
- Update target network
- Clear the buffer - NO
- Repeat

Implementation
- See exported chat
- Large, infrequent update that causes big policy jumps.
- Time-limit bootstrapping
	- terminal vs. truncated
	- Bootstrap on truncations
- Soft target update


 Bellman equation
- https://spinningup.openai.com/en/latest/spinningup/rl_intro.html#bellman-equations
- https://chatgpt.com/c/68a1c289-7264-8329-a5af-602f4e71997b
- Is Bellman equation holds only for optimal value function or for any value function?
- All four of the value functions obey special self-consistency equations called Bellman equations.
- The crucial difference between the Bellman equations for the on-policy value functions and the optimal value functions, is the absence or presence of the max over actions.


# TRPO

Trust Region Policy Optimization

[[KL-Divergence]]
[[Variational Autoencoder (VAE)]]
[[Convex Optimization]]

TODO
- [ ] Quadratic approximation
- [ ] Natural gradient
- [x] Importance sampling

Properties
- On-policy
- Solving a constrained optimization problem
- Inspired PPO

Spinning Up
- https://spinningup.openai.com/en/latest/algorithms/trpo.html
- Convex Optimization by Boyd and Vandenberghe
- [[Convex Optimization]]

Trust Region Policy Optimization
- https://arxiv.org/abs/1502.05477
- Schulman

ChatGPT
- https://chatgpt.com/c/689b99f0-1aec-8329-8f92-bd4643d181d6

The fraction
The fraction is the likelihood ratio: how much more/less likely the new policy is to take the same action.
surrogate advantage vs. surrogate objective
likelihood ratio

Trust Region
The circle is defined not by Euclidean distance in parameter space, but by KL divergence between old and new policy distributions.

VPG vs. TRPO
Мы заменили логарифм вероятности на отношение двух вероятностей
log-probability vs. likelihood ratio

Why we need to replace the log-probability form with a likelihood ratio, why just introducing the KL constraint is not enough?
Constrained optimization. No regular gradient ascent anymore. Evaluate candidate policies.
Does it mean we need to treat formulas differently?

Importance sampling
- https://en.wikipedia.org/wiki/Importance_sampling
- Monte Carlo method for evaluating properties of a particular distribution, while only having samples generated from a different distribution
- Target distribution in our case is the new policy and we only have samples drawn from the old policy.

As I know TRPO is on-policy algorithm, in which moment we will get new policy out of old policy?
We compute the ratio for many candidate policies.

Optimization
- Constrained optimization problem
- Quadratic approximation
- Constrained quadratic approximation
- Constrained quadratic approximation with closed form solution

Quadratic approximation
Instead of solving the above exactly (which is hard), TRPO approximates
Fisher Information Matrix (from the KL expansion)
Constrained quadratic optimization with a known closed-form solution
The optimal direction is the natural gradient

Natural gradient step
Instead of regular gradient ascent, TRPO uses a natural gradient step that accounts for the curvature of the policy space via the Fisher Information Matrix.

Разложение в ряд Тейлора
- [[Taylor Series]]
- определение advantage гарантирует, что его математическое ожидание по текущей политике равно нулю

Градиент surrogate objective в точке $\Theta_k$ равняется VPG для старой полиси.
- Почему тогда это называется surrogate objective?
- Если градиент этой функции равен Policy Gradient для старой политики, получается мы получили формулу лосса для VPG?
	- Не совсем, формула для TRPO сложнее, они совпадают только локально в точке $\Theta = \Theta_k$. Как раз в этой точке мы и раскладываем в ряд тейлора.
- ~~В VPG мы оптимизируем градиент? Если это формула уже является градиентом полиси, почему нам нужен ac_loss.backward() ?~~


# PPO

Proximal Policy Optimization

HF
- https://huggingface.co/blog/deep-rl-ppo

There are two primary variants of PPO:
PPO-Penalty
PPO-Clip

proximal - ближайший

Properties
- On-policy
- Relies on specialized clipping in the objective function

TRPO vs. PPO
- PPO methods are significantly simpler to implement, and empirically seem to perform at least as well as TRPO.
- 2nd order method vs. 1st order method + some tricks

ChatGPT
- https://chatgpt.com/c/68a1a6ff-d698-8329-8f25-c9336486b097

PPO vs. [[Gradient Clipping]]
- [[Gradient Clipping]] prevents exploding gradients but doesn’t prevent the update from pushing the policy too far in parameter space.
- PPO clipping: Instead of clipping gradients, it clips the probability ratio between new and old policies

Surrogate objective formula from TRPO?
- Why we use the surrogate objective formula from TRPO? If we do not solve Constrained optimization problem anymore and do usual gradient ascent, why we cannot just write usual VPG loss?

Implementation
- Should we fix trained neural net to calculate ratio in the loss formula?
- What if we do only one update, how to tell PyTorch what this neural net is the constant?
- When we do first update, is the ratio equal to 1?
- We can already have the action probability form the old policy in the buffer?

No log in the loss function?
- Совпадает с VPG в точке $\theta_k$
- Или совпадает только градиент?

Cursor
- Note: PPO is on-policy; data from random actions is off-policy.

# DDPG

Deep Deterministic Policy Gradient

Continuous control with deep reinforcement learning
- https://arxiv.org/abs/1509.02971

Properties
- off-policy algorithm
- concurrently learns a Q-function and a policy
- adapted specifically for environments with continuous action spaces

Max over actions for continuous action spaces
- normal optimization algorithm

MSBE
- mean-squared Bellman error (MSBE) function
- is it exactly what we learn in usual DQN algorithm?

Tricks
- Replay Buffers
- Target Networks
	- Problematically, the target depends on the same parameters we are trying to train
	- polyak averaging for target network
- DDPG Detail: Calculating the Max Over Actions in the Target
	- target policy network

Policy learning in DDPG
- Q-function is differentiable
	- is it only holds when action space is continuous?
- gradient ascent (with respect to policy parameters only)
- Q-function parameters are treated as constants
