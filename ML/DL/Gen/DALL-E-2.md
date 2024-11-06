
unCLIP

# External

https://openai.com/index/dall-e-2/

DALL-E 2 - Pytorch
- https://t.me/ai_newz/1093
- https://github.com/lucidrains/DALLE2-pytorch

gonzo_ML
- https://t.me/gonzo_ML/919
- Декодер это модифицированный GLIDE
- Про GLIDE
	- *картиночные CLIP эмбеддинги добавляются к эмбеддигам временных шагов диффузионной модели*
		- откуда беруться картиночные эмбединги, если для этого нужна картинка?
		- результат работы prior сети
- Парная репрезентация
- DDIM

# Paper

Hierarchical Text-Conditional Image Generation with CLIP Latents
- https://arxiv.org/abs/2204.06125
- Aditya Ramesh, Prafulla Dhariwal, Alex Nichol, Casey Chu, Mark Chen
- Citations (5485)
- DALL-E-2

# Links

[[DALL-E]]

[[GLIDE]]

# Videos

How does DALL-E 2 actually work?
- https://www.youtube.com/watch?v=F1X4fHzF4mQ
- Text embeddings
	- CLIP
	- Text embeddings vs. CLIP embeddings - ?
- Prior network
	- Two options
		- Autoregressive prior
		- Diffusion prior
	- Model for processing text embedding to image embedding
	- How diffusion model works here?
- Decoder
	- Another diffusion model
- GLIDE
	- What text embeddings used in GLIDE?