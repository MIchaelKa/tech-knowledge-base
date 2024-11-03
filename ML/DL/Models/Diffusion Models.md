
# External

Notion
- https://www.notion.so/Diffusion-Models-fac71777ec1548ae9fcd343bd2d196e6

DALL-E
- https://www.notion.so/DALL-E-3b0bd44a8e73428aa1551821bc573cb2
- [[DALL-E]]


# Links

[[Markov Chain]]

# Papers


Denoising Diffusion Probabilistic Models
- https://arxiv.org/abs/2006.11239
- Jonathan Ho, Ajay Jain, Pieter Abbeel
- Berkeley
- DDPM

Improved Denoising Diffusion Probabilistic Models
- https://arxiv.org/abs/2102.09672
- Alex Nichol, Prafulla Dhariwal
- OpenAI

Diffusion Models Beat GANs on Image Synthesis
- https://arxiv.org/abs/2105.05233
- Prafulla Dhariwal, Alex Nichol
- OpenAI
- https://t.me/ai_newz/439

Latent Diffusion
- High-Resolution Image Synthesis with Latent Diffusion Models
- https://arxiv.org/abs/2112.10752
- https://t.me/ai_newz/1056
- https://t.me/ai_newz/1057

Stable Diffusion
- https://t.me/ai_newz/1368

# Videos

Diffusion models from scratch in PyTorch
- Info
	- 07.2022
- External
	- https://www.youtube.com/watch?v=a4Yfz2FxXiY
	- https://colab.research.google.com/drive/1sjy9odlSSy0RBVgMTgP7s99NXsqglsUL
	- http://localhost:8888/lab/tree/ml_sandbox/dl/diffusion_model_tutorial.ipynb
- Links
	- Diffusion-GAN
- My questions
	- https://chatgpt.com/c/6724ed66-8430-8000-a776-20a41839ead3
	- https://chatgpt.com/c/672510ca-8e68-8000-8a15-2522093e5f32
- Text guided image generation
- Slow generation process
	- Sequential generation process
	- As these models are still in their infancy there might be lots of improvements in the future
- Main components
	- Noise scheduler
	- Model that predicts the noise in the image
		- Neural Network
		- UNet
	- Timestep encoding
		- Positional embeddings from transfromer
- Dataset
	- StanfordCars
	- Data range (-1, 1)
- Forward process
	- Markov process
	- Each step depends on previous
	- N
		- Mean - previous image
		- Variance - Fixed
	- Variance schedule
		- $\beta_t$
		- how much noise we want to add
	- Noise scheduler
		- Different strategies
		- Simple strategy: adding noise linearly
		- Мы можем сразу, напрямую (не последовательно) посчитать шум для таймстемпа $t$
		- Closed form sampling
- Backward process
	- Parameterized backward process
- Training
	- Batch-training
	- Sample timestamp t
- Loss
	- ELBO
		- Variational lower bound
		- Similar to [[Variational Autoencoder (VAE)]]
	- Alternatives
		- Denoising score matching
	- Just use L1 or L2 in this tutorial
- Sampling
	- Adding noise during sampling
	- See questions
	- Why Add Noise During Generation?
		- It is the same as sample from above Gaussian distribution

# Terms

VQ
Vector quantize


# Overview

Pros
- High quality samples
- Diversity

Cons
- Slow generation process
	- Slow sampling
	- Sequential generation process