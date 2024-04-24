
**VQA: Visual Question Answering**
[https://arxiv.org/abs/1505.00468](https://arxiv.org/abs/1505.00468)

**Links**
[https://visualqa.org/](https://visualqa.org/)

HF
[https://huggingface.co/tasks/visual-question-answering](https://huggingface.co/tasks/visual-question-answering)

PWC
[https://paperswithcode.com/task/visual-question-answering](https://paperswithcode.com/task/visual-question-answering)

PWCv2
[https://paperswithcode.com/dataset/visual-question-answering-v2-0](https://paperswithcode.com/dataset/visual-question-answering-v2-0)

# Сводка

**Размер**
204K images from COCO
614K free-form natural language questions (3 questions per image)
6 million **free-form** (but concise) answers (10 answers per question)

**Основные моменты**
обычно ответ это одно слово

# Ссылки

vqa models

# Обзор

~~Вопрос и картинки с вариантами ответов.~~
Картинки с вопросом и правильным ответом (несколько вариантов правильного ответа от нескольких независимых разметчиков).

# Реализация

**Evaluation**
vqa evaluation

[https://visualqa.org/evaluation.html](https://visualqa.org/evaluation.html)

**Code**
[https://github.com/GT-Vision-Lab/VQA/tree/master](https://github.com/GT-Vision-Lab/VQA/tree/master)

формула для подсчета acc
чтобы было не 0, нужно чтобы ответ модели точно совпал хотябы с одним из вариантов?
насколько это актуально для LLM?

# Блоги и статьи

---

**Introduction to Visual Question Answering: Datasets, Approaches and Evaluation**
[https://tryolabs.com/blog/2018/03/01/introduction-to-visual-question-answering](https://tryolabs.com/blog/2018/03/01/introduction-to-visual-question-answering)

Bayesian approaches

**Accuracy**
while this is a reasonable option for multiple-choice answer systems, when it comes to open-ended answers it tends to be very **penalizing**.

WUPS measure

**Multiple independent ground truth answers**
Instead of relying on semantic measures, we could have **multiple ground truth answers per question**, as we saw for the VQA dataset.

---

**An introduction to Visual Question Answering**

[https://blog.allenai.org/vanilla-vqa-adcaaaa94336](https://blog.allenai.org/vanilla-vqa-adcaaaa94336)

sourced from the MS-COCO dataset
each question is accompanied by 10 answers
99% of the answer containing 3 or fewer words

**When open ended isn’t really that open ended**
reformulate the open ended question answering problem into a K-way multiple choice problem

---