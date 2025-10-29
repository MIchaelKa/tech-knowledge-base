

# External

https://x.com/karpathy/status/1977755427569111362
https://github.com/karpathy/nanochat

[[Transformer]]


Introducing nanochat: The best ChatGPT that $100 can buy.
- https://github.com/karpathy/nanochat/discussions/1
- Environment
	- uv
	- toml
		- TOML has become the standard for Python project configuration since PEP 621
	- wandb
- Data
	- Common Crawl
	- FineWeb - 15T
- Tokenizer
	- compression ratio, the higher the better?
	- why it's better than GPT-2 if algorithms shouldn't be changed?
- CORE metric
	- https://arxiv.org/abs/2406.11794
- Chinchilla scaling law recommendations
	- https://arxiv.org/abs/2203.15556
- Model
	- ~560M parameters
- Pre-Training
	- ~4e19 FLOPs capability model
	- Validation bpb
		- bits per byte on the validation dataset
		- better measure than just the typical cross-entropy loss
		- tokenizer-invariant
		- TODO
- Midtraining
	- OpenAI Harmony
		- ChatML vs. OpenAI Harmony
		- https://chatgpt.com/c/6901f8b2-25cc-832b-b76e-718d13f909e8
	- This run only takes about 8 minutes
- Supervised Finetuning (SFT)
	- SFT stretches out rows of data and pads them, exactly mimicking the test-time format
	- TODO