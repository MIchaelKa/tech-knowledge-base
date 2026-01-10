
# Links

[[Generative Models]]
[[LLM]]
[[Diffusion Models]]
[[DiT]]

# Metrics

Metrics
- FID
	- Fréchet Inception Distance
- CLIP score
- PR in MS-COCO
- IC
	- Inception Score

Metrics
- GPT
	- https://chatgpt.com/c/672cba38-c278-8000-893f-17c2e27babc7
- Why Inception?
	- Inception-v3
	- Historical Precedence / Consistency

Datasets
- COCO

# Models

text2image arena
- https://artificialanalysis.ai/text-to-image/arena

DALL-E 3
- https://t.me/ai_newz/2275
- Consistency Models
	- https://t.me/ai_newz/1787

Midjourney
- https://t.me/ai_newz/3323
	- Midjourney vs. FLUX

Black Forest Labs
- FLUX.1
	- https://t.me/ai_newz/3094
	- SD3
- FLUX
	- https://t.me/ai_newz/3316


[[Stable Diffusion]]


# Local inference


Что можно попробовать запустить самому, локально или в коллабе?
- [[Qwen-Image]]
- [[Stable Diffusion]]
- [[Imagen]]

# Editing

Model for editing?
Select region in the image.
How it's done?

Qwen-Image-Edit
[[Qwen]]


# LLM

Gemini 2.0 Flash
- https://t.me/ai_newz/3740
- ControlNet
- inpainting
- хирургически точное редактирование картинки одним только текстом
	- хочется все таки указывать регион, чтобы избежать текстовых описаний
	- Editing

GPT Image 1
- GPT 4o
- https://t.me/ai_newz/3770
	- LLM-ки генерят изображения хуже, чем чисто диффузионные модели
	- Gemini 2.0 Flash
	- 26 Mar 2025
- https://t.me/ai_newz/3785
- https://openai.com/index/introducing-4o-image-generation/
- https://en.wikipedia.org/wiki/GPT_Image
- Авто-регрессионная модель

GPT Image 1.5

# Nano Banana


wiki
- https://en.wikipedia.org/wiki/Nano_Banana

Nano Banana
- https://gemini.google.com/app/5f00873f490ba45e
- Nano Banana generates a **structured initial draft** and then iteratively refines it, reducing generation time significantly.
- Nano Banana is dLLMS ?
- https://en.wikipedia.org/wiki/Nano_Banana
- [[Diffusion Models]]


Gemini 3 Pro Image (она же Nano Banana Pro)
- https://t.me/ai_newz/4262
- https://blog.google/technology/ai/nano-banana-pro/
- Архитектурно это все также диффузионная голова поверх токенов из текстового энкодера Gemini.

Nano Banana Pro aka Nano Banana 2
- https://t.me/seeallochnaya/3117
- https://deepmind.google/models/gemini-image/pro/

# Papers

Flow Matching for Generative Modeling
- https://arxiv.org/abs/2210.02747
- Yaron Lipman, Ricky T. Q. Chen, Heli Ben-Hamu, Maximilian Nickel, Matt Le
- Flow Matching

# Terms

VQ
Vector Quantize

# Overview

Energy Based Model (EBM)
Contrastive Divergence Algorithm
Need to sample for training
How to get samples? - MCMC

Score Matching
Fisher Divergence
No need to sample for training
Expensive Hessian
Langevin MCMC for inference

Score Based Models
=? Score Matching

Denoising Score Matching
Langevin MCMC for inference

Diffusion Models
Multiple levels of noise-perturbed data densities
Annealed Langevin dynamic

Noise Level
Мы предсказываем градиент noise-perturbed data density
Далее используя этот градиент мы можем сделать сэмпл, но только из noise-perturbed data density текущего уровня шума 
Градиент(скор функция) для данной зашумленной картинки равен добавленному шуму