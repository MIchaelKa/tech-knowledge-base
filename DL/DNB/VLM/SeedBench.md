
# Внешние ссылки

**Paper**
SEED-Bench: Benchmarking Multimodal LLMs with Generative Comprehension
https://arxiv.org/abs/2307.16125

**GH**
https://github.com/AILab-CVC/SEED-Bench

**SEED-Bench Leaderboard**
https://huggingface.co/spaces/AILab-CVC/SEED-Bench_Leaderboard

PPL evaluation method

# Сводка

**Основные моменты**
Не используют GPT для оценки. Используют GPT-3 как классификатор
CC3M

**Формат** 
Картинки с вопросом и вариантами ответов.

**Размер**
19к примеров

**Метрики**
ACC

# Ссылки

[[InstructBLIP]]
CC3M

# Термины


# Вопросы

PPL
PPL evaluation method

# Обзор

**Структура**
12 категорий
12 evaluation dimension

spatial and temporal understanding capabilities
включают в себя 12 категорий?

## Составление датасета

**Источник**
CC3M

**Извлечение информации**
[[BLIP-2]]
[[Segment Anything]]
[[PaddleOCR]]

[[GRIT]]
в источники?

Использование ChatGPT для генерации вопросов и вариантов ответов

Фильтрация вопросов которые могли быть отвечены без картинки.

Классификация каждой пары картинка-вопрос в одну из 12 категорий.
evaluation dimension

**Соотнесение ответов с доступными вариантами**
Используют GPT-3 как классификатор

# Данные


# Архитектура


# Обучение


# Оценка

