

# Внешние ссылки

**Paper**
Learning Transferable Visual Models From Natural Language Supervision
https://arxiv.org/abs/2103.00020

**Official**
CLIP: ConnectingText and Images
https://openai.com/blog/clip/

**YK**
https://www.youtube.com/watch?v=T9XSU0pKX2E

**open_clip**
https://github.com/mlfoundations/open_clip

# Сводка

**Основные моменты**

**Количество параметров**

**Оценка**


# Ссылки


# Термины


# Вопросы

На каких данных учили CLIP openai?

Какой декодер для текста использовался в оригинальной статье?


# Обзор

Сравнение с [[Image Captioning]]
Predicting text from the images

**Zero-shot classification**
[[Zero-Shot Learning (ZSL)]]
Rephrasing the promt
Model that can predict text → Classifier

Can we do this with Image Captioning models?
Нет, потому что такие модели не могут выдавать метрику близости между картинкой и текстом. Можно использовать для этого отдельную текстовую модель.

---

Q Learning
RL?

**STL10**
STL10 dataset
Few samples for each class

**Linear Probing**
Retrain a new last linear layer for new task/dataset
zero-shot vs. few-shot

**Few-shot**
Точность CLIP сначала уменьшается если примеров меньше для few-show чем 4
[[Few-Shot Learning (FSL)]]

Robustnest for data shift


# Данные


# Архитектура


# Обучение


# Оценка

