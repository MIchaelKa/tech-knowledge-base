
Rotary Positional Embeddings (RoPE)

Positional Encoding
- [[Transformer]]

# External

Paper
- RoFormer: Enhanced Transformer with Rotary Position Embedding
- https://arxiv.org/abs/2104.09864

Other
- https://nn.labml.ai/transformers/rope/index.html

pwc
- https://paperswithcode.com/method/rope
- not works anymore

Inside RoPE: Rotary Magic into Position Embeddings
- https://learnopencv.com/rope-position-embeddings/
- Absolute Position Embeddings (The First Generation)
- Relative Position Embeddings (Second Generation)

RoPE (Rotary positional embeddings) explained: The positional workhorse of modern LLMs
- https://www.youtube.com/watch?v=GQPOtyITy54

absolute position vs. relative position

paired dimensions

chatgpt
- https://chatgpt.com/c/68c13305-7c88-8332-af17-78b2b7d19317


1
- The dot product after rotation depends only on i−j i.e. relative distance.
- But we also want to have a semantic meaning in those dot products, right?
- As I understand q and k vectors before applying the RoPE rotation already have some angle between them and this angle should capture the semantic meaning, how after applying the RoPE rotation we can distinguish between them?
- I cannot imagine how only magnitude of the vector in the doc product can affect similarity, it just scale the things. So even two large orthogonal vectors will have zero similarity score.

2
- sinusoidal positional encodings are absolute
- attention still sees absolute positions; it doesn’t explicitly model relative distances
- why?

3
- Why RoPE is not compatible with Multi-head Latent Attention (MLA)?
- [[Attention]]
- TODO. Learn MLA first.
