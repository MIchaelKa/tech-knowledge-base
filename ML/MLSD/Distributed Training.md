
Distributed Inference
Parallelism

# External Links

https://www.notion.so/8ff74e3c5e1e4a8ab1adbd5ce3b2087a

# Термины

Распределенное обучение
Distributed training

Масштабирование
Scaling

Масштабируемость
Scalability

# Multiple GPUs


[[PyTorch]]

Tutorial
- https://pytorch.org/tutorials/beginner/blitz/data_parallel_tutorial.html

nn.DataParallel
- https://docs.pytorch.org/docs/stable/generated/torch.nn.DataParallel.html
- Implements data parallelism at the module level.
- update is done on the replicas which are destroyed after `forward`.

chatgpt
- https://chatgpt.com/c/68e65ec7-cdec-8329-ba73-f7c82be092f5
- same optimization trajectory as my single-GPU run
- Prefer DistributedDataParallel (DDP) for almost everything
- Python GIL

Questions

- DataParallel vs. DistributedDataParallel
- If you use DistributedDataParallel, you have more control (and more options)
- Prefer DistributedDataParallel (DDP) for almost everything

- Should we increase batch_size x num_of_gpu to get identical training results?
- Not with nn.DataParallel

- Do we need to scale lr when using several GPUs?
- Not with nn.DataParallel

Several sources of divergence
- BatchNorm (or other “running-statistics” layers)
	- SyncBatchNorm
- Check if loss curves, accuracy, **gradient norms**, etc. are similar.