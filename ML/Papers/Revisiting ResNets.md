
# Внешние ссылки

**Paper**
Revisiting ResNets: Improved Training and Scaling Strategies
https://arxiv.org/abs/2103.07579

https://gdude.de/blog/2021-03-15/Revisiting-Resnets

https://opendatascience.slack.com/archives/C04PE5M8V/p1615898403010900

# Ссылки

[[ResNet]]
[[Self-Supervised Learning (SSL)]]
[[Noisy Student]]

# Обзор artgor

https://opendatascience.slack.com/archives/C5VQ222UX/p1615899145006600

Код и чекпойнты на TF
(ссылки из статьи, но что-то там я ничего не нашёл, вторая ссылка вообще не работает):
[https://github.com/tensorflow/models/tree/master/official/vision/beta](https://github.com/tensorflow/models/tree/master/official/vision/beta)
[https://github.com/tensorflow/tpu/tree/master/models/official/resnet/resnet_rs](https://github.com/tensorflow/tpu/tree/master/models/official/resnet/resnet_rs)

Офигенная статья от Google Brain и UC Berkeley с конкретными инженерными идеями по улучшению архитектур и тренировки ResNet. Похоже, что это может быть заменой EffNet-ам, если не считать размера моделей. Авторы решили проанализировать по отдельности что больше влияет на качество моделей: архитектурные изменения или режим тренировки и "scaling strategies" (подробнее об этом дальше). Оказалось, что архитектура играет значительно менее важную роль.

Основных идеи две:
- если моделька может оверфитнуться (например при долгой тренировке), то лучше увеличивать глубину модели. В обратном случае - ширину
- прогрессивное увеличение разрешения картинок при тренировке стоит делать медленее

И ещё одна важная идея (впрочем, об этом говорилось и раньше, но они экспериментально показали): трюки, которые работают на мелких моделях и при короткой тренировке, могут не работать на больших моделях и долгой тренировке. **Так что тюнить все надо на максималках**

Новую архитектуру назвали ResNet-RS was developed. Она в 2.1x - 3.3x раз шустрее, чем EfficientNets на GPU при сравнимом качестве на ImageNet. На semi-supervised learning, ResNet-RS даёт 86.2% top-1 ImageNet. При этом в 4.7x раз шустрее, чем EfficientNet-NoisyStudent. Transfer learning тоже показывает крутые результаты. В итоге авторы предлагают использовать их модельки как новый бейзлайн.

P. S. You can read the english version of my review here:
[https://andlukyane.com/blog/paper-review-resnetsr](https://andlukyane.com/blog/paper-review-resnetsr)