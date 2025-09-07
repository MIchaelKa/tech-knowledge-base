
Mixtral of Experts
Sparse Mixture of Experts (SMoE)
vs.
Mixture of Experts (MoE)

Mistral.AI

# External

DeepSeek review
- https://t.me/gonzo_ML/3293

HF
- https://huggingface.co/blog/moe

A Visual Guide to Mixture of Experts (MoE)
- https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-mixture-of-experts
- dense model vs. sparse model
	- vs. dropout
- Experts
	- experts learn more fine-grained information than entire domains
	- experts tend to focus on syntax rather than a specific domain
	- What about more deep layers?
- Router
	- gate network
	- FFNN + softmax
	- Determines which tokens are sent to which experts
	- В одном и той же входной последовательности разные токены проходят через разные FFNN
	- Что значит токен прошел через декодер? - Предсказали следующий токен для этого токена.
- MoE
	- Dense MoE vs. Sparse MoE
	- Sparse MoE was introduced my Mistral.AI?
- Load Balancing
	- Expert Capacity
		- GShard
		- limit the amount of tokens a given expert can handle
		- token overflow
	- Switch Transformer
		- One of the first transformer-based MoE
		- capacity factor
			- If we increase the capacity factor each expert will be able to process more tokens.

GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding
- https://arxiv.org/abs/2006.16668
- Dmitry Lepikhin

Switch transformers: Scaling to trillion parameter models with simple and efficient sparsity
- https://arxiv.org/abs/2101.03961

Switch Transformers
- https://t.me/gonzo_ML/472
- модели от гугла на 1,6T в 2021
- модели от гугла на 137B в 2017 до выхода первой GPT
- expert-parallelism
	- не совсем понятно чем это отличается от model-parallelism


# Mixtral of Experts

YK
- https://www.youtube.com/watch?v=mwO6v4BlgZQ

Mixtral of Experts
- https://arxiv.org/abs/2401.04088

Links
- SwiGLU
- Paired feedback dataset

Модель
- Mixtral 8x7B
- Контекст: 32k

Sparse Mixture of Experts (SMoE)
- Это то что появляется в этой статье?

Mistral
- Не говорят ничего про свои данные и откуда они их берут.
- Самая открытая лицензия.
- Apache 2.0

Mixtral 8x7B
Sparse Mixture of Experts (SMoE)
Для каждого токена используется только подмножество всех параметров

Mixture of Experts
Большинство параметров в FFN слое

Каждая матрица в FFN слое имеет большой размер.
Делаем несколько разных матриц в FFN слое.
Делаем каждую такую матрицу меньше.
Просто уменьшаем hidden_size или [[LoRA]] ?

Слой аттеншена уже был разделен похожим образом - MHA
[[Distributed Systems]]

Разделяем FFN слой на несколько разных матриц
разные матрицы == эксперты

**Sparse Mixture of Experts (SMoE)**
Расширяет концепцию MoE дальше
Каждый токен идет не через все, а только через определенное подмножество экспертов.
Routing Neural Network - [[Classification]] network

**Sparse Softmax**
$Softmax(TopK(x*W_G))$
Большинство выходов - нули

**Expert Parallelism**
[[Distributed Training]]
Model Parallelism

**Sparse paremeter count**
Полное количество параметров, растет с увеличением количества экспертов

**Active paremeter count**
Количество параметров участвующих в вычислении одного forward pass
Растет с размером разрешения эмбеддинга.
Растет с количеством экспертов на токен.

