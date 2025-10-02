
vLLM
- https://github.com/vllm-project/vllm

vLLM Joins PyTorch Ecosystem
- https://pytorch.org/blog/vllm-joins-pytorch/
- Originally built around the innovative PagedAttention algorithm

PagedAttention
- Efficient Memory Management for Large Language Model Serving with PagedAttention
- https://arxiv.org/abs/2309.06180

Links
- [[LLM Optimization (LLMA)]]

Какие есть альтернативы?
- HF
- trt-llm

Qwen/Qwen2-VL-7B-Instruct
- Is it quantized?
- Memory
- 16 k image tokens
- Will the context length depends on the size of the image?

Memory
- [[GPU Memory]]
- the rest of the memory reserved for KV Cache is 51.27GiB

ChatGPT
- Memory usage and concurrency
- https://chatgpt.com/c/679cc428-bccc-8000-840c-453d03b45157
- Batch parameters
- mm_counts
	- multi-modal counts
- Merging
	- When concurrency is really happening, you may see logs indicating “Merging X requests into a batch” or “Scheduled tokens for Y sequences.”

Batch parameters 1
- --max-model-len
- --max-num-seqs
- --max-num-batched-tokens

Batch parameters 2
- max_model_len - context length of the model
- max_num_seqs - batch size
- max_num_batched_tokens

Batch parameters formula
- Isn't max_num_batched_tokens = max_num_seqs * max-model-len ?
- max_num_seqs = max_model_len // max_num_batched_tokens

GH
- https://github.com/vllm-project/vllm/issues/2492
- prefill stage

Tokens
- Context length

concurrency
- batches vs. concurrent requests
	- https://chatgpt.com/c/679cd3f4-c9d4-8000-8227-935935e2ff06
- vllm concurrent requests
- vllm batch requests
- openai api batch requests
	- https://chatgpt.com/c/679fa5a8-4668-8000-bbee-06b336d798df
	- There isn’t a magic “batch endpoint” where you can bundle several completely independent requests into a single API call
	- Example for asyncio

Optimization and Tuning
- https://docs.vllm.ai/en/latest/performance/optimization.html
- preemptions
- Terms
	- https://chatgpt.com/c/679ff281-e040-8000-b1c4-3e1e79c657cc
	- ITL
		- ITL (Inter-Token Latency)
	- TTFT
		- TTFT (Time To First Token)