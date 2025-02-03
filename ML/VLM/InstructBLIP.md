
InstructBLIP: Towards General-purpose Vision-Language Models with Instruction Tuning
[https://arxiv.org/abs/2305.06500](https://arxiv.org/abs/2305.06500)

# Ссылки

Finetuned language models are zero-shot learners
https://arxiv.org/abs/2109.01652

LAVIS library

# Термины

[[Instruction tuning]]
vision-language instruction tuning

**Query Transformer**
instruction-aware Query Transformer

**Multitask learning**
один из двух подходов к общей задаче
второй это подход который использует BLIP-2 и Flamingo

OCR tokens

# Сводка

**Количество параметров**
BLIP-2

**Benchmarks**

ScienceQA
90.7% accuracy on questions with image contexts

**Datasets**
26 датасетов
LLaVA-Instruct-150K

**Основные моменты**
instruction data
instruction-aware visual feature extraction
balanced sampling strategy

*improved performance by scaling up the pretraining data*
[[LLaVA-1.5]]


# Вопросы

OCR tokens
*Furthermore, for datasets that involve scene texts, we add OCR tokens in the instruction as supplementary information.*

Найти место в статье, где говориться о что-то похожем на Format prompting
Просто обсуждают этот момент?

# Обзор

## Данные

instruction data

Подборка датасетов и категоризация

**11 категорий задач**
типов задач
image captioning
image question answering

**26 датасетов**
26 датасетов преобразованные в instruction tuning формат
13 используются для обучения
13 для валидации

**Instructions**

instruction templates
основа для составления instruction tuning данных

На каких данных учился BLIP-2
Там не было инструкций?

**Валидация**
HatefulMemes. Классификация изображений.

**Два типа отложенных данных для валидации**
1 - датасет который модель не видит во время обучения, но тип задач которой присутствует
2 - датасет который модель не видит во время обучения и тип задач которой также отсутствует

## Сэмплинг

balanced sampling strategy

Примеры сэмплируются с вероятностью равной квадратному корню от размера датасета.
Если ничего не делать то примеры будут сэмплированться с вероятностью равной просто размеру датасета
Таким образом получается что вероятность сэмплирования меньше для датасетов с большим размером, чем была бы?

## Инференс

vocabulary ranking method
ограничивают vocabulary модели списком кандидатов для некоторых датасетов, например ScienceQA



# Архитектура

## Visual feature extraction
instruction-aware visual feature extraction

*textual instruction is given not only to the frozen LLM, but also to the Q-Former*
а как было в BLIP-2?

добавляют текстовые токены на вход Q-former
Как при этом выход Q-former по прежнему состоит из K эмбедингов, где К - количество query vectors.



# Обучение
