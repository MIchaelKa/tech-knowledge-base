
**LayoutLM: Pre-training of Text and Layout for Document Image Understanding**
[https://arxiv.org/abs/1912.13318](https://arxiv.org/abs/1912.13318)

YT
https://www.youtube.com/watch?v=ewyDVIdKXm0

HF
[https://huggingface.co/docs/transformers/model_doc/layoutlm](https://huggingface.co/docs/transformers/model_doc/layoutlm)

---

**LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking**
[https://arxiv.org/abs/2204.08387](https://arxiv.org/abs/2204.08387)

# Ссылки

[[BERT]]

[[Kosmos]]
v2?

# Обзор


[[MP-DocVQA]]
*all the previous methods utilize the text recognized with an off-the-shelf OCR*
(про все версии v1-v3)

*importance of layout information when working with Transformers*

---

**Входная последовательность**
Текстовый эмбединг плюс позиционные эмбединги для каждой из 4 координат.
Позиционные эмбединги похожи на те что использовались в Kosmos-2?
Позиционные эмбединги не маскируется во время Language Modelling при-трейна

---
