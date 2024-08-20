
SAM
Segment Anything

paper
*my thoughts*

# External Links

**Paper**
Segment Anything
https://arxiv.org/abs/2304.02643

**Official**
https://segment-anything.com/

Introducing Segment Anything: Working toward the first foundation model for image segmentation
https://ai.meta.com/blog/segment-anything-foundation-model-image-segmentation/

**TG**
https://t.me/ai_newz/1846


# Summary

**Key moments**
- Foundation model
	- GPT-3 moment for segmentation
	- Promptable segmentation
	- Zero-Shot
		- [[Zero-Shot (ZSL)]]
		- zero-shot transfer
- SA-1B Dataset

**Parameters**
- Image Encoder - 632M
- Request encoder and mask decoder - 4M

Evaluation
- *IoU?*
- *Segmentation metrics?*

# Links

[[Semantic Segmentation]]


*We take inspiration from NLP*
GPT-3

Interactive segmentation
human-in-the-loop

**Transformers**
[[DETR]]
[[ViT]]

# Papers

- MAE
	- Masked autoencoders are scalable vision learners
- Perpixel classification is not all you need for semantic segmentation.
	- *The paper where is more detailed description of how Mask decoder work?*

# Ideas

SAM - CV Foundation model
GPT - NLP Foundation model

self-driving foundation models?
https://en.wikipedia.org/wiki/Self-driving_car

# Questions

token-to-image and image-to-token attentions
- just changing Q and K?
	- first Q from image embeddings, K from output tokens
	- then Q from output tokens, K from image embeddings


# Overview

**Speed and annotations**
*model needs to run in real time on a CPU in a web browser to allow our annotators to use SAM interactively*

# Foundation model

Foundation model for image segmentation
*foundation model for image segmentation: a **promptable** model that is trained on diverse data and that can adapt to specific tasks, analogous to how prompting is used in natural language processing models.*

What does it mean, foundation model?
[https://en.wikipedia.org/wiki/Foundation_model](https://en.wikipedia.org/wiki/Foundation_model)

## Promptable segmentation

Prompts: clicks, boxes, text, and so on

Examples of text prompts:
???

Before:
*Before SAM was released, creating an accurate object segmentation model for specific image tasks required highly specialized work by technical experts*
After:
*out-of-the-box use cases via prompting techniques*

*model trained for promptable segmentation can perform a new, different task at inference time*

# Architecture


**Mask decoder**
It needs to output the same number of embeddings as it was produced by encoder in order to have correspondence with original image.

**How mask decoder in Segment Anything(SAM) works?**
- only request
	- https://chatgpt.com/c/4869e3ec-78d4-44e9-b392-fe307d6f948d
- request + paper
	- TODO

**Token encoder**
*token encoder provides the needed number of tokens?*
output tokens (was seen in AM-2)

**Loss**
focal loss and dice loss
focal loss for semantic segmentation?

# Data

https://ai.meta.com/datasets/segment-anything/

*The data was collected using SAM.*
Как это работает когда модель ошибается?
[[Pseudo Labeling]]


data engine in Segment Anything (SAM) vs. Pseudo Labeling
- only request
	- https://chatgpt.com/c/d3c86e71-0c9e-4f19-b963-972a8bf0a5f4
- request + paper
	- https://chatgpt.com/c/df1920dd-9b9d-4e10-ab04-648cf516f6bc

3rd stage (fully automatic stage ) in Segment Anything (SAM) vs. Pseudo Labeling
- request + paper
	- https://chatgpt.com/c/df1920dd-9b9d-4e10-ab04-648cf516f6bc


SA-1B Dataset
- ENG
	- Data for training
	- 1B masks on 11M images
- RUS
	- Данные для тренировки
	- 1 млрд масок на 11 млн изображений

common public segmentation datasets
- ADE20k
- COCO

data engine
- human-in-the-loop?
- *how SA-1B Dataset was built*
- three stages
	- model-assisted manual annotation stage
		- interactive segmentation
		- “brush” and “eraser” tools
		- *using classical CV such as morphology(link?)?*
		- *Adobe tools?*
		- model-assisted annotation runs in real-time directly inside a browser
			- precomputed image embeddings
		- did not collect these names or descriptions *provided by annotator*
			- *why so?*
		- At the start of this stage, SAM was trained using **common public segmentation datasets *(should be a link?)***
		- After sufficient data annotation, SAM was retrained using only newly annotated masks.
		- 4.3M masks from 120k images
	- semi-automatic stage
		- To detect confident masks, we trained a bounding box detector
		- *They used Faster-RCNN for this?*
		- *What about MASK-RCNN? Was data from MASK-RCNN used in first stages of training? Probably in one of public datasets?*
		- 5.9M masks in 180k images
		- As in the first stage, we periodically retrained our model on newly collected data (5 times).
	- fully automatic stage
		- confident masks
			- IoU prediction module
		- stable masks
			- thresholding the probability map at 0.5 − δ and 0.5 + δ results in similar masks
		- NMS