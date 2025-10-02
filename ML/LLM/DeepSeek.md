
# External

GH
- https://github.com/deepseek-ai

DeepSeek moment
- https://t.me/gonzo_ML/3239

Собрал свои посты про DeepSeek воедино в англоязычном блоге
- https://t.me/gonzo_ML/3331

# Links

[[LLM]]
[[Transformer]]

# Timeline

DeepSeek-V2
- DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model
- https://arxiv.org/abs/2405.04434

R1-Lite
- https://t.me/ai_newz/3445
- 20.11.2024
- бесплатный конкурент o1, который скоро релизнут в опенсорс
- inference time scaling заставили работать за пределами OpenAI

DeepSeek 2.5
- https://t.me/ai_newz/3529
- 10 Dec 2024

DeepSeek-V3 Technical Report
- https://arxiv.org/abs/2412.19437

DeepSeek-R1
- DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning
- https://arxiv.org/abs/2501.12948
- [[DeepSeek-R1]]


# VLM

[[VLM]]

Notion
- https://www.notion.so/VLM-df9b285137bc4c55b398531cfb4ca701#663f613d0fe64535be871e03b51bde6f

DeepSeek-VL2
- https://github.com/deepseek-ai/DeepSeek-VL2
- https://huggingface.co/deepseek-ai/deepseek-vl2-tiny


# DeepSeek-V2

DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model
https://arxiv.org/abs/2405.04434

Multi-head Latent Attention (MLA)

# DeepSeek-V3

DeepSeek-V3 Technical Report
- https://arxiv.org/abs/2412.19437

DeepSeek-V3 Technical Report
- https://t.me/gonzo_ML/3292

DeepSeek-V3
- transformer layers = 61
- d_h = 7168
- attention heads = ?
- parameters = MoE с 671B параметров всего и 37B активных.



## То что пришло из DeepSeek-V2

[[Multi-Head Latent Attention (MLA)]]

Другие способы оптимизации внимания при ускорении генерации
- [[Attention]]

DeepSeekMoE: Towards Ultimate Expert Specialization in Mixture-of-Experts Language Models
- https://arxiv.org/abs/2401.06066

DeepSeekMoE
- [[Mixture of Experts (MoE)]]
- DeepSeekMoE пытается добиться от экспертов большей специализации.
- Fine-Grained Expert Segmentation
- Shared experts
	- выучивают какое-то общее знание, им токены отправляются всегда
- Routed experts
	- affinity score
	- No FFNN anymore?

## Новое

Multi-Token Prediction (MTP)
- При инференсе MTP модули отбрасываются, но можно и использовать для speculative decoding.

FP8 Training
- В реальности у DeepSeek, конечно, тоже mixed precision — какие-то вещи по-прежнему считаются в более полных форматах, BF16 или даже FP32.
- наконец оно завелось в промышленном режиме для большой модели хорошего качества

Inference optimization
- [[LLM Optimization (LLMA)]]
- Деплоймент фаз prefilling и decoding разделён.

3.5. Suggestions on Hardware Design
- NVLink
- H800
- Infiniband (scale-out) and NVLink (scale-up)


## Обучение


Pre-training
- 14.8T токенов (у предыдущей версии было 8.1T токенов)
- Токенизатор BPE со словарём в 128k.
- Fill-in-Middle (FIM) стратегия с частотой 0.1
- YaRN (https://arxiv.org/abs/2309.00071) для расширения контекста

Post-training
- Состоит из двух частей, Supervised Fine-Tuning (SFT) и RL.
- SFT делался на дополнительных Reasoning и Non-Reasoning данных
- итоговый датасет для instruction-tuning составляет 1.5M примеров
- Resoning (SFT)
	- Reasoning данные фокусировались на математике, программировании, логических задачах.
	- Данные генерировались внутренней DeepSeek-R1 моделью
	- рекурсия
	- постепенно модель выучивала паттерны R1
	- rejection sampling
	- В RL фазе с высокой температурой генерились ответы модели, и постепенно модель выучивала паттерны R1.
		- [[Temperature]]
		- During the RL phase
- RLHF
- [[Constitutional AI]]
	- TODO

RLHF
- PPO vs. [[GRPO]]
- rule-based Reward Model (RM) и model-based RM
- RM были обучены на SFT чекпойнтах DeepSeek-V3.
- Как и в DeepSeek-V2, авторы использовали Group Relative Policy Optimization (GRPO)
- В этих методах я не специалист, интересно, можно было бы заменить на DPO или нет?
- reward hacking

Reward hacking 
- когда модель начинает “обманывать” reward, генерируя тексты с ложными триггерами

DeepSeek-V3 vs. DeepSeek-R1
- https://chatgpt.com/c/68ce7520-4b70-8332-8d71-a390aa5ba2e6

Questions

- What the difference between DeepSeek-V3 and DeepSeek-R1 in terms of reasoning? DeepSeek-V3 was also trained with reasoning SFT data and as it was stated in the paper "models learns to incorporate R1 patterns"
- reasoning tags

- Зачем нужно генерировать два вида SFT сэмплов?
- In order to combine both behaviors in the model.

- Что такое rejection sampling?

- During the RL phase
- Речь идёт именно про обучение экспертной модели (а не про саму V3)

- Что такое preference data?
- В DeepSeek preference data дополнительно включает обоснование (CoT reasoning), почему один ответ лучше другого.
- Как выглядит формат такой preference data? Насколько я понимаю в стандартной reward model на вход подается текст, на выход число - reward. Теперь же модели еще также нужно предоставить CoT reasoning. Как происходит получение reward из такого ответа в свободной форме?
- CoT reasoning включается как часть preference sample, составляется людьми при разметке




