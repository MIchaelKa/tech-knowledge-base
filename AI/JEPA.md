

JEPA
Joint Embedding Predictive Architectures


A Path Towards Autonomous Machine Intelligence
- Paper
- openreview.net/pdf?id=BZ5a1r-kVsf
- 2022

# Links

[[LLM]]
- Timeline

# Overview


YK
- https://www.youtube.com/watch?v=jSdHmImyUjk
- non-generative architecture
- non-contrastive self-supervised learning paradigm
- H-Jepa
- World Model
- Mode-1 perception-action episode
	- Kahneman
	- This reactive process does not make use of the world model not the cost
- Cost
	- External reward
	- Intrinsic motivation
- Model-free RL
	- Train the actor using the reward
	- At inference time actor is simply act
	- TODO
- Mode-2 perception-action episode
	- roll out the world model
	- using gradient decent at inference time
	- similar to construction of adversarial examples
- Training reactive policy from the result of Mode-2 reasoning
- [[Self-Supervised Learning (SSL)]] and [[Energy-Based Models (EBMs)]]
	- Energy function and training loss are the same things - YK
	- Energy function - minimize at inference time
	- Training loss - minimize at training time
- Latent-Variable EBM
	- minimize energy with respect to latent variable z to find z that makes x and y most compatible
- Collapse problem
	- How we can set z to y?
	- https://chatgpt.com/c/6907c780-09e0-832e-9f16-0814f8dc9620
- Overview
	- SSL
	- Energy Function
		- vs. CLIP
		- VQ-GAN - minimizing the energy at inference time
- How to deal with Collapse problem
	- Contrastive learning and [[Curse of Dimensionality]]
	- Regularized methods
	- Minimize/Maximize Information Content

# Comments

Можно узнать твое мнение по Jepa architecture и energy-based world models в целом? Ян Лекун видит его как более реалистичное для AGI 

# Versions

Развитие темы про JEPA, world models и выучивание интуитивной физики из видео.
- https://t.me/gonzo_ML/3501
- V-JEPA ?

V-JEPA 2
LLM-JEPA
