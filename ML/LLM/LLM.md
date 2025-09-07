
# TODO

InternLM
[[Mamba]]

langchain

MMLU
p-tuning

# External


Notion
- https://www.notion.so/LLM-36725aa99601409291ae54c42fb0c4b1

# Links

[[Transformer]]

# Курсы

AndrejKarpathy
- Deep Dive into LLMs like ChatGPT
- https://www.youtube.com/watch?v=7xTGNNLPyMI
- https://t.me/rybolos_channel/1386
- DeepSeek R1

LLM101n
- https://github.com/karpathy/LLM101n
- https://t.me/gonzo_ML/2818

Стенфордский курс по внутреннему устройству LLM
- https://t.me/ai_newz/3930
- CS336, Language Modeling from Scratch

Курс молодого ресёрчера
- https://t.me/buckwheat_thoughts/164
- NLP

HF llm-course
- https://huggingface.co/learn/llm-course/en/chapter1/1

Mastering LLMs: Открытый курс по LLM от практиков
- https://t.me/ai_newz/3087

# Timeline

GPT-2
- https://en.wikipedia.org/wiki/GPT-2
- 14 February 2019

GPT-3
- https://en.wikipedia.org/wiki/GPT-3
- May 29, 2020

GPT-3 исполнилось пять лет
- Хороший обзор с момента появления GPT-3
- https://t.me/ai_newz/3935
- 300B токенов

Language models are few-shot learners
- https://arxiv.org/abs/2005.14165
- GPT-3

Introducing ChatGPT
- https://openai.com/index/chatgpt/
- November 30, 2022

GPT-3.5
- ?

GPT-4
- https://openai.com/index/gpt-4-research/
- https://en.wikipedia.org/wiki/GPT-4
- March 14, 2023
- Rumors claim that GPT-4 has 1.76 trillion parameters

# Blogs

John Schulman's Homepage
http://joschu.net/index.html

# Термины

ICL
in-context learning

# Posts

Как выжать максимум из LLM?
- https://t.me/bogdanisssimo/288

Ссылки
- [[RAG]]
- kNN few-shot
- Chain-of-Thought (CoT)

Ensemble choice shuffle
- Техника которая работает когда нужно выбрать один вариант из нескольких предоставленных.
- MMBench

# Контекст

Короткий комментарий про длинные контексты.
- https://t.me/gonzo_ML/3408
- В общем, по-прежнему не работает тема "запихну всё в один большой промпт". Ну как не работает, технически работает, но продуктово...

Сколько длина контекста у ChatGPT4o?
- Сколько теконов?
- Сколько это в листах А4?
- https://chatgpt.com/c/c529ecbd-0639-4a25-8e7f-766a0bf16976
- 1 токен ≈ 0.75 слова, 10к токенов / 0.75 = 6к слов / 500 слов на страницу =  12 страниц А4

Q
- Как задавать вопросы по книге?
- Насколько важно поместить всю книгу в контекст?

BOTEC

# Overview

Temperature
- https://chatgpt.com/c/679b97ff-9d50-8000-9566-3b83e09f66b1
- [[Temperature]]
- https://platform.openai.com/docs/api-reference/chat/create

Structured Outputs
- https://docs.vllm.ai/en/latest/features/structured_outputs.html
- guided decoding
- развернутые ответ и COT vs. answer in single word
	- [[OpenAI o1]]
- ChatML

Predicted Outputs
- https://t.me/seeallochnaya/1964
- https://platform.openai.com/docs/guides/predicted-outputs
- in canvas
	- predicted output openai is enabled in canvas?

Thinking
- Thinking
- [[OpenAI o1]]
- [[DeepSeek]]


# Training

[[RLHF]]
[[DPO]]

[[SFT]]
Отличается ли чем-то сам процесс тренировки (лосс или что-то еще) на этапе при-трейна и SFT, или мы просто заменяем датасет и также тренируем Next token prediction task?
