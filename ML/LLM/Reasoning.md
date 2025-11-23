
Thinking
рассуждения

# Links

[[AI]]
[[LLM]]

[[DeepSeek-R1]]
[[OpenAI o1]]


# External

Sonnet 3.7
- https://t.me/gonzo_ML/3423
- https://www.anthropic.com/research/visible-extended-thinking

Build Reasoning Models
- HF NLP Course
- https://huggingface.co/learn/llm-course/en/chapter12
- RLHF vs. SFT ?
	- Почему у RLHF получается лучше файтюнить ЛЛМ?
	- Читать статью GPT 3.5 ?
- Proximal Policy Optimization (PPO)
- Direct Preference Optimization (DPO)
- GRPO
	- Group Relative Policy Optimization (GRPO)
	- technique for RLHF
	- GRPO groups similar samples together and compares them as a group.

Speculations on Test-Time Scaling
- https://t.me/seeallochnaya/1986
- спекуляции по поводу того, как работает модель OpenAI o1

# Latent Reasoning


Про непрерывный Test Time Scaling
- https://t.me/buckwheat_thoughts/110
- 12.02.2025
- чекпоинт форварда до генерации через LM Head

Scaling up Test-Time Compute with Latent Reasoning
- https://arxiv.org/abs/2502.05171

[[Coconut]]
[[SIM-CoT]]

LCM
iCoT

# ChatGPT

Reasoning tokens
- https://chatgpt.com/c/680d050a-d4ec-8000-8339-1fb8b9517e76

v1
- https://chatgpt.com/c/680d0be0-cbfc-8000-b521-80168a6c0321

v2
- https://chatgpt.com/c/68bac6d4-11c4-8329-95d2-598947edfb2e
- reasoning в R1 в сущности — это новый слой над RLHF

# CoT


Chain-of-Thought → Tree-of-Thought
- https://t.me/gonzo_ML/1885
- CoT это эмерджентное свойство, начинающее проявляться с размера модели в районе 100B
- CoT-SC

To CoT or not to CoT? Chain-of-thought helps mainly on math and symbolic reasoning
- https://t.me/buckwheat_thoughts/19


Self-Consistency Improves Chain of Thought Reasoning in Language Models
- https://arxiv.org/abs/2203.11171
- CoT-SC


# Overview

Thinking inside the model?

Reasoning = CoT + RL
