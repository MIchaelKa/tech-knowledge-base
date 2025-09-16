

# External

Notion
- https://www.notion.so/Transformer-6377faf80582440d832405b7b393ad8b

The Illustrated Transformer
- http://jalammar.github.io/illustrated-transformer/

A series of videos on the transformer
- https://www.youtube.com/playlist?list=PLDw5cZwIToCvXLVY2bSqt7F2gu8y-Rqje


# Links

[[BERT]]

# Summary

Output
- If you input n vectors into a transformer it's going to give you n things as an output.

# Size

https://chatgpt.com/c/68bbf387-68c4-832e-b0f2-d2f3d07da451

Original transformer
- 6 encoder layers
- 512 hidden units
- 8 attention heads

Variables
- d_h - скрытая размерность (embedding / model dim)
- d_ff - размер внутреннего слоя, обычно d_ff = 4 * d_h

BERT_base
- transformer layers = 12
- d_h = 768
- attention heads = 12
- parameters = ~109 M

BERT_large
- transformer layers = 24
- d_h = 1024
- attention heads = 16
- parameters = ~335 M

# Positional Encoding

Representing The Order of The Sequence Using Positional Encoding


# Decoder

Как работает decoder
- https://chatgpt.com/c/683cc789-f928-8000-ac1f-f59ff1704961
- режим обучения и режим генерации
- в обоих режимах предсказываются следующие токены для всей последовательности

Шаги работы декодера
- Сначала на вход подается SOS (Start of sequence) токен
- Затем SOS + первый предсказанный токен

Могут ли в процессе работы декодера в режиме инференса изменятся уже предсказанные ранее слова в последовательности?
- Нет
- Поэтому мы и можем использовать KV-cache

Применяем ли мы Masked self-attention во время инференса?
- ДА
- Именно поэтому и возможно использование KV-cache

Что будет, если разрешить смотреть в будущее?
- Это уже не autoregressive модель — это что-то вроде BERT или других denoising autoencoders.
- Убирать masked self-attention в autoregressive моделях не просто делает модель медленнее —  она полностью меняет суть модели
- Модель будет работать дольше но потенциально сможет исправлять свои ошибки?

KV-cache
- [[LLM Accelerating (LLMA)]]
- https://chatgpt.com/c/74067459-18f1-40f8-876e-ef5dfb754d92

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