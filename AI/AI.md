 
# External

Notion
- https://www.notion.so/LLM-36725aa99601409291ae54c42fb0c4b1

Moved
- https://www.notion.so/AI-db462ce714064eb0abf62dd0cdb2d2af

Собираем кейсы AI которые РЕАЛЬНО работают
- https://t.me/kyrillic/1116


# Links

[[LLM]]
[[LLM. Interpretability]]
[[Reasoning]]

[[DL]]
[[VLM]]
[[AI. Corp]]

[[Agents]]
[[MCP]]
[[CG Design and Art]]

# Overview

цена за токен
- https://t.me/ai_newz/3899
- модель более разговорчивая и выдаёт, в среднем, в 2.6x больше токенов на одних и тех же задачах

DLLM
- доменно-специфичные модели (DLLM)
- https://t.me/gonzo_ML/3605

# Benchmarks

Gemini 3.0
- https://t.me/seeallochnaya/3110
- категории бенчмарков
- SimpleQA от OpenAI

SWE-Bench
- https://t.me/seeallochnaya/2830

SWE-ReBench
- https://t.me/seeallochnaya/3091

Agentic benchmarks / Агентские бенчмарки
- https://t.me/seeallochnaya/3110
- Vending Bench
- WeirdML

Спидраним NanoGPT агентами: новый бенчмарк
- https://t.me/rybolos_channel/1524
- NanoGPT speedrun

Пицца аля-semi-supervised
- https://habr.com/ru/companies/ods/articles/422873/
- как обучить модель и получить разметку датасета, разметив всего несколько сэмплов
- 13 сен 2018 в 13:05

# Tools

[[Agents. Coding]]
[[Cursor]]


Canvas
- https://t.me/kyrillic/985
	- Apple Intelligence
	- LLM-интерфейса здорового человека
- https://t.me/seeallochnaya/1841
	- vs Cursor
- https://t.me/ai_newz/3530
- OpenAI
	- https://help.openai.com/en/articles/9930697-what-is-the-canvas-feature-in-chatgpt-and-how-do-i-use-it



NotebookLM
- https://t.me/gonzo_ML/2976

Notebook Agents
- [LinkedIn](https://www.linkedin.com/posts/lvwerra_jupyter-agents-llms-running-data-analysis-activity-7275570666840457218-lDqR?utm_source=share&utm_medium=member_desktop)
- https://huggingface.co/spaces/data-agents/jupyter-agent
- Jupyter Agents

Deep Research
- DeepResearch
	- https://huggingface.co/blog/open-deep-research
	- https://openai.com/index/introducing-deep-research/
- Posts
	- https://t.me/seeallochnaya/2293
	- https://t.me/c3po_notes/263
- Agent

Agents
- GAIA
	- General AI Assistants benchmark
- Humanity's Last Exam
- agentic framework
- smolagents
	- https://github.com/huggingface/smolagents
- CodeAgent
	- Code actions require 30% fewer steps than JSON
- Operator
	- https://openai.com/index/introducing-operator/
	- OpenAI’s Deep Research is probably boosted by the excellent web browser
		- ?


# Image generation and LLM

[[Imagen]]

Gemini 2.0 Flash
- https://t.me/ai_newz/3740
- ControlNet
- inpainting

GPT 4o
- https://t.me/ai_newz/3770
- https://t.me/ai_newz/3785
- https://openai.com/index/introducing-4o-image-generation/


# Arena


https://beta.lmarena.ai/leaderboard

TG
- https://t.me/seeallochnaya/2100
- Style Control
- LMSYS Arena

Elo rating system
- https://en.wikipedia.org/wiki/Elo_rating_system


Chatbot Arena
- https://t.me/datastorieslanguages/419

# ChatML

Chat Markup Language
ChatML

Links
- https://openai.com/index/introducing-chatgpt-and-whisper-apis/
- https://github.com/openai/openai-python/blob/release-v0.28.0/chatml.md
- [medium.com](https://cobusgreyling.medium.com/the-introduction-of-chat-markup-language-chatml-is-important-for-a-number-of-reasons-5061f6fe2a85)

prompt injection attacks
vs.
SQL injection


# Blogs

Andrej Karpathy — “We’re summoning ghosts, not building animals”
- https://www.youtube.com/watch?v=lXUZvyajciY
- https://chatgpt.com/c/68fdfdb5-bc3c-832f-b1d7-e61d445fecf1
- They don't do a lot of thing that you've alluded to earlier
	- Continual learning
- Atari deep RL shift
	- Why it was so important?
	- Attempt to get agents.
	- Misstep that was adopted
- Meta learning
	- pre-training spontaneously meta- learns in-context learning 
- Early agents
	- Web agent w/o LLMs
- Compression
	- LLAMA 3 - 70B - 15T training tokens
	- Massive amounts of compression
	- pre-training - 0.075 bits/token
	- in-context - 2.56M bits/token ??
- Nick Lane
	- https://en.wikipedia.org/wiki/Nick_Lane
- Continual learning
	- No analogue of the sleep process in the LLM
		- Context window -> Memory
		- Distillation phase
	- LoRA
	- Ways to have longer context window
		- Sparse attention scheme
		- DeepSeek v3.2
- Nanochat
- LLM judges for RL
- English
	- people in the room
		- what people in the room felt was about to happen at different breakthrough moments
	- zeitgeist - дух времени
	- I have a hard hat on
	- to steelman the other perspective
	- strip - лишить
	- irrespective - независимо


Richard Sutton – Father of RL thinks LLMs are a dead end
- https://www.youtube.com/watch?v=21EYKqUsPfg
- Our field is subject to bandwagons and fashions, so we loose track of the basic things.

On DeepSeek and Export Controls
- Дарио Амодеи
- https://www.darioamodei.com/post/on-deepseek-and-export-controls
- https://t.me/gonzo_ML/3275
- Claude 3.5 Sonnet is a mid-sized model that cost a few $10M's to train

François Chollet: How We Get To AGI
- https://www.youtube.com/watch?v=5QcCeSsNRks
- scaling law
	- model size and train data size
- skill itself is not intelligence

Jeff Dean & Noam Shazeer – 25 years at Google: from PageRank to AGI
- https://www.youtube.com/watch?v=v0gjI__RyCY
- https://t.me/seeallochnaya/2307
- GDP
- algorithms following hardware
- our systems
	- data flow is expensive
	- arithmetic operations is cheap
- deep learning
	- O^3 - arithmetic
	- O^2 - data copying
- NGram
	- https://chatgpt.com/c/680e96ac-b04c-8000-b614-ec0933b9c9af
- BERT in google search
- длинный контекст
	- [[LLM]]
- shall
	- I guess we shall see

Why I don’t think AGI is right around the corner
- https://www.youtube.com/watch?v=nyvmYnz6EAg
- https://chatgpt.com/c/68990ef0-e5dc-8323-a596-f7e1b56d6375
- Continuous Learning
	- vs. MLSD [[Continuous Learning]]
- Context window
	- Cloude Code compacts the session memory into a summary every 30 minutes
- Computer use
	- As horizon lengths increase rollout have to become longer
- DeepSeek-R1 and GPT-4 -> o1
	- The idea: we should train the model to solve verifiable math and coding problem
- Reasoning
	- ? 


ai-2027
- https://t.me/seeallochnaya/2486
- https://t.me/seeallochnaya/2503
- https://t.me/boris_again/3131
- https://t.me/gonzo_ML/3526
- https://t.me/cryptovalerii/762
- https://t.me/new_yorko_times/359

2027 Intelligence Explosion: Month-by-Month Model — Scott Alexander & Daniel Kokotajlo
- https://www.youtube.com/watch?v=htOvH12T7mU
- algorithmic progress
- progress multiplier
- research multiplier
- component of research
	- research taste
	- quantity of researchers
	- serial speed
		- all humans have the same serial speed
	- compute

Leopold Aschenbrenner - 2027 AGI, China/US Super-Intelligence Race, & The Return of History
- https://www.youtube.com/watch?v=zdbVtZIn9IM
- Leopold Aschenbrenner

Situational Awareness

Джон Шульман
- https://t.me/seeallochnaya/1461
- Наверняка вам попадались выдержки из недавнего интервью Джона Шульмана (кофаундера OpenAI) на Dwarkesh Podcast.
- первый автор в статье про PPO
- скачок InstructGPT -> ChatGPT


How Does Claude 4 Think? – Sholto Douglas & Trenton Bricken
- https://www.youtube.com/watch?v=64lXQP6cs5M
- [[LLM. Interpretability]]
- anthropic
- pareto frontier
- circuits
- sparse autoencoder
- model scratchpad (reasoning?)
- [[Constitutional AI]]
- model self-awareness
- resolution at the top end

