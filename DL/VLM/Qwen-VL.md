
Qwen-VL: A Versatile Vision-Language Model for Understanding, Localization, Text Reading, and Beyond
https://arxiv.org/abs/2308.12966

**GH**
https://github.com/QwenLM/Qwen-VL

**API**
[https://help.aliyun.com/zh/dashscope/developer-reference/vl-plus-quick-start/](https://help.aliyun.com/zh/dashscope/developer-reference/vl-plus-quick-start/)

Qwen-VL-Plus
Qwen-VL-Max
???

# Сводка

**Основные моменты**
multilingual
multiple images
fine-grained perception (grounding, text reading, etc)
тренируют вместе визуальную и языковые части

**Количество параметров**
LLM - 1.8B - 72T
Для VLM используется только Qwen-7B
Total: 9.6B (хорошая табличка в статье)

**Benchmarks**
TouchStone

**Данные для тренировки**
Pretrain: 1.4B (cleaned)
GRIT

# Ссылки

Kosmos-2
Shikra

**Метрики**
EM
VQA Score
ANLS

# Термины

**Точное восприятие**
fine-grained perception
чтение текста
детекция - grounding

few-shot learning
in-context learning
in-context few-shot learning
RICES

# Вопросы


# Обзор

**Две версии**
Qwen-VL
image captioning, question answering, text-oriented question answering, and visual grounding

Qwen-VL-Chat
instruction-tuned vision-language chatbot based on Qwen-VL

# Данные



# Архитектура

**Vision encoder**
Openclip

**LLM**
Qwen-7B

## **Adapter**
Position-aware Vision-Language Adapter

Похож на Q-Former из BLIP-2? Но вместо целого трансформера только один cross-attention слой.
2D absolute positional encodings

## Inputs

**bbox**
bbox для задач детекции или для передачи информации подается как строка и токенизируется как текст.
Вводятся также два специальных токена, между которыми помещается эта информация.


# Обучение

3 стадии

## Pretrain
 
**Данные**
Обзор image-text датасетов
Total: 1.4B (cleaned)
Чистили данные

**Обучение**

**Одна эпоха**
batch size of 30720
50,000 steps
1.5 billion image-text samples

Маленькое разрешение картинок 224х224

Обучают визуальный энкодер и адаптер

## Multi-task Pretrain

**Данные**

Данные с первого этапа, но с большим разрешением?

GRIT

GQA / VQA / DocVQA
У этих датасетов есть трейн сет?

interleaved image-text data

Total: ~100M

**Обучение**
Увеличивают разрешение 448х448
Обучают всю модель

## SFT

[[Instruction tuning]]
Получаем Qwen-VL-Chat

**Данные**
Total: 350K

**Обучение**
Замораживают визуальный энкодер

# Оценка

Image Caption
General Visual Question Answering
Text-oriented Visual Question Answering
Refer Expression Comprehension
Instruction Following

**Image captioning**
greedy search
???

**ScienceQA**
*for ScienceQA, we constrain the model’s output to possible options*
что-то похожее в [[InstructBLIP]]

Pix2Struct-Large (1.3 B)
SOTA DocVQA?
[[Pix2Struct]]


**Refer Expression Comprehension**
Нужно детектировать и локализовать объект
RefCOCO
GRIT
Почему в табличке нет Kosmos-2?

**Instruction Following**
TouchStone