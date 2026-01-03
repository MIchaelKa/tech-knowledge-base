
Paper
- High-Resolution Image Synthesis with Latent Diffusion Models
- https://arxiv.org/abs/2112.10752
- Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer
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

TG
- https://t.me/ai_newz/1056
- https://t.me/ai_newz/1057

Links
- [[Variational Autoencoder (VAE)]]
- VQ-VAE
	- paper
	- billions of parameters
- GANs
	- problems with multi-modal distributions

YT 1
- https://www.youtube.com/watch?v=wuwByIh5kDU
- classifier free guidance - ?

YT 2
- https://www.youtube.com/watch?v=0khrry76voI
- HF diffusers library
- UNet
- Attention
	- spacial self-attention
- LinearAttention
	- channel wise attention


ChatGPT
- https://chatgpt.com/c/6958346e-2ab4-8330-9f1d-4d390b0a72a7


wiki
- https://en.wikipedia.org/wiki/Latent_diffusion_model
- VAE
	- self-attention mechanism near the end
		- TODO

# Questions

- Как работает добавление шума в Latent Diffusion если эмбеддинг после VAE энкодера уже имеет стандартное? нормальное распределение?
- KL-лосс лишь _мягко тянет_ к $\mathcal{N}(0,I)$, но не заставляет туда лечь.


- VAE and [[Normal Distribution]]
