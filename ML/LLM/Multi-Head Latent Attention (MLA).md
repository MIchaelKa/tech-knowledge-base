
[[Attention]]
[[DeepSeek]]
[[RoPE]]
[[KV-Cache]]
[[Transformer]]

Matrix decomposition
- low-rank approximation
- rank factorization
- [[Singular Value Decomposition (SVD)]]

Paper
- The core of MLA is the low-rank joint compression for attention keys and values to reduce Key-Value (KV) cache during inference
- Dimension per head vs. Embedding dimension
- 𝑊^𝑈𝐾, 𝑊^𝑈𝑉 up-projection matrices
- matrix used to produce the decoupled key that carries Rotary Positional Embedding (RoPE)

A Gentle Introduction to Multi-Head Latent Attention (MLA)
- https://machinelearningmastery.com/a-gentle-introduction-to-multi-head-latent-attention-mla/
- Another key technique is that the multiple heads of attention are implemented only in the decompression matrices
- Looks like the formulas here are more complicated than in chatgpt explanation
- 

DeepSeek-V3 Technical Report
- https://t.me/gonzo_ML/3292
- классический Multi-Head Attention (MHA)
	- нарезаются на векторы для отдельных голов внимания
		- нарезаются ?
- сокращает размер необходимого KV-кеша, потому что надо кешировать только низкоразмерные c_t, а не полноразмерные k_t, v_t как раньше
	- как это работает? все еще нужно затем разворачивать c_t в k_t, v_t?
- переиспользование матриц
	- Более того, матрицы проекций из c_t в ключи и значения можно вообще убрать
	- матрицу для k_t (W^uk) можно инкорпорировать внутрь матрицы для получения q_t (W^q)
	- матрицу для v_t (W^uv) внутрь выходной матрицы W^o.
	- как это работает? матрица обучается выполнять сразу две задачи?
- decoupled RoPE
	- [[RoPE]]
	- позиционные эмбеддинги RoPE несовместимы с низкоранговой компрессией KV


Understanding Multi-Head Latent Attention
- https://planetbanatt.net/articles/mla.html
- rank factorization
- You can think of low-rank decomposition as trading memory costs for computation costs
	- At the same time KV-cache is trading computation costs for memory costs
- Perturbations in Low-Rank Decomposition
	- you are only able to travel from rank r matrix to rank r matrix


# chatgpt

- https://chatgpt.com/c/68ca81af-0b54-832b-b0b0-874bcf806f92
- Interactions with RoPE (Rotary Position Embeddings)
- DeepSeek-V2 introduces Partial-RoPE
- Compression is a learned projection
- Retrofitting


Questions

- Decompressing + applying RoPE every time you attend to past tokens would be very expensive.
- Don't we decompress keys and values for all past tokens when we predict next token anyway?
- Latent keys are never fully decompressed per token.
- Instead, the attention computation is reformulated so that the query interacts directly with the latent keys

- You only project the current query into the latent space.
- You never decompress all the old cached keys.
- That means we calculate the attention in the latent space. Is it true? Why previously you told about decompressing k and v to the full size using W_decomp?

- Parenthesis
- Whether you compute attention in latent space or full space depends on how you parenthesize the low-rank factorization.

- What about values?
- Previously there were the following statements
	- values need a decompression step — because you actually need the weighted sum over value vectors in the model’s full dimension d.
	- But that’s just one matrix multiply after the softmax, not per past token per step.
- What the difference? We need to decompress all the values here, right? And it should require the same amount of computation as to reconstruct all the keys.
- Values are weighted with the attention matrix in the latent space too, then we decompress only the final weighted value.

Partial-RoPE

- Divide key on two parts: apply RoPE for the first part, compress the second part without the RoPE

- Am I right that compressed part is much bigger than the part where we apply the RoPE? Or otherwise compression would be no so efficient?

- I still cannot get why we cannot apply RoPE in the latent space? Why it less meaningful?

- Why not define a new RoPE in latent space?
- It wouldn’t correspond to the RoPE that the model was pre-trained with (which lives in full space).
- I want to say that we do not use RoPE to train from scratch? But what if we will? Can we in that case apply RoPE in latent space?

Heads

- K and V are shared between the heads or between the queries?
- Heads

- Am I right that in MLA each head uses the same K and V?
- Does each head have its own decompression matrix, or is it shared?
- Compression matrices are shared.
- Decompression matrices can be per head.
- See *A Gentle Introduction to Multi-Head Latent Attention (MLA)*