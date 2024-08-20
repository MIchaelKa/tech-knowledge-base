
Pix2Struct: Screenshot Parsing as Pretraining for Visual Language Understanding
[https://arxiv.org/abs/2210.03347](https://arxiv.org/abs/2210.03347)

# Ссылки
**References**
Donut
T5
GIT2

# Сводка

**Количество параметров**
282M
1.3B

**Benchmarks**
ChartQA
TextCaps
DocVQA

**Datasets**
AI2D
C4

**Метрики**
BLEU
CIDEr

**Ablations**
Warmup
Masking
Screenshot Parsing


# Вопросы

**Термины**
high-resource domains
surface-level features

1.

>we finetuned Donut on tasks where a purely visual baseline was unavailable

Разве Donut это не purely visual ?



# Обзор

Ставили целью сделать базовую модель, которую затем можно файнтюнить для большого числа финальных задач.
T5


# Основные идеи и улучшения

train dataset - predict html from masked screenshots
variable-resolution inputs
single modality

**Train dataset**
80M screenshots of web pages
URLs in the C4 corpus

**Variable-resolution inputs**
variable-resolution inputs for vision transformers (ViT)
prevent distortion

это то чего не хватало Никите?
pad/unpad эксперимент
MobileLLM

ViT масштабирует картинку до фиксированного разрешения и затем нарезает на патчи фиксированного размера. Получается всегда одинаковое количество патчей.

Pix2Struct масштабирует с сохранением AR, чтобы получалось максимальное количество патчей определенного размера в пределах заданной максимальной длины.

Почему это называется **variable-resolution** ?


**Single modality**
render text on top of the images

# Training

Использовалась ли какие-то еще данные кроме screenshot parsing, для пре-трейна?
Делают ли они файнтюн?

**Finetune**
Новая стратегия как раз и заключается в том чтобы отрисовывать текст прямо на самой картинке сверху.
Делают так для существующих датасетов?

**Warmup**
curriculum learning
Разогрев на простой OCR задаче.
BooksCorpus

input sequence length
128 patches
2048 patches

Почему количество входной последовательности больше для пре-трейна?

BLEU
метрика которую использовали для пре-трейна