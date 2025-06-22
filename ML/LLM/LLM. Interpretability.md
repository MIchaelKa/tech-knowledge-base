
Anthropic

mechanistic interpretability
- механистические интерпретации
- Transformer Interpretability

Transformer Interpretability
- https://t.me/cryptovalerii/768
- https://arena-chapter1-transformer-interp.streamlit.app/


# Overview

scratchpad
- model scratchpad
- reasoning?
- https://chatgpt.com/c/683b79d4-a7a8-8000-9cde-dcc6d2eb05ea

эвристики в LLM
- https://t.me/boris_again/3178
- https://chatgpt.com/c/6820b3e4-994c-8000-964f-84baafe1ff47
- эвристическая схема для сложения?
- Toy Models of Addition от Anthropic

# Circuits

Circuits
Circuits Anthropic
Circuits transformers

Liinks
- [[Transformer]]
- [[LLM Accelerating (LLMA)]]

On Interpretability
- https://t.me/gonzo_ML/3200
- посты Криса Олаха
- developmental interpretability

Chris Olah
- https://colah.github.io/

Distill
- https://distill.pub/2020/circuits/
- reverse engineer of vision models

Zoom In: An Introduction to Circuits
- https://distill.pub/2020/circuits/zoom-in/


Transformer Circuits Thread
- https://transformer-circuits.pub/


A Mathematical Framework for Transformer Circuits
- https://transformer-circuits.pub/2021/framework/index.html
- Dec 22, 2021
- Vocab
	- circuits
	- mechanistic interpretability
- notebooklm
	- TODO
- attention-only transformer
	- toy model
	- in this paper we will study transformers with two layers or less which have only attention blocks
	- we've also simply had much less success in understanding MLP layers so far
	- we also ignore layer normalization
- attention head
	- formulation
		- “concatenate and multiply” formulation (vs.)
		- independent operations, each outputting a result which is added into the residual stream
			- DONE: why it mathematically equal?
				- explained later
	- Attention Heads are Independent and Additive
	- The fundamental action of attention heads is moving information.
- induction head
	- specific attention heads
	- can explain in-context learning in these small models
	- very general in-context learning algorithm
- in-context learning
	- ?
- mathematical framework for understanding transformers
	- ?
- bigram statistics
	- NGram
	- https://chatgpt.com/c/680e96ac-b04c-8000-b614-ec0933b9c9af
	- skip-trigram tables
- Transformer Overview
	- equivalent ways to represent the same computation
	- We focus on autoregressive, decoder-only transformer language models, such as GPT-3.
	- token unembedding
		- linera layer + softmax ?
		- unembedding is a matrix that maps from the model’s hidden space (like `d_model = 768`) to the vocabulary space (say, 50,000 tokens)
- residual stream
	- https://chatgpt.com/c/68457d96-8da8-8000-b69c-393495a788f4
	- The residual stream is a single high‑dimensional vector that gets updated cumulatively as tokens are processed.
	- In transformers, the residual stream vectors are often called the “embedding.”
	- residual stream often dedicates subspaces to tokens other than the present token, breaking the intuitions the embedding terminology suggests
	- residual stream as a communication channel
	- The residual stream has a deeply linear structure.
		- vs. ResNet 
		- implicit "virtual weights"
		- There is no non-linearity applied to the residual stream itself in transformer
	- virtual weights
	- high demand on residual stream bandwidth
- Attention Heads are Independent and Additive
	- output matrix
	- The concatenate definition is often preferred because it produces a larger and more compute efficient matrix multiply.
- Attention Heads as Information Movement
	- They typically write to different subspace than they read
	- В отдельно взятом стриме Attention Heads пишет в одно и тоже место (subspace) ?
- Tensor Product / Kronecker Product Notation
	- https://transformer-circuits.pub/2021/framework/index.html#notation-tensor-product
	- https://en.wikipedia.org/wiki/Kronecker_product
	- A ⊗ B ∈ ℝ^{(m·p) × (n·q)}
	- per position vs. across positions
		- per position - looking only at one token representation at time
		- across position
			- how attention works
			- matrix of interactions
	- Both per-position and cross-position operations in a single unified structure
	- linear maps from matrices to matrices
	- Step-by-Step with Kronecker Products
	- Y = W_o * A * W_v * X
		- why simple 2D matrix multiplication doesn't suffice to express full Transformer computations like attention
		- Y = (A @ (X @ W_v)) @ W_o     # ← this works
	- [[MIT 18.065. Matrix Methods.]]
- Zero-Layer Transformers
	- Because the model cannot move information from other tokens, we are simply predicting the next token from the present token.
	- optimal behavior​ is to approximate the bigram log-likelihood
- One-Layer Attention-Only Transformers
	- ensemble of a bigram model and several "skip-trigram" models
	- bilinear form


