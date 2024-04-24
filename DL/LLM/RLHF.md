
Reinforcement Learning from Human Feedback


**InstructGPT**
InstructGPT = GPT-3 + RLHF

https://openai.com/research/instruction-following


# HF

https://huggingface.co/blog/rlhf

## Reward model
preference model

Это может быть также языковая модель. Должна выдавать одно число - награду(reward).
Выдавать именно одно число необходимо, чтобы можно было использовать в дальнейшем существующие алгоритмы RL.


**Тренировочный датасет**
Промт
Ответ LM
Ранжирование результатов от различных моделей, которое проводят люди

Можно ли сказать, что reward model - это ранжирующая модель?
При этом она выдает только одно число -  score (которое может использоваться для ранжирования)

## Fine-tune with RL

Proximal Policy Optimization (PPO)

*formulate this fine-tuning task as a RL problem*

## Other

**humans in the loop**
*human workers outside the training loop*
встречали что-то подобное при подготовке к mlsd


# LLaVA

LLaVA-RLHF
https://llava-rlhf.github.io/

Aligning Large Multimodal Models with Factually Augmented RLHF
https://arxiv.org/abs/2309.14525