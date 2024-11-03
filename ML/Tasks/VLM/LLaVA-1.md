
**Visual Instruction Tuning**
Haotian Liu, Chunyuan Li, Qingyang Wu, Yong Jae Lee
[https://arxiv.org/abs/2304.08485](https://arxiv.org/abs/2304.08485)

**LLaVA: Large Language and Vision Assistant**
[https://llava-vl.github.io/](https://llava-vl.github.io/)

HF
[https://huggingface.co/llava-hf](https://huggingface.co/llava-hf)

GH
[https://github.com/haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA)

# Сводка

**Основные моменты**
instruction-tuning -> visual instruction-tuning
instruction-following data
два новых evaluation benchmarks
projection - простой линейный слой

**Количество параметров**
Основная часть параметров в LLM
7B

**Benchmarks**
ScienceQA
LLaVA-Bench

**Данные для тренировки**
CC-595K
LLaVA-Instruct-150K

# Ссылки

Flamingo
GLIP
Git
BLIP-2
OPT
LangChain

MM-CoT
multimodal chain-of-thought

Instruct pix2pix: Learning to follow image editing instructions

CVinW

Data centric experiments

# Термины


# Вопросы

Почему не использовали GPT-4V?
Эта модель уже была доступна на момент выхода статьи?


# Обзор

**Instruction tuning**
[[Instruction tuning]]
Ссылки на статьи по instruction-tuning

teacher-student distillation
???

Flamingo
*Flamingo can be viewed as the GPT-3 moment in the multimodal domain*

vs. visual prompt tuning

**visual instruction-tuning**
первая попытка расширить **instruction-tuning** и включить в него визуальную составляющую.



# Данные

**Pretrain**
CC-595K
Total: 595K

**Finetune**
LLaVA-Instruct-150K
Total: 150K

## LLaVA-Instruct-150K

**Источник**
COCO images

**Instruction-following data**
данные для обучения в формате инструкций
в этой статье получаем мульти-модальные данные в этом формате

Датасеты c парами изображение-текст
CC
LAION

Расширение пар изображение-текст до соответсвующей **instruction-following** версии.

**3 типа instruction-following data**
Conversation
Detailed description
Complex reasoning

conversation is multi-turn

**Использование GPT-4**
Использование **language-only** GPT-4 для генерации **instruction-following data**

seed examples in in-context-learning
несколько примеров которые были сделаны вручную для in-context-learning GPT-4

При составлении Также используется информации о bbox объектов

# Архитектура


Простой линейный слой для перевода эмбеддингов после визуального энкодера в пространство эмбеддингов LLM

VQ для LLaVA
Есть ли эксперименты по использованию VQ ?
Изначально это хорошо работало в диффузионных моделях, перенесется ли это на задачи визуального ассистента?
[[Diffusion Models]]

## Состав

**Vision encoder**
CLIP visual encoder ViT-L/14

*grid features before and after the last Transformer layer*

**LLM**
Vicuna


# Обучение

Случайно переставляют местами картинку и текст на входе в LLM

**Conversation turns**
multi-turn conversation data
Вопросы и ответы в режиме диалога, в первом запросе идет картинка (всегда в первом?)

Только для категории - Conversation

## **2 этапа обучения**

**Этап 1**
vision-language alignment pretraining stage

CC-595K
filter CC3M to 595K image-text pairs
naive expansion method (без использования GPT-4)

И визуальных энкодер и LLM заморожены на этом этапе.
Тренируется только projection слой

**Этап 2**
visual instruction tuning stage

Размораживают LLM
LLaVA-Instruct-150K
Используют для тренировки ScienceQA?

# Оценка

**Использование GPT-4 для оценки**
Также используется только языковая GPT-4
Создание троек: картинка + GT текстовое описание + вопрос к картинке
Текстовое описание используется для входных данных к GPT-4
Картинка используется для входных данных для LLAVA

Upper-bound
результат полученный с помощью  GPT-4 и GT текстового описания

Судья
Снова испльзуется GPT-4
Оценки по шкале 1-10

**2 бенчмарка**

**LLaVA-Bench (COCO)**
30 images from COCO-Val-2014
90 questions (для каждой картинки?)

**LLaVA-Bench (In-the-Wild)**
24 images with 60 questions in total
designed to be challenging

**ScienceQA**
Кто именно был SOTA на ScienceQA в то время?
MM-CoT