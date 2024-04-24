
CogVLM: Visual Expert for Pretrained Language Models
[https://arxiv.org/abs/2311.03079](https://arxiv.org/abs/2311.03079)


# Сводка

**Основные моменты**
Увеличенное количество параметров визуальной части
Deep fusion
Trainable visual expert
Grounding

**Количество параметров**
CogVLM-17B
10B vision parameters
7B language parameters.

**Benchmarks**
Visual7W
TDIUC

**Данные для тренировки**

# Ссылки

**Papers**
A generalist framework for panoptic segmentation of images and videos

**RoPE**
Rotary Position Embedding
[https://paperswithcode.com/method/rope](https://paperswithcode.com/method/rope)


# Термины

**shallow alignment**
про адаптеры между визуальной и языковой частью

# Вопросы

p-tuning

# Обзор

Говорят о том что естественным подходом в области VLM брать уже готовую LLM. Что трудно обучить VLM которая бы обладала той же лингвистической способностью.

Затем говорят о деградации NLP способностей у VLM моделей.
NLP способности сравниваются на NoCaps CIDEr

**Deep fusion**
deep fusion between vision and language information
Показывают недостатки **shallow alignment**
[[GLIP]]
Должны ли мы тут сослаться также на [[Flamingo]]?

Идея пришла при сравнении p-tuning vs. LoRA
*in the shallow alignment methods, the image features act like the prefix embedding in p-tuning*

**Совместное обучение визуальной и языковой части**
Подход использованный [[Qwen-VL]], PaLI

*making the language model trainable during VLM pretraining will lead to catastrophic forgetting*
PaLM-E

**Решение предложенное в этой статье**
trainable visual expert
*image features in the sequence use a new different QKV matrix and MLP layer with the text features


# Данные


# Архитектура

**LLM**
Vicuna-7B

**Visual encoder**
EVA2-CLIP-E
10B параметров? Нет, не здесь, отдельные параметры тренируются в Trainable visual expert

**Trainable visual expert**
По сути еще один трансформер величиной с LLM
Удваивается количество параметров, FLOPS остаются те же.

Могут ли визуальные и текстовые эмбеддинги аттендиться между собой в данной архитектуре?

# Обучение


# Оценка

