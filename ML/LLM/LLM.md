
# TODO

InternLM
[[Mamba]]

langchain

MMLU
p-tuning

# External


Notion
- https://www.notion.so/LLM-36725aa99601409291ae54c42fb0c4b1


John Schulman's Homepage
http://joschu.net/index.html

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

# Термины

ICL
in-context learning

Perplexity

# Training

[[RLHF]]
[[DPO]]
[[SFT]]

[[Nanochat]]

The Smol Training Playbook
- https://huggingface.co/spaces/HuggingFaceTB/smol-training-playbook
- https://x.com/eliebakouch/status/1983930328751153159


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


# Perplexity

PPL

https://en.wikipedia.org/wiki/Perplexity

HF
- https://huggingface.co/docs/transformers/perplexity
- Perplexity (PPL) is one of the most common metrics for evaluating language models.
- The larger the perplexity, the less likely it is that an observer can guess the value which will be drawn from the distribution.

Evaluation Metrics for Language Modeling
- https://thegradient.pub/understanding-evaluation-metrics-for-language-models/

chatgpt
- https://chatgpt.com/c/68e24b89-8d58-832c-8af0-d777dafa89a6
- Perplexity - Экспонента кросс-энтропии

Perplexity vs. Entropy

Интерпретация Perplexity
- Perplexity – “эффективное количество возможных слов”, которые модель считает правдоподобными на каждом шаге.
- Exponentiation “убирает лог”, возвращая нас в пространство вероятностей.


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

# Blogs


HC2025-K1: Predictions for the Next Phase of AI
- https://www.youtube.com/watch?v=v0beJQZQIGA
- Кстати, у Ноама был кейноут доклад на свежей HotChips
	- https://t.me/gonzo_ML/4071
- Noam Shazeer
- What LLM wants
	- Logarithmic gains from
		- Computations
	- things that made deep learning take off
- 2015 - 2025
	- Perplexity
	- [[LLM]]
- 2016 - Sparsely-gated [[Mixture of Experts (MoE)]]
	- more parameters
	- not more computations
	- you need method of sparsity that compatible with fast matrix computation
	- block sparsity
	- MatMul speed
- 2017 - Transformer
- 2018
	- Data parallelism
		- SPMD
		- en.wikipedia.org/wiki/Single_program,_multiple_data
		- model size limitation - should fit on one chip
	- Model parallelism
		- Mesh-TensorFlow
		- Use JAX now
	- Parameters to training token ratio
		- 1:1
		- Chinchilla - 1:20 ?
	- 3D mesh of processors
- What LLM wants from hardware
	- FLOPs
	- Memory capacity
	- Memory bandwidth

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

# Papers

Inference-Time Scaling for Generalist Reward Modeling
- https://arxiv.org/abs/2504.02495
- https://t.me/seeallochnaya/2824
- [[DeepSeek]]
- RLVR
- Generalist reward model (GRM)
- DeepSeek для себя решают следующее: они будут учить модель, которая получает на вход промпт, от одного до нескольких ответов на него, генерирует критику для каждого из ответов, и в конце выдаёт оценки всех ответов по шкале от 1 до 10.
- Критики будут опираться на принципы, которые специфичны для каждого промпта и генерируются самой моделью.
- Принципы — это описание человеческим языком того, что может служить критерием хорошего и плохого ответа на данный вопрос.
- Rejective Fine-Tuning (RFT)
- Gemma-2-27B
- Очень часто у LLM, которые занимают оценкой ответов, есть position bias — когда первый (или второй) ответ априори оценивается моделью лучше