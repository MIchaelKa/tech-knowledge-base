
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

Multi-head Latent Attention (MLA)
- классический Multi-Head Attention (MHA)
	- нарезаются на векторы для отдельных голов внимания
		- нарезаются ?
- сокращает размер необходимого KV-кеша, потому что надо кешировать только низкоразмерные c_t, а не полноразмерные k_t, v_t как раньше
	- как это работает? все еще нужно затем разворачивать c_t в k_t, v_t?
- переиспользование матриц
	- матрицу для k_t (W^uk) можно инкорпорировать внутрь матрицы для получения q_t (W^q)
	- матрицу для v_t (W^uv) внутрь выходной матрицы W^o.
	- как это работает? матрица обучается выполнять сразу две задачи?
- decoupled RoPE
	- позиционные эмбеддинги RoPE несовместимы с низкоранговой компрессией KV

Другие способы оптимизации внимания при ускорении генерации
- Multi-Query Attention (MQA)
	- K и V шарятся между всеми головами внимания (что сильно ускоряет инференс и слегка ухудшает качество)
- Grouped-Query Attention (GQA)
	- Среднее между MHA and MQA


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
- [[LLM Accelerating (LLMA)]]
- Деплоймент фаз _prefilling_ и _decoding_ разделён.

3.5. Suggestions on Hardware Design
- NVLink
- H800
- Infiniband (scale-out) and NVLink (scale-up)


## Обучение


Pre-training
- 14.8T токенов (у предыдущей версии было 8.1T токенов)
- Токенизатор BPE со словарём в 128k.
- Fill-in-Middle (FIM) стратегия с частотой 0.1
- YaRN ([https://arxiv.org/abs/2309.00071](https://arxiv.org/abs/2309.00071 "https://arxiv.org/abs/2309.00071")) для расширения контекста

Post-training
- Состоит из двух частей, Supervised Fine-Tuning (SFT) и RL.
- SFT делался на дополнительных Reasoning и Non-Reasoning данных
- итоговый датасет для instruction-tuning составляет 1.5M примеров
- Resoning
	- постепенно модель выучивала паттерны R1
- рекурсия
	- Данные генерировались внутренней DeepSeek-R1 моделью
- rejection sampling
	- TODO
- GRPO
	- Как и в DeepSeek-V2, авторы использовали Group Relative Policy Optimization (GRPO)
- constitutional AI
	- TODO

RLHF
- PPO vs. GRPO
- rule-based Reward Model (RM) и model-based RM