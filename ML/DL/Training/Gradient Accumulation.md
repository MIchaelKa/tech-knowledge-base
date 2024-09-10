
Moved
https://www.notion.so/Gradient-Accumulation-2cffd1ab8d4a4b379c07a8873c114183


# Links

[[Distributed Training]]

[[Mixed precision training (MPT)]]

# Overview

Gradient accumulation is a technique that simulates a larger batch size by accumulating gradients from multiple small batches before performing a weight update.

# Comments

>на разрешением 1280х1280 вполне можно тренировать effdet с батчем 16 на V100, если саму сетку собрать самому и сделать её небольшой. см model_config.py . Только очень рекомендую аккумулировать градиенты, чтобы батч стал хотя бы 128, иначе не обучается.

