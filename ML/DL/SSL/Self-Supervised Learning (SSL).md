
самообучение

self-supervised learning
semi-supervised learning
semi-supervision learning

weak supervision

unsupervised learning?

# External Links

[https://dyakonov.org/2020/06/03/самообучение-self-supervision/](https://dyakonov.org/2020/06/03/%D1%81%D0%B0%D0%BC%D0%BE%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-self-supervision/)

[https://en.wikipedia.org/wiki/Self-supervised_learning](https://en.wikipedia.org/wiki/Self-supervised_learning)

[https://lilianweng.github.io/posts/2019-11-10-self-supervised/](https://lilianweng.github.io/posts/2019-11-10-self-supervised/)

# Links

[[Data]]
[[Labeling]]

[[Contrastive Learning (CL)]]

[[DINO]]
[[DINOv2]]

[[BERT]]
word2vec



# Overview

Self-supervised learning is a method of machine learning that can be regarded as an intermediate form between supervised and unsupervised learning.
- wiki

# Дьяконов

[https://dyakonov.org/2020/06/03/самообучение-self-supervision/](https://dyakonov.org/2020/06/03/%D1%81%D0%B0%D0%BC%D0%BE%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-self-supervision/)

Мы пропустим описание базового вида обучения – с подкреплением
- [[Reinforcement Learning (RL)]]

В последние годы гораздо меньше работ по выбору предварительных задач, поскольку основным направлением в самообучении стало сравнительное обучение [[Contrastive Learning (CL)]]

Mutual information
Взаимная информация
https://en.wikipedia.org/wiki/Mutual_information

NT-Xent
- Такая функция ошибки почти превращается в Triplet Loss, если использовать только 1 негативный пример.

# UL vs. SSL

unsupervised learning vs. self-supervised learning
- [[Unsupervised Learning (UL)]]
- Unlike unsupervised learning, however, learning is not done using inherent data structures.
	- wiki

What is the difference between self-supervised and unsupervised learning?
- https://ai.stackexchange.com/questions/40341/what-is-the-difference-between-self-supervised-and-unsupervised-learning
- In SSL you use your own inputs x (or a modification, e.g. a crop or with data augmentation applied) as the supervision
- UL - no supervision at all