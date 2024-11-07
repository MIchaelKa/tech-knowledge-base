
TG
- https://t.me/ai_newz/877

Paper
- GLIDE: Towards Photorealistic Image Generation and Editing with Text-Guided Diffusion Models
- https://arxiv.org/abs/2112.10741
- Citations (2810)
- Alex Nichol, Prafulla Dhariwal, Aditya Ramesh, Pranav Shyam, Pamela Mishkin, Bob McGrew, Ilya Sutskever, Mark Chen
- OpenAI

Overview
- Text-Guided Diffusion Models
- Parameters
	- 3.5B - 64x64
		- намного меньше чем DALL-E-1 - 12B
	- 1.5B - upsampling model to 256x256
- Upsampling model
	- DM
- Inpainting
	- Explicitly trained DM for inpainting
- Metrics
	- PR in MS-COCO
		- ???
	- IC - Inception Score

YK
- https://www.youtube.com/watch?v=gwI6g1pBD84
- 29.12.2021
- Text-Guided Diffusion
	- CLIP Guided
	- CF Guided
		- works better
	- сравнение двух подходов в статье
- Predicting noise
	- Predict only noise added on the last step
- Conditioning
	- Adding text or class to generation
	- Class conditional model
		- $\epsilon = (x_t, t, y=cat)$
		- one-hot vector embedding vector for class representation
		- Как совместить эмбединги индекса и класса с картинкой $x_t$ ?
			- Diffusion models from scratch in PyTorch
	- Text conditional model
		- CLIP embeddings?
		- Transformer model
- Guided Diffusion
	- We want to push model to the certain direction
	- Classifier guidance
		- ImageNet classifier
		- Take gradient for image
		- DeepDream
		- cs231n
	- CLIP Guided Diffusion
		- Take gradient for image
		- Обновляем не веса модели, а картинку, так чтобы CLIP(img,text) выдавал большую схожесть
		- CLIP(img,text) - inner product of embeddings
	- Classifier-Free guidance
		- YK: Looks like trick, we shouldn't do that.
		- Во время тренировки иногда не предоставляем информацию о $y$
			- $\epsilon = (x_t, t, y=0)$
		- Во время инференса прибавляем к картинке вектор
			- $\epsilon (x_t, t, y) -\epsilon (x_t, t, 0)$
		- Pros
			- Это также позволяет использовать дополнительные данные для обучения (картинки у которых нет подписи)
			- Не нужна дополнительная модель
		- Guidance scale
			- Просто предсказывая $\epsilon (x_t, t, y)$, у нас нет информации в какую сторону можно усилить сигнал
			- При S=1 - no guidance
		- Потенциально можно использовать hard-negative sampling, contrastive sampling
			- Еще сильнее уточняем направление
	- Предположение почему CF Guided работает лучше
		- DM defines adversarial examples
			- What does it mean?
			- [[Adversarial Attacks]]
	- Noised classifier
		- для CLIP Guided Diffusion
		- noised clip verson
		- классификатор который умеет работать с зашумленными картинками, иначе такие картинки будут out of distribution