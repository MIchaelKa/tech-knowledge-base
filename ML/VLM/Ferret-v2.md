
Apple

Ferret-v2: An Improved Baseline for Referring and Grounding with Large Language Models
https://arxiv.org/abs/2404.07973

Paper Review
https://artgor.medium.com/paper-review-ferret-v2-an-improved-baseline-for-referring-and-grounding-with-large-language-4aff89652225


# Сводка

**Основные моменты**
Referring and grounding
Upscaling input image
3 этапная тренировка
DINO

**Количество параметров**
7B
13B

**Данные для тренировки**
LVIS
GRIT

**Benchmarks**


# Ссылки

[[DINOv2]]

**Referring and grounding**
Kosmos-2
Shikra
[[Ferret]]
Ничего не говорят про Qwen

GLIPv2


# Термины

**Any resolution**
Подход с кропами как в LLaVA-Next


# Вопросы


# Обзор

pseudo-labeled VQA and OCR datasets


# Upscaling input image
higher-resolution scaling

**Изначальные ссылки**
Kosmos-2.5 (взяли у Pix2Struct)
CogAgent
mplug-owl

Говорят что эти подходы не работают хорошо на традиционных VLM бенчмарках

## Mainstream methods

**Direct upsampling**
[[CogVLM]]
[[Qwen-VL]]

**Any resolution**
Sphinx
LLaVA-Next

## Tasks
Исследуют на задачах

**Visual detail analysis**
ROC
REC
???

Resolution-critical OCR tasks
TextVQA

Reasoning MLLM benchmarks
Ferret-Bench

## Any resolution

Берут подход с кропами как в LLaVA-Next
Говорят о возникающих нюансах, из-за того что возникают два различных типа изображения: глобальное и патчи.
Решают проблему с DINOv2 encoder.

# Данные

# Состав

**LLM**
Vicuna

**Visual encoder**
DINO
CLIP

# Архитектура


**Отдельные проджекторы**
*separate MLP projectors for each vision encoder*
Два энкодера CLIP и DINO?
Два различных проджектора для глобальной картинки и патчей?

low-resolution image is encoded via CLIP
high-resolution sub-patches are encoded via DINOv2



# Обучение

**3 этапная тренировка**
coarse to fine в плане разрешения изображений
Дополнительный второй этап - high-resolution dense alignment


# Оценка

