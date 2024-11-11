
# External

Notion
- https://www.notion.so/Diffusion-Models-fac71777ec1548ae9fcd343bd2d196e6

Awesome-Diffusion-Models
- https://github.com/diff-usion/Awesome-Diffusion-Models

wiki
- https://en.wikipedia.org/wiki/Diffusion_model

# Links

[[Image Generation]]

[[Generative Models]]

[[Markov Chain]]

[[Variational Autoencoder (VAE)]]

# Papers


Deep unsupervised learning using nonequilibrium thermodynamics
- https://arxiv.org/abs/1503.03585

Generative Modeling by Estimating Gradients of the Data Distribution
- https://arxiv.org/abs/1907.05600
- score-based generative modeling method

Denoising Diffusion Probabilistic Models
- https://arxiv.org/abs/2006.11239
- Jonathan Ho, Ajay Jain, Pieter Abbeel
- Berkeley
- DDPM
- Ignoring weighting term

Improved Denoising Diffusion Probabilistic Models
- https://arxiv.org/abs/2102.09672
- Alex Nichol, Prafulla Dhariwal
- OpenAI

Diffusion Models Beat GANs on Image Synthesis
- https://arxiv.org/abs/2105.05233
- Prafulla Dhariwal, Alex Nichol
- OpenAI
- https://t.me/ai_newz/439

Classifier-Free Diffusion Guidance
- https://arxiv.org/abs/2207.12598
- Jonathan Ho, Tim Salimans

Elucidating the Design Space of Diffusion-Based Generative Models
- NeurIPS 2022
- https://arxiv.org/abs/2206.00364
- https://t.me/ai_newz/1911

# DE

[[Differential Equations]]

Score-Based Generative Modeling through Stochastic Differential Equations
- https://arxiv.org/abs/2011.13456
- Yang Song, Jascha Sohl-Dickstein, Diederik P. Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole

Denoising Diffusion Implicit Models
- https://arxiv.org/abs/2010.02502
- Jiaming Song, Chenlin Meng, Stefano Ermon
- DDIM

# Models

DDPM
DDIM

[[DALL-E]]
[[GLIDE]]
[[DALL-E-2]]

[[Latent Diffusion]]

[[Imagen]]

Stable Diffusion
- https://t.me/ai_newz/1368
- https://github.com/CompVis/stable-diffusion
- CompVis
- LAION-2B
- Imagen
- Grounding DINO
	- https://t.me/ai_newz/1852

Neural Network Parameter Diffusion
- https://arxiv.org/abs/2402.13144
- https://t.me/gonzo_ML/2394
- hypernetwork
- Model soups: averaging weights of multiple fine-tuned models improves accuracy without increasing inference time
- LD

ControlNet
- https://github.com/lllyasviel/ControlNet


# Tutorial

Denoising Diffusion Models: A Generative Learning Big Bang - Туториал
- https://cvpr2023-tutorial-diffusion-models.github.io/
- https://www.youtube.com/watch?v=1d4r19GEVos
- https://t.me/ai_newz/2273
- differential equation solvers
	- advances on accelerating sampling from diffusion models
	- DPM-Solver (NeurIPS 2022 Oral)
	- DEIS
- Unlike the previous tutorial, we will streamline the discussion on fundamentals
- Fundamentals
	- Part 1. DDPM
		- Diffusion kernel
			- Closed form sampling
			- Diffusion kernel is Gaussian convolution
		- Distributions
			- We don't have access to PDF of data distribution on all steps, excluding the last
			- Ancestral sampling
	- Part 2. Score-based generative modeling with Differential Equations
		- [[Differential Equations]]
		- ODE
			- Neural ODE
			- 
		- Stochastic Differential Equations (SDE)
		- Forward diffusion process as SDE
			- Score-Based Generative Modeling through Stochastic Differential Equations
			- Forward diffusion process is discretization of SDE
		- Probability Flow ODE
			- Convert SDE to ODE
			- Flow Matching?
	- Part 3. Accelerated Sampling
		- Generative learning trilemma
		- Advanced ODE/SDE solvers

# Blogs

What are Diffusion Models?
- https://lilianweng.github.io/posts/2021-07-11-diffusion-models/
- Forward process
	- Closed form sampling
	- reparameterization trick
- Backward process
	- VAE
		- *As demonstrated in Fig. 2., such a setup is very similar to VAE*
		- Learn VAE first!
		- [[Variational Autoencoder (VAE)]]
	- Ignoring weighting term
		- Denoising Diffusion Probabilistic Models
	- score-based generative modeling
- bits/dim
- unCLIP

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


What are Diffusion Models?
- https://www.youtube.com/watch?v=fbLgFrlTnGU
- Forward path
- Markov chain
- Отличие от VAE
	- Forward process is fixed. Only one nn is trained.
- ELBO


How AI Image Generators Work (Stable Diffusion / Dall-E) - Computerphile
- https://www.youtube.com/watch?v=1CIpzeNxIhU
	- Oct 4, 2022
- Dall-E 1 or 2 ?
- Объясняет как работает GLIDE?
- GAN vs. Diffusion models
	- Smaller steps for model to get from noise to good-looking image
- Predicting noise
	- Predict only noise added on the last step
	- vs.
	- Predicting all the noise added during all the steps
		- This is what we do
		- That why we need to add some noise back during the generation process.
	- About adding some noise back
- How to direct generation process?
	- How to condition on text in
		- UNet
			- same way as to adding timestamp
			- add embedding to every pixel?
		- Transformer
			- cross-attention
	- To train we need image-text pairs
- Classifier free guidance

Stable Diffusion in Code (AI Image Generation) - Computerphile
- https://www.youtube.com/watch?v=-lz30by8-sU

# Terms

VQ
Vector Quantize


# Overview

Pros
- High quality samples
- Diversity

Cons
- Slow generation process
	- Slow sampling
	- Sequential generation process