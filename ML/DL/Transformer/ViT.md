
https://www.notion.so/ViT-1242a91c9b98482bb76210eac7c7b0e6

# External Links

HF
[https://huggingface.co/docs/transformers/model_doc/vit](https://huggingface.co/docs/transformers/model_doc/vit)

*Following the original Vision Transformer, some follow-up works have been made*
[[DINO-DETR]]

Implementation
https://github.com/lucidrains/vit-pytorch

YK
- https://www.youtube.com/watch?v=TrdevFK_am4
- [[DINO]]

Сборник статей по улучшению оригинальной архитектуры ViT
https://t.me/ai_newz/883

# Paper

An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale
[https://arxiv.org/abs/2010.11929](https://arxiv.org/abs/2010.11929)


# Links

[[Understanding Deep Learning (UDL) (BOOK)]]

[[Transformer]]

[[Swin Transformer]]

# Overview

Attention
- Attention is quadratic operation.
- This is a limitation of transformer architecture.
- ViT idea - global attention but between patches of an image.
- Compare to CNN, ViT can attend pixels with much larger distance

Local attention
- Can we attend pixels only in some local area(3x3)?
- How it differ from CNNs?
- [[Swin Transformer]] ?

Transformer vs. MLP
- Each neuron in MLP also attends to every other inputs below, but the weight is fixed, in the transformer, it is calculated on the fly.
- Transformers are generalization of MLPs
- Everything is connected to everything

Inductive priors
- Does not have such a strong inductive prior for working with images as CNN have
- Need a lot of data, more than CNN
- Even more data and train without skip connections
	- Why do not use skip connections?

ViT learns the same things that CNN do
- Wavelets

CLS токен
- для суммаризации информации о всем изображении
- не обладает какой-то определенной связанной с ним позиции.
- CLS токен vs. mean(all embeddings)
	- [[BERT]]

 Positional embeddings
- 2D for ViT?
	- TODO