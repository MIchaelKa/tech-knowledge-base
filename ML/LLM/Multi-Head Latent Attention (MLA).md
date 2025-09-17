
[[Attention]]

[[DeepSeek]]
[[RoPE]]
[[KV-Cache]]


Matrix decomposition
- low-rank approximation
- rank factorization
- [[Singular Value Decomposition (SVD)]]


K and V are shared between the heads or between the queries?


Multi-Head Latent Attention (MLA)
- https://machinelearningmastery.com/a-gentle-introduction-to-multi-head-latent-attention-mla/

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
	- 


chatgpt
- https://chatgpt.com/c/68ca81af-0b54-832b-b0b0-874bcf806f92
- Interactions with RoPE (Rotary Position Embeddings)
- DeepSeek-V2 introduces Partial-RoPE


Questions

- Decompressing + applying RoPE every time you attend to past tokens would be very expensive.
- Don't we decompress keys and values for all past tokens when we predict next token anyway?
- Latent keys are never fully decompressed per token.
- Instead, the attention computation is reformulated so that the query interacts directly with the latent keys

- You only project the current query into the latent space.
- You never decompress all the old cached keys.
- That means we calculate the attention in the latent space. Is it true? Why previously you told about decompressing k and v to the full size using W_decomp?