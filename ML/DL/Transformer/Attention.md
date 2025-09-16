
# External

Notion
- https://www.notion.so/Attention-2b94c9b8c6bb46ff944f7e964f47923b

Attention alternatives
- https://www.notion.so/Attention-alternatives-8989f21a2c7845628c3b5d9ba38a1724


# Attention masks

Виды аттеншена

**Causal mask attention**
То что используется в декодере, когда токены не могут смотреть в будущее.

Self-attention mask schemes
https://www.researchgate.net/figure/Self-attention-mask-schemes-Four-types-of-self-attention-masks-and-the-quadrant-for-the_fig4_363688134

Attention types
- Self-Attention
- Cross-Attention
- Causal mask attention
	- Mask-Attention
	- Masked self-attention
- Multi-Head Attention


# Attention optimization

[[DeepSeek]]

- Multi-Head Attention (MHA)
	- классический вариант
- Multi-Query Attention (MQA)
	- K и V шарятся между всеми головами внимания (что сильно ускоряет инференс и слегка ухудшает качество)
- Grouped-Query Attention (GQA)
	- Среднее между MHA and MQA
- Multi-Head Latent Attention (MLA)


# Multi-Head Latent Attention (MLA)

Multi-Head Latent Attention (MLA)
https://machinelearningmastery.com/a-gentle-introduction-to-multi-head-latent-attention-mla/

low-rank approximation
[[Singular Value Decomposition (SVD)]]

[[DeepSeek]]