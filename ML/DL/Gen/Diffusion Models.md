
# External

Notion
- https://www.notion.so/Diffusion-Models-fac71777ec1548ae9fcd343bd2d196e6

# Links

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


# Models

DDPM
DDIM

[[DALL-E]]
[[GLIDE]]
[[DALL-E-2]]

Latent Diffusion
- Paper
	- High-Resolution Image Synthesis with Latent Diffusion Models
	- https://arxiv.org/abs/2112.10752
	- Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer
- TG
	- https://t.me/ai_newz/1056
	- https://t.me/ai_newz/1057
- Links
	- [[Variational Autoencoder (VAE)]]
	- VQ-VAE
		- paper
		- billions of parameters
	- GANs
		- problems with multi-modal distributions
- Linked papers
	- Zero-shot text-to-image generation
		- purely transformer-based approach
	- Deep unsupervised learning using nonequilibrium thermodynamics
		- ? - ссылается как на статью которая вводит DM
- Overview
	- latent space of pretrained autoencoders
	- less aggressive downsampling
	- DM - hierarchy of denoising autoencoders
		- [[Denoising Autoencoder (DAE)]]
	- Using DM beyond image synthesis
	- likelihood-based models
		- ?
	- train DMs in the learned latent space

Imagen
- Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding
- https://arxiv.org/abs/2205.11487
- https://t.me/ai_newz/1186

Stable Diffusion
- https://t.me/ai_newz/1368
- https://github.com/CompVis/stable-diffusion
- CompVis
- LAION-2B
- Imagen
- Grounding DINO
	- https://t.me/ai_newz/1852

# Blogs

What are Diffusion Models?
- https://lilianweng.github.io/posts/2021-07-11-diffusion-models/
- Forward process
	- Closed form sampling
	- reparameterization trick
- Backward process
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