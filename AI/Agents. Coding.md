

# Links

[[Coding. Prompts]]
[[Rev. Sessions]]

[[AI]]
[[AI. Corp]]

# External


Vibe coding
- https://en.wikipedia.org/wiki/Vibe_coding
- Vibe coding and tests


Copilot
- https://www.notion.so/GitHub-Copilot-6d39382b23824aa784bf493d84581317

Windsurf

Aider
- https://aider.chat/

Gemini CLI

Antigravity
- https://t.me/new_yorko_times/394


Gemini in Android Studio
- https://developer.android.com/gemini-in-android
- https://developer.android.com/studio/gemini/overview
- https://developer.android.com/studio/gemini/agent-mode


# Benchmarks

[[AI]] - Benchmarks

SWE-Bench
- https://t.me/seeallochnaya/2830

SWE-Bench Verified
- ?

SWE-ReBench
- https://swe-rebench.com/
- https://t.me/seeallochnaya/3091
	- кстати, если агенту / llm в бенчмарке vercel-а дать явную инструкцию прогонять линтер и делать билд проекта, то метрики сильно-сильно растут)
- https://t.me/AIexTime/160


бенчмарк от Vercel
- https://nextjs.org/evals


# Open source

MiniMax M2


# Cursor

External
- https://www.cursor.com/
- https://t.me/c/1508800336/4613
- https://t.me/seeallochnaya/2170
- https://vas3k.blog/blog/2024/

Интересно про то, как построен Курсор
- https://t.me/gonzo_ML/3702
- https://newsletter.pragmaticengineer.com/p/cursor

Cursor 2.0
- https://t.me/ai_newz/4231
- вертикальная интеграция
- https://chatgpt.com/c/6920d5dd-bb14-832a-8800-d342a7935d6a

Improving Cursor’s agent for OpenAI Codex models
- https://cursor.com/blog/codex-model-harness

- can cursor make changes in several files at once?
- YES

Security
- https://www.cursor.com/security#codebase-indexing
- Codebase Indexing


# Codex

Codex
- OpenAI
- https://t.me/seeallochnaya/2576
- https://openai.com/index/introducing-codex/
- cloud-based software engineering agent

Оказалось Codex CLI теперь включён в подписку ChatGPT
- 25.08.2025
- https://t.me/ai_newz/4129
- Уровень Codex как CLI инструмента не дотягивает до Claude Code, но, судя по отзывам, качество работы которую делает Codex — лучше.

GPT-5.1-Codex-Max
- https://t.me/seeallochnaya/3113
- GPT-5.1-Codex -> GPT-5.1-Codex-Max
- Эта модель, получила возможность пользоваться новым инструментом `compaction`, сжимающим контекст и позволяющим продолжать работу дольше.


https://openai.com/codex/
https://developers.openai.com/codex/
https://chatgpt.com/en-ES/features/codex

https://github.com/openai/codex

https://chatgpt.com/codex


codex vs. claude code
codex vs. cursor

Codex + Cursor - what the point?
- https://chatgpt.com/c/6920d2bd-e20c-832a-a51a-51fa84d03a82
- Cursor is not a model, and Codex (or GPT-4.1/GPT-5.1, etc.) is the model.
- Shared agent state across environments

Cloud agent
- github?

Use Codex with the Agents SDK
- https://developers.openai.com/codex/guides/agents-sdk
- Start by turning Codex CLI into a MCP server that the Agents SDK can call.

Ask and Agent modes:
- https://chatgpt.com/c/692724d1-d944-832a-8dd1-4686856ed931


# Claude Code

Links
- https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview
- https://t.me/datastorieslanguages/411
- Default prompt is available.
- Can we find default prompt for Cursor?
- [[Rev. Sessions]]

Claude Code vs. Cursor
- https://chatgpt.com/c/6920d704-fcf4-8325-9ea3-9fd3fa698574

# Documentation

Gemini
- https://gemini.google.com/app/fae2be4d3645cf79

Инструменты для Генерации Диаграмм
- Mermaid или PlantUML

TODO
- Antigravity
- Codex
- Cursor
- Claude Code
- Sourcegraph Cody


# Overview

Смогут ли AI агенты генерировать сразу ассемблер или машинный код, более оптимальный чем получается если генерировать высокоуровневый код и затем пользоваться компилятором

Мне никогда не нравилось на 100% как работает tab в курсоре

Выход GPT-5.1-Codex-Max, хорошее время чтобы начать с Codex?

LLM с помощью специального tool должна сама управлять своим контекстом, не только добавлять туда, но и удалять ненужное, сжимать существующее.

Как долго агент может автономно выполнять задачи, связанные с ML и разработкой
- https://t.me/seeallochnaya/3134


# Scaffolds

Разные скаффолды вокруг моделей: Cursor, Codex CLI, Claude Code.
Как это реализовано, как модели вызывают инструменты, выполняют команды?
Доступно ли Cursor все то что доступно в Codex CLI или Claude Code?
Где описан такой API для определенной модели?
Все работает через [[MCP]]?

ChatGPT
- https://chatgpt.com/c/692f5ace-e884-8331-8b26-f2d3194d36de
- Официальный “tools / function calling” API
- Anthropic Tools
- больше контроль в терминале и легкость кастомизации (ты сам пишешь инструменты)
- API модели (от провайдера)
	- поле `tools` / `functions`
- API инструментов (от клиента/скаффолда)
	- MCP?


- Когда мы используем Официальный “tools / function calling” API, все наши описания инструментов хранятся в контексте у модели?
- все современные LLM имеют мультиканальные входы
- нагрузка — когнитивная, а не токенная.
- модели могут “галлюцинировать инструменты”

- Я правильно понимаю что MCP сервис сам в себе не несет LLM, это сервис который реализует интерфейс, который может быть вызван другой LLM через function calling. Можно ли например написать свой аналог Cursor как MCP сервис?
- API инструментов (от клиента/скаффолда) vs. MCP


# Software 3.0

https://t.me/ai_newz/3971
https://t.me/gonzo_ML/3704

Software 2.0
- https://karpathy.medium.com/software-2-0-a64152b37c35


Andrej Karpathy: Software Is Changing (Again)
- https://www.youtube.com/watch?v=LCEmiRjPEtQ
- Films
	- Rain man
		- Encyclopedic memory of LLMs
	- Memento
	- 50 first dates
		- Context windows is wiped out every time
- Software 1.0
	- Map of github
	- thinking about neural networks as a different kind of classifiers, this framing was a lot more appropriated
- Software 2.0
	- HuggingFace model atlas
- Software 3.0
	- neural networks became programmable
- CAPEX
	- Capital Expenditures
	- Capital expenditures contrast with operating expenses (OPEX)
	- https://chatgpt.com/c/6857e0fe-da5c-8000-a28b-6de194075a69
- AI is the new electricity
	- Andrew Ng
- LLMs have properties of utilities
	- CAPEX to train an LLM
- LLMs have properties of fabs
	- xAI colossus cluster
	- fabless model
- LLMs have properties of OS
	- LLAMA -> Linux
	- LLM -> CPU ?
	- Context window -> RAM
	- text/chat/promts in LLM -> terminal in OS
	- NO GUI invented yet
- Circa 1960s 
- LLM psychology
	- emergent psychology that is human like
	- no equivalent of sleep to consolidate the knowledge into weights
- GUI for LLMs
	- Text is very hard to read, interpret, understand... 
	- Autonomy slider
	- Cursor
	- Perplexity
- Generation - Verification loop
	- We have to keep AI on the leash
	- Better to work on small chunks
- Example with the app publication
	- Code is the easiest part
	- Devops is hard, need to be done manually in the browser
- Build for agents
	- Human - GUI
	- Computer - API
	- Agents (Computer + Human) - ?
	- Docs for LLMs
- Docs for LLMs
	- robots.txt -> llms.txt
	- to pictures
	- use markdown
	- click -> curl
	- MCP