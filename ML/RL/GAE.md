
Generalized Advantage Estimation (GAE)

# Links

[[Spinning Up in Deep RL]]

# External

Spinning Up’s implementations of VPG, TRPO, and PPO make use of it.
https://spinningup.openai.com/en/latest/spinningup/rl_intro3.html

High-Dimensional Continuous Control Using Generalized Advantage Estimation
- https://arxiv.org/abs/1506.02438
- John Schulman, Philipp Moritz, Sergey Levine, Michael Jordan, Pieter Abbeel

chatgpt
- https://chatgpt.com/c/68bf3620-2fd8-832f-9e0f-b170160e88d2


TD (Temporal Difference)

Monte Carlo returns
1-step TD error (a.k.a. TD residual)
Multi-step Advantage Estimators
GAE combines all k-step estimators using an exponential weighting with parameter λ

λ parameter controls bias–variance trade-off

