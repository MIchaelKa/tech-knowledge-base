

https://x.com/karpathy/status/1980397031542989305
- whether pixels are better inputs to LLMs than text?
- input can now be processed with bidirectional attention easily and as default, not autoregressive attention - a lot more powerful
	- ?
	- if you want to be really extra you could in principle bidirectional encode the entire context window just to predict the next single token. But doing this means you can’t parallelize training.
- Tokenizers are ugly, separate, not end-to-end stage

https://x.com/vllm_project/status/1980235518706401405

https://github.com/deepseek-ai/DeepSeek-OCR

