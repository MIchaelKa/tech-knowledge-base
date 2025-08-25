
2018

# External

https://t.me/smalldatascience/827

https://spinningup.openai.com/en/latest/

https://github.com/openai/spinningup/tree/master

# Links

[[Reinforcement Learning (RL)]]

# Intro

Intro
- RL and AI safety
- package
- Still has Gym dependency?

Algorithms
- On-Policy Algorithms
	- Example: VPG
	- they don’t use old data, which makes them weaker on sample efficiency
	- trades off sample efficiency in favor of stability
- Off-Policy Algorithms
	- Example: DDPG
	- Deterministic PG
	- DDPG is closely connected to  [[Q-Learning]] algorithms
	- able to reuse old data very efficiently
	- Bellman’s equations
- On-Policy vs. Off-Policy 
	- https://chatgpt.com/c/6863cc0e-c75c-8000-8809-e358989ae8aa


Code format
- experience buffer object


The `seed` flag sets the seed for the random number generator. RL algorithms have high variance, so try multiple seeds to get a feel for how performance varies.

openai spinning up and gymnasium

OpenMPI


# Part 1: Key Concepts in RL


RL is the study of agents and how they learn by trial and error.

The environment changes when the agent acts on it, but may also change on its own.
The goal of the agent is to maximize its cumulative reward, called **return**.

Policies
- policy == agent
- policy is essentially the agent’s brain

Stochastic Policies
- Categorical Policies
	- discrete action spaces
- Diagonal Gaussian Policies
	- continuous action spaces
- Two key computations
	- sampling
	-  log likelihoods of particular actions

Diagonal Gaussian Policies
- neural network that maps from observations to mean actions
- single vector of log standard deviations
	- [[Variational Autoencoder (VAE)]]
	- two ways: function of the state or not
	- [[Normal Distribution]]
- The log-likelihood of a k-dimensional action a, for a diagonal Gaussian
	- Can you derive this formula?

Likelihood vs. Probability
- [[MLE]]

Trajectories
- episodes or rollouts

Rewards
- The goal of the agent is to maximize some notion of cumulative reward over a trajectory
- discount factor is both intuitively appealing and mathematically convenient

Return
- cumulative reward

The RL Problem
- expected return
	- the goal in RL is to select a policy which maximizes expected return
	- probability distributions over trajectories

Goal
- cumulative reward over a trajectory
- expected return
- vs. ?

Value
- expected return if you start in that state or state-action pair, and then act according to a particular policy forever after
- state or state-action pair

On-Policy Action-Value Function
- What point in taking an arbitrary action a? 
	- state-action pair

Advantage Functions


# Part 2: Kinds of RL Algorithms

Model-Free vs Model-Based RL
- By a model of the environment, we mean a function which predicts state transitions and rewards.


# Part 3: Intro to Policy Optimization


PyTorch distributions are really useful for RL

policy gradient vs. loss function

Loss Function
- make loss function whose gradient, for the right data, is policy gradient

The loss function means nothing.
- todo

Expected Grad-Log-Prob (EGLP) lemma
- Imagine this: if you sampled actions from your policy but ignored rewards, you’d get zero gradients (EGLP). That makes sense — there's nothing to learn.
- https://chatgpt.com/c/687bb0a9-1a08-8000-8658-7d0d5d0d1bbd

Reward-to-go policy gradient
- reinforcing actions proportional to past rewards, all of which had zero mean
	- why zero mean?
	- those past rewards are independent of the current action
	- https://chatgpt.com/c/687bae4d-ea6c-8000-a5af-4feb3d690768

Baseline
- Use EGPL
	- If b depends on the action, then you can’t pull it out of the expectation (over actions)
	- https://chatgpt.com/c/687bb0a9-1a08-8000-8658-7d0d5d0d1bbd
- On-policy value function as a baseline 


Forms of the Policy Gradient

# Resources

Spinning Up as a Deep RL Researcher
- parallelized versions of these algorithms
- more than one environment
	- sometimes things will work in one environment even when you have a breaking bug, so make sure to test in more than one environment once your results look promising
- run everything for many random seeds
- tips on how to do a research

