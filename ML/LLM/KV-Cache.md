

KV Cache
- https://chatgpt.com/c/74067459-18f1-40f8-876e-ef5dfb754d92
- Why we do not use cache for queries?

The KV Cache: Memory Usage in Transformers
- https://www.youtube.com/watch?v=80bIUggRJf4
- Higher pricing for longer context in OpenAI API

Могут ли в процессе работы декодера в режиме инференса изменятся уже предсказанные ранее слова в последовательности?
- Нет
- Поэтому мы и можем использовать KV-cache

Применяем ли мы Masked self-attention во время инференса?
- ДА
- Именно поэтому и возможно использование KV-cache