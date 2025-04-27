
Mixtral of Experts
Sparse Mixture of Experts (SMoE)
vs.
Mixture of Experts (MoE)

Mistral.AI

# Внешние ссылки


A Visual Guide to Mixture of Experts (MoE)
- https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-mixture-of-experts

Paper
- Mixtral of Experts
- https://arxiv.org/abs/2401.04088

HF
https://huggingface.co/blog/moe

YK
https://www.youtube.com/watch?v=mwO6v4BlgZQ

# Сводка

**Основные моменты**

**Модель**
Mixtral 8x7B
Контекст: 32k

# Ссылки

SwiGLU

# Термины

Paired feedback dataset

# Вопросы

Sparse Mixture of Experts (SMoE)
Это то что появляется в этой статье?

# Обзор

**Mistral**
Не говорят ничего про свои данные и откуда они их берут.
Самая открытая лицензия.
Apache 2.0

Mixtral 8x7B
Sparse Mixture of Experts (SMoE)
Для каждого токена используется только подмножество всех параметров

**Mixture of Experts**
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



# Количество параметров

**Sparse paremeter count**
Полное количество параметров, растет с увеличением количества экспертов

**Active paremeter count**
Количество параметров участвующих в вычислении одного forward pass
Растет с размером разрешения эмбеддинга.
Растет с количеством экспертов на токен.

