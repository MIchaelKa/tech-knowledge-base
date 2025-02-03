
# External

Notion
- https://www.notion.so/VLM-df9b285137bc4c55b398531cfb4ca701


open_vlm_leaderboard
https://huggingface.co/spaces/opencompass/open_vlm_leaderboard

# TODO

InternLM
CogAgent
MiniGPT-4
ShareGPT
LLaVAR
Flamingo
PaLI
Mini-Gemini
Shikra

**Done**
Ferret
LLaVA

# Термины

OCR tokens

# Идеи

Перекос в VLM моделях в сторону LLM.
Основное число параметров результирующей, модели это параметры LLM.

**RLHF**
Почти никто из существующих VLM не использует RLHF
Только одно упоминание в LLaVA-RLHF?

# vLLM

vLLM
- https://github.com/vllm-project/vllm

vLLM Joins PyTorch Ecosystem
- https://pytorch.org/blog/vllm-joins-pytorch/
- Originally built around the innovative PagedAttention algorithm

PagedAttention
- Efficient Memory Management for Large Language Model Serving with PagedAttention
- https://arxiv.org/abs/2309.06180

Какие есть альтернативы?
- HF
- trtllm

Qwen/Qwen2-VL-7B-Instruct
- Is it quantized?
- Memory
- 16 k image tokens
- Will the context length depends on the size of the image?

Memory
- [[GPU Memory]]
- the rest of the memory reserved for KV Cache is 51.27GiB

Memory usage and concurrency
- https://chatgpt.com/c/679cc428-bccc-8000-840c-453d03b45157
- --max-model-len
- --max_num_seqs
- --max_num_batched_tokens


Tokens
- Context length

concurrency
- batches vs. concurrent requests
	- https://chatgpt.com/c/679cd3f4-c9d4-8000-8227-935935e2ff06
- vllm concurrent requests
- vllm batch requests