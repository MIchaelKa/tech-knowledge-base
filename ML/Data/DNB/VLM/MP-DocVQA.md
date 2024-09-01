
Multi-Page DocVQA

**Hierarchical multimodal transformers for Multi-Page DocVQA**
[https://arxiv.org/abs/2212.05935](https://arxiv.org/abs/2212.05935)

GH
https://github.com/rubenpt91/MP-DocVQA-Framework

# Сводка

**Основные моменты**
Extend DocVQA to the multi-page scenario
MP-DocVQA - новый датасет, взяли за снову DocVQA
New hierarchical method, Hi-VT5, based on the T5 architecture

**Метрики**
[[ANLS]]

**Размер**
46, 176 questions
5, 928 multi-page documents
47, 952 page images

**Количество параметров**
316M

**Benchmarks**

**Данные для тренировки**

# Ссылки

[[DocVQA]]

**DocCVQA**
Document Collection Visual Question Answering
20 questions posed over a whole collection

[[Longformer]]
*combination of global and local attention*

## Models

[[LayoutLM]]
TILT

[[T5]]

## e2e

[[Donut]]
Dessurt

*limited input sequence length of these methods*


# Термины

**Структура**
hierarchical structure
hierarchical structure vs. graph structure
tree structure vs. graph structure
[[PDFVQA]]


# Вопросы


# Обзор

**Текстовые модели**
Такие задачи раньше решались в основном только текстовыми моделями. Например бенчмар DocVQA. Либо это были не e2e системы.
**BertQA**
*predicts the start and end indices of the answer span from the given context*

**Входная последовательность и квадратичная сложность Attention**
Обработка документов из нескольких страниц приводит к тому что мы работаем с длинной входной последовательностью. Упираемся в квадратичную сложность Attention.

**Модель**
Hierarchical Visual T5 (Hi-VT5)
extending the input sequence length up to 20480 tokens

**Суммаризация**
encoder summarizes the most relevant information
special `PAGE` tokens
вдохновлено `CLS` токеном в [[BERT]]

**Decoder**
Обрабатывает только PAGE токены

**Страница в ответом**
метод может предоставить страницу где была найдена информация
*additional head to predict the index of the page*


# Создание датасета

За основу взяли Single-DocVQA
Добавили для каждого примера страницы из оригинального документа

# Архитектура

VT5 Encoder

Document Image Transformer (DIT)

OCR tokens
*encoding both text semantics and layout features*
LayoutLM
LATR

# Обучение

TODO

# Оценка

3 различных способа оценки
oracle - подается только одна страница где находится правильный ответ == DocVQA
concat - все страницы подаются вместе
max conf - все страницы подаются поочередно и выбирается ответ по самому высокому confidence

Hi-VT5 показывает высокие метрики в сравнении с конкурентами в ‘concat’ режиме

# Краткий обзор

**Multi-Page DocVQA**

Статья старенькая, интересного немного

**По данным**
За основу взяли обычный DocVQA и расширили его до мульти-страничного сетапа просто добавив страницы из оригинального документа до и после. Дальше  в таком датасете вылезли различные несоответствия и разночтения, некоторые вопросы стали некорректными, они все это почистили и получили новый датасет MP-DocVQA.

**По модели**
Сделали модель Hi-VT5
NO LLM, 316M параметров
OCR токены как в LayoutLM

Из интересного то, как они адаптировали ее к мульти-страничности.
Ключевая проблема в мульти-страничном сетапе - большая длина входной последовательности.
Они это решают так. Есть енкодер, который принимает документ по страницам, и пытается всю инфу со страницы суммаризировать в один PAGE токен (похоже на CLS токена у BERT)
Затем декодер при ответе работает уже только с PAGE токенами.
Вопрос подается с каждой страницей в энкодер  + OCR токены одной страницы + визуальные фичи одной страницы

По результатам из интересного показывают как их модель душит Longformer и LayoutLMv3 на MP-DocVQA