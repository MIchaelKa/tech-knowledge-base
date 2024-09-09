
https://www.notion.so/Transformer-6377faf80582440d832405b7b393ad8b

# Summary

Output
- If you input n vectors into a transformer it's going to give you n things as an output.

# Links



# Topology

[[Network Topology]]

https://github.com/karpathy/ng-video-lecture/blob/master/gpt.py

Questions
- self.dropout(wei) in attention head ?

## Layer Normalization

Why do transformers use layer norm instead of batch norm?
- https://stats.stackexchange.com/questions/474440/why-do-transformers-use-layer-norm-instead-of-batch-norm
- A less known issue of BatchNorm is that how hard it is to parallellize batch-normalized models.
- Sentence length
	- In NLP tasks, the sentence length often varies
	- In transfromer LayerNorm normalizes only over the last dimension (feature dimension), and didn't not normalizes over sentence length
	- What if for NLP, do not average over sentence length when use BatchNorm?

Residual connections + Layer Normalization
- Inside each sub-layer in encoder block (self-attension and fc)
- Separately for each head?

pre/post layer norm
- LN before or after activation
- LN before or after residual
- post layer norm
	- original
	- LayerNorm(X+Z)
- pre layer norm
	- improved
	- improved gradient flow w/o Normalization on the way
	- как ты себе объяснял почему pre normalization лучше?


pre normalization vs. past normalization
- https://stackoverflow.com/questions/77864704/annotated-transformer-why-x-dropoutsublayerlayernormx
- Pre-LN is a more pure and direct highway for info flow

On Layer Normalization in the Transformer Architecture
https://arxiv.org/abs/2002.04745


## Activation function

ReLU только в FFNN слое?
dropout вместо ReLU

# Attention masks
Виды аттеншена

**Causal mask attention**
То что используется в декодере, когда токены не могут смотреть в будущее.

Self-attention mask schemes
https://www.researchgate.net/figure/Self-attention-mask-schemes-Four-types-of-self-attention-masks-and-the-quadrant-for-the_fig4_363688134


- Self-Attention
- Cross-Attention
- Causal mask attention
	- Mask-Attention
	- Masked self-attention
- Multi-Head Attention