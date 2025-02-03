
BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models
[https://arxiv.org/abs/2301.12597](https://arxiv.org/abs/2301.12597)

HF
[https://huggingface.co/docs/transformers/model_doc/blip-2](https://huggingface.co/docs/transformers/model_doc/blip-2)


# Ссылки

Flamingo

**HNM**
hard negative mining strategy
Align before fuse: Vision and language representation learning with momentum distillation.

**FlanT5**
encoder-decoder-based LLMs

**OPT**
OPT: open pre-trained transformer language models

# Термины

VLP
Vision-language pre-training (VLP)

Q-former
Querying Transformer
query vectors

image encoder
???

# Сводка

**Количество параметров**
Q-Former: 188M == BERT_base + cross attention layers

**Benchmarks**
VQAv2
NoCaps
Flickr

**Train dataset**
use the same pre-training dataset as BLIP
129M images in total

COCO
[[Visual Genome (VG)]]
CC3M
CC12M
SBU
115M images from the LAION400M

# Вопросы

1.
image-to-text generation loss

# Обзор

Отвечают на вопрос, как делать эффективный пре-трейн для MLLM
Замораживают и vision encoder и LLM.
Между ними тренируют Querying Transformer.

# Архитектура

## Q-former
Querying Transformer

Легкий трансформер, играет роль адаптера между двумя модальностями.
Тренируется в два этапа.

Уменьшает количество визуальных патчей.
Смотри **bottleneck architecture** ниже

**Query vectors**
set of **learnable** query vectors
Похожие query vectors какие были у [[DETR]]?

Вспомнить как работает cross-attention
Количество **query vectors** и **image feature**s разное

**bottleneck architecture**
query vectors < image features
Авторы пишут что это позволяет эффективнее извлекать визуальную информацию.
Как это работает?
Количество выходной последовательности **Q-former**, равно количеству query vectors

---

Состоит из двух частей

1.
Имеет cross-attention слои для взаимодействия с фичами от image encoder

2.
Текстовый трансформер который может работать и как енкодер и как декодер.
Как заставить работать BERT как декодер?

## Состав

**Vision encoder**
ViT-L/14 from CLIP
*uses the second last layer’s output features*

**LLM**
OPT model family
FlanT5


# Обучение

Тренируется только **Q-former**

**Первая фаза**
Тренируются только vision encoder и Q-former
Тренировка похожа на BLIP
*three pre-training objectives*

1.1
**ITC**
Image-Text Contrastive Learning

*unimodal self-attention mask, where the queries and text are not allowed to see each other*

Как подаются на вход **query vectors** и input text.

1 вариант
Вместе в одной последовательности?
Используется один и тот-же self-attention слой для обоих последовательностей, как это работает? Копируют веса, чтобы вычислять параллельно, а не последовательно?

То что в итоге окажется в InstructBLIP?

2 вариант
**query vectors** и input text подаются последовательно

трансформеру все равно на порядок токенов в последовательности

1.2
**ITG**
Image-grounded Text Generation

*Since the architecture of Q-Former does not allow direct interactions between the frozen image encoder and the text tokens, the information required for generating the text must be first extracted by the queries, and then **passed to the text tokens via self-attention layers**.*

Какой текст нужно сгенерировать на этом этапе?

1.3
**ITM**
Image-Text Matching