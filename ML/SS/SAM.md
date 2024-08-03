
SAM
Segment Anything

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
Foundation model

GPT-3 moment for segmentation
Promptable segmentation
Zero-Shot

**Количество параметров**
Image Encoder - 632M параметров.
Encoder запросов и decoder масок - 4M параметров.

**Оценка**

**Данные для тренировки**
SA-1B Dataset
1 млрд масок на 11 млн изображений
https://ai.meta.com/datasets/segment-anything/

# Links

[[Semantic Segmentation]]

[[Zero-Shot (ZSL)]]
zero-shot transfer

*We take inspiration from NLP*
GPT-3

Interactive segmentation

**Transformers**
[[DETR]]
[[ViT]]

# Papers

MAE
Masked autoencoders are scalable vision learners

Perpixel classification is not all you need for semantic segmentation.
*The paper where is more detailed description of how Mask decoder work?*
# Overview

**Foundation model**
Foundation model for image segmentation
*foundation model for image segmentation: a **promptable** model that is trained on diverse data and that can adapt to specific tasks, analogous to how prompting is used in natural language processing models.*

What does it mean, foundation model?
[https://en.wikipedia.org/wiki/Foundation_model](https://en.wikipedia.org/wiki/Foundation_model)

**Speed and annotations**
*model needs to run in real time on a CPU in a web browser to allow our annotators to use SAM interactively*

# Promptable segmentation

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
https://chatgpt.com/c/4869e3ec-78d4-44e9-b392-fe307d6f948d

**Loss**
focal loss and dice loss
focal loss for semantic segmentation?

# Data

*The data was collected using SAM.*
Как это работает когда модель ошибается?
[[Pseudo Labeling]]
