
# External

Paper
- Long-CLIP: Unlocking the Long-Text Capability of CLIP
- https://arxiv.org/abs/2403.15378

https://t.me/timeforcv/12

# Links


[[CLIP]]

[[DALL-E]]


# Overview

Summary
- efficient fine-tuning solutions for CLIP to support long-text input
- knowledge-preserved stretching
- primary component matching
- maintain CLIP’s latent space
	- для того чтобы можно было легко заменить в существующих моделях SD? 

Downstream tasks
- text-image retrieval
- text-to-image generation
	- how to use CLIP?
	- Stable Diffusion
		- [[Diffusion Models]]
		- Q: какая конкретно модель используется в этой статье?
	- Paper
		- High-resolution image synthesis with latent diffusion models

image retrieval
- https://paperswithcode.com/task/image-retrieval
- text-image retrieval

Results
- 20% in long caption text-image retrieval
	- как тестируется клип на этой задаче если длина его контекста ограничена 77 токенами, просто обрезается?
- 6% in traditional text-image retrieval tasks
- Benchmarks
	- [[COCO]]
	- [[Flickr30k]]
- Metrics
	- T2I R@1 - COCO

Length of the text token sequence
- context
- CLIP
	- restricted to 77 tokens
	- effective length less than 20
- effective length
	- because of training datasets
	- Q: how to calculate?

text encoder vs. language model

CLIP limitations because of small context
- text
- image
	- limits the image encoder also
- attributes
	- interrelationship between different attributes
	- ‘bag of concepts’ approach
	- Paper
		- When are lemons purple? the concept association bias of vision-language models.


Solutions
- positional embedding
	- Q: original CLIP should already use it, no?

knowledge-preserved stretching
- 20 well-trained positional embedding
- interpolation of insufficiently trained positional embeddings
	- Q: how it was done?
- positional embedding interpolation
	- Paper
		- Extending context window of large language models via positional interpolation.
		- [[RoPE]]

primary component matching
- fine-tuning on the CLIP model using long captions
- problems
	- degradation on the short-text capability
- use fine-grained and coarse-grained image features
	- fine-grained for long captions
	- coarse-grained for short summary
- PCE
	- primary component extraction
	- method for extracting coarse-grained image features from fine-grained image features
		- [[FPN]] ?
	- 3 modules
	- [[PCA]]
- 2 stage tuning
	- fine-grained tuning
	- coarse-grained tuning

Datasets
- vision-language datasets
	- datasets
		- [[Visual Genome (VG)]]
		- LAION
	- short captions
- ShareGPT4V
	- covers rich information including object properties and spatial relationships
	- long captions
- urban-200 dataset
	- introduced in the paper

Exploring the Effective Length of CLIP
- urban-200 dataset
- R@1 do not increase
- текст в датасете действительно содержит полезную информацию после 20 токенов?
	- судя по результатам Long-CLIP - да
	- или Long-CLIP просто лучше работает по другой причине?

# Discussion
