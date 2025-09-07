
Reinforcement Learning from Human Feedback

# Overview

ChatGPT
- https://chatgpt.com/c/687cce3c-3388-8000-b347-bcce969b22d0
- Proximal Policy Optimization (PPO)
- Group Relative Policy Optimization (GRPO)
	- [[DeepSeek]]


RLHF (3 phases)
- Supervised Fine-Tuning (SFT)
	- Why Supervised Fine-Tuning (SFT) is the phase of RLHF?
- Reward Model (RM) Training
	- Pairwise Ranking / BERT-like
- Reinforcement Learning (usually PPO)


# OpenAI

Fine-Tuning Language Models from Human Preferences
- https://arxiv.org/abs/1909.08593
- https://openai.com/index/fine-tuning-gpt-2/
- https://github.com/openai/lm-human-preferences

Aligning language models to follow instructions
- https://openai.com/research/instruction-following
- InstructGPT = GPT-3 + RLHF

Training language models to follow instructions with human feedback
- https://arxiv.org/abs/2203.02155
- InstructGPT
- RLHF

InstructGPT vs. ChatGPT
- скачок InstructGPT -> ChatGPT
	- Джон Шульман
	- https://t.me/seeallochnaya/1461

Introducing ChatGPT
- https://openai.com/index/chatgpt/
- November 30, 2022


# HF

Illustrating Reinforcement Learning from Human Feedback (RLHF)
https://huggingface.co/blog/rlhf
Published December 9, 2022

## Reward model

Preference model

Это может быть также языковая модель.
Должна выдавать одно число - награду(reward).
Выдавать именно одно число необходимо, чтобы можно было использовать в дальнейшем существующие алгоритмы RL.

Тренировочный датасет
- Промт
- Ответ LM
- Ранжирование результатов от различных моделей, которое проводят люди.

Ranking vs. score assigning
- Люди лучше делают ранжирование, чем присваивают определенное число (скор)
- The differing values of humans cause these scores to be uncalibrated and noisy.

Methods for ranking the text
- Side by side comparison
- Elo rating system
- Ranking for [[Rev. QNet. Research]]

Можно ли сказать, что reward model - это ранжирующая модель?
При этом она выдает только одно число -  score (которое может использоваться для ранжирования)

Reward model - это аналог value function or critic?

## Fine-tune with RL

Proximal Policy Optimization (PPO)

We need to formulate this fine-tuning task as a RL problem.

Action space
Token vocabulary

Observation space
Distribution of possible input token sequences.
Vocab size ^ Sequence length

Additional Penalty
- https://chatgpt.com/c/68ac7aac-c8d4-832b-a7d7-d675d178af87
- Penalty on the difference between per-token probability distributions from the RL policy and the initial model
- Scaled version of [[KL-Divergence]]
- [[Variational Autoencoder (VAE)]]
- Does vanilla PPO has this penalty?
	- No
- TRPO explicitly uses KL divergence
- PPO-Penalty
- KL divergence is approximated via sampling from both distributions (explained by John Schulman [here](http://joschu.net/blog/kl-approx.html))

## Tools

Repos and tools for RLHF

Large dataset from Anthropic
https://huggingface.co/datasets/Anthropic/hh-rlhf


## Other

humans in the loop
human workers outside the training loop
встречал что-то подобное при подготовке к mlsd


# LLaVA

LLaVA-RLHF
https://llava-rlhf.github.io/

Aligning Large Multimodal Models with Factually Augmented RLHF
https://arxiv.org/abs/2309.14525