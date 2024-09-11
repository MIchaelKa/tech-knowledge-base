
Moved
https://www.notion.so/Zero-Shot-Learning-ZSL-3a2bb7e2b1594080a6e02c37b54f981b

Zero-Shot Learning


# External Links

[https://en.wikipedia.org/wiki/Zero-shot_learning](https://en.wikipedia.org/wiki/Zero-shot_learning)

[https://www.quora.com/What-is-zero-shot-learning](https://www.quora.com/What-is-zero-shot-learning)

[https://towardsdatascience.com/xlm-enhancing-bert-for-cross-lingual-language-model-5aeed9e6f14b](https://towardsdatascience.com/xlm-enhancing-bert-for-cross-lingual-language-model-5aeed9e6f14b)


# Links



# Discussion

CLIP vs. Image Captioning
- [[Image Captioning]]
- [[CLIP]]
- В Image Captioning модели нельзя было загрузить свой текст, только картинку.
- Сответственно нельзя делать Zero-Shot

Каждой картинке соответсвует не просто метка класса, а более подробное текстовое описание. Таким образом эта задача не только из области CV но и NLP

Эмбеддинги
- CV модель должна выдавать на выходе текстовый эмбеддинг?
- Текстовые и визуальные эмбеддинги должны находится в одном пространстве.

# Overview


Zero-Shot Learning - Dr. Timothy Hospedales
- https://www.youtube.com/watch?v=jBnCcr-3bXc&t=626s
- Key
	- Key is to embed categories labels as vectors
	- Then learn some mapping between image features and class vectors
- Domain shift
- Manifold learning (Manifold label propagation)