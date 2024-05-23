
**Improved Baselines with Visual Instruction Tuning**
Haotian Liu, Chunyuan Li, Yuheng Li, Yong Jae Lee
[https://arxiv.org/abs/2310.03744](https://arxiv.org/abs/2310.03744)


# Сводка

**Основные моменты**
MLP cross-modal connector
Incorporating academic task related data such as VQA
Response formatting prompts

**Количество параметров**
-

**Benchmarks**
Статья ссылается на 12 бенчмарков

**Данные для тренировки**
LCS-558K
VQA datasets
ShareGPT

# Ссылки

**Scaling up the pretraining data**
[[InstructBLIP]]
Qwen-VL

ShareGPT

# Термины

**Visual resampler**
about q-fromer
Почему авторы статьи называют его таким образом?


# Вопросы


# Обзор


# Данные

**VQA data**
Academic-task-oriented VQA data
Предполагается что такие датасеты имеют простую структуру ответа?

Ссылка на статью *Visual instruction tuning with polite flamingo*

*InstructBLIP incorporates academic-task-oriented VQA*
Взяли дополнительные датасеты которые были использованы в [[InstructBLIP]]

Наблюдение: [[LLaVA-1]] плохо работает на academic benchmarks которые обычно требуют односложного ответа

**Format prompting**
Prefix tuning
???

Промт для VQA
*Answer the question using a single word or phrase.*

*inability to balance between short- and long-form VQA*
Наблюдают это у InstructBLIP

В статье предлагается не просто подавать такой промпт при инференсе, но и файнтюнить LLM с таким промптом.

**Pretrain**
LCS-558K
a subset of ∼558K image-text pairs from LAION-CC-SBU with BLIP captions


# Архитектура

**Q-Fromer vs. MLP**
В статье говорится следующее: простая архитектура LLaVA работает лучше чем Q-Fromer в InstructBLIP.
Каким образом это происходит?



# Обучение


# Оценка

