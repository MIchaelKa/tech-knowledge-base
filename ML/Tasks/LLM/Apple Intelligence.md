

How to get Apple Intelligence
- https://support.apple.com/en-gb/121115
- Not available in EU on iPhone?
- macOS


Apple Intelligence Foundation Language Models
- External
	- [machinelearning.apple.com](https://machinelearning.apple.com/research/apple-intelligence-foundation-language-models)
	- https://arxiv.org/abs/2407.21075
	- [TG](https://t.me/c/1508800336/4473)
- Links
	- [[Foundation Model]]
	- [[Edge Device Inference]]
	- Transformers on Apple NPU?
- Overview
	- AFM-on-device
		- on device
		- 3B
		- 3B on phone?
	- AFM-server
		- large server-based language
		- params?
	- coding model for XCode
	- Private Cloud Compute
	- Adapters
		- adapters are fine-tuned for specific user needs
	- Evaluation
		- helpfulness and unintended harm
- Architecture
	- [[Transformer]]
	- [[Network Topology]]
	- [[RoPE]]
	- RMSNorm
- Benchmarks
	- MMLU
	- GSM8K
- Data
	- decontamination
		- benchmarks
		- train data?
- Training
	- 3 stages
		- core
		- continued
			- finer data upweights
				- TODO
				- how?
			- favoring a *higher* code and math
			- licensed data
		- context-lengthening
	- AFM-on-device
		- knowledge distillation
		- structural pruning
		- initialize it from a pruned 6.4B model
	- Optimizer
		- RMSProp
	- Frameworks
		- AXLearn
		- [[JAX]]
- Post-Training
	- SFT
	- RLHF
	- Synthetic data
		- Math
		- TODO
- Powering Apple Intelligence features
	- task-specific fine-tuning
	- runtime-swappable adapters
	- [[LoRA]] adapters
		- rank 16
		- for a rank 16 adapter typically require 10s of megabytes
- Optimization
	- quantization
		- less than 4 bit-per-weight
		- LoRA
		- accuracy-recovery adapters
		- application adapters will fine tune from accuracy-recovery adapters
	- Quantization schemes
		- block
			- apply quantization algorithms in a block basis
			- TODO
		- quantization constants (i.e., lookup tables)
	- Mixed-precision quantization
		- Residual connections and layers importance
			- [chatgpt o1](https://chatgpt.com/c/677ecdc4-cfa0-8000-9c05-8502911e620f)
			- [chatgpt 4o](https://chatgpt.com/c/677ece80-beec-8000-b27d-272c16e55e27)
			- If the weights of F(x) are close to zero - low importance
			- The same layers is always unimportant for every input
				- Pruning?
		- 3.7 bpw
	- Talaria
		- interactive model latency and power analysis tool
		- TODO
- Case: summarization
	- Prompt injection
- Evaluation
	- human evaluation results
		- loose to Llama‑3‑8B?
	- decontamination against our evaluation prompts
- Structure
	- application teams


Vocabulary
- perpetuating
	- make (something) continue indefinitely
	- to cause something to continue
	- https://dictionary.cambridge.org/dictionary/english/perpetuate
	- увековечивание
- profanity
	- ненормативная лексика
- contamination
	- загрязнение
- elevate
	- возвысить / поднимать / повышать
- prohibitively
	- запретительно
	- prohibitively expensive - непомерно дорогой
- moderate
	- средний / умеренный / сдержанный
- elicit
	- вызывать / добиваться
	- evoke or draw out (a reaction, answer, or fact) from someone