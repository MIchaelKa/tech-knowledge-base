
https://www.notion.so/779c7d49747a44b8a3fd09338bc9c418

Воспроизводимость

# External Links

https://pytorch.org/docs/stable/notes/randomness.html

# Links

[[TNN. Training Speed.]]

[[Statistical Significance]]

[[Курс по ML System Design]]
- Очень важный вопрос для версионирования


# pytorch

pytorch nondeterminism
- torch.backends.cudnn.deterministic
- Deterministic operations are often slower than nondeterministic operations
- https://pytorch.org/docs/stable/notes/randomness.html


pytorch reproducibility dataloader

## benchmark

torch.backends.cudnn.benchmark
- Нужно обязательно ставить `torch.backends.cudnn.benchmark = False` ?

`set_random_seed` в mmdetection
`torch.backends.cudnn.benchmark = False`

`seed_everything` у меня
`torch.backends.cudnn.benchmark = True`

torch.backends.cudnn.benchmark and reproducibility
https://discuss.pytorch.org/t/effect-of-torch-backends-cudnn-deterministic-true/113095