
# External


Playing Atari with Deep Reinforcement Learning
https://arxiv.org/abs/1312.5602


# Links

Q-star OpenAI

Markov Process
Markov Decision Process

State Machine


# Questions

RL and LLM Agents
How to apply to LLM?
[[RLHF]]

# YK

https://www.youtube.com/watch?v=nOBm4aYEYR4

Observation = State

Проблема с базовым сетапом в RL, получаем Reward только в конце.
Похожая проблема с Seq2Seq моделями.
Пример с шахматами, мы можем сказать что получили ревард только в самом конце, когда поставили мат. Но разве мы не можем оценивать промежуточные положения?

Q-Learning
$R = Q(s,a)$
proposed action - if I did action a, what would my total reward be?

Policy
$a = \pi(s)$ 

Q-Func + Policy
$R = Q_\pi(s,a)$
Policy говорит нам об еще одном действии которое мы сделаем после действия $a$

Is Q-Function the same thing that on-policy action value function?

Пример с шахматами и Магнусом Карлсеном в качестве Policy

The Bellman Equation

Q-Learning can be done in many different ways. What the ways?

How can we learn this Q-function?

Self-regression
Table for learning. Q,S,R.
Initialize with random values?
We you use our own estimates as a target, plus combine them with the actual reward from the world.
How to get such a table for continuous spaces?
Reducing the whole problem to just estimating of a single step

Language Modeling
Connection with autoregressive language modeling.
Proximal Policy Optimization vs. Q-Learning for [[RLHF]]
Action space is token vocabulary

Experience Replay
