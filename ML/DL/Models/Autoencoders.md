
Moved
https://www.notion.so/Autoencoders-f1ef3b32ce8244828acca772b7b0765b

# External Links

https://www.jeremyjordan.me/autoencoders/

# Parent

[[Unsupervised Learning (UL)]]
[[Generative Models]]

# Links

[[dlcourse.ai]]

[[Variational Autoencoder (VAE)]]
[[Denoising Autoencoder (DAE)]]

[[PCA]]

# Discussion

Unsupervised Learning (UL) or Self-Supervised Learning (SSL)
- UL
- Autoencoders used in modern SSL frameworks for representation learning.

# Overview

Получение эмбедингов без меток правильных классов.
Обучение без учителя.

Latent Variable 
Скрытая переменная

Steps
- Тренируем сеть выдавать на выход те же данные что были поданы на вход.
- Основная идея в наличие _ботлнек слоя_ в середине сети который не может полностью сохранить исходные данные.
- Encoder - Decoder архитектура.
- То что в середине такой архитектуры(результат работы энкодера) - Latent variable (внутреннее представление)
- Minimize squared error loss


Примеры использования
- Много неразмеченных изображений.
- Сначала тренируем автоэнкодер, а затем поверх эмбедигов тренируем сеть для задачи классификации.
- Как правило притрейн на имейджнет работает лучше.