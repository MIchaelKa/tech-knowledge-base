
Статистическая значимость

Cтатистически значимые результаты тренировки NN
- [[How to Train Your ResNet]]

# External Links

https://en.wikipedia.org/wiki/Statistical_significance

Как я перестал беспокоиться и полюбил Пуассон-Bootstrap | Вебинар Валерия Бабушкина | karpov.courses
https://www.youtube.com/watch?v=Zki9VMzxcFU

# Links

[[Raschka. Model Evaluation.]]

# Overview

Statistical Significance vs. statistical power
- Statistical significance is more concerned with Type I errors (false positives), whereas statistical power focuses on Type II errors (false negatives)

statistical power
- https://en.wikipedia.org/wiki/Power_(statistics)
- The higher the statistical power, the less likely you are to make a Type II error

Statistical Significance
- determined by the [[P-value]]

# ML Models

Сравнение ML моделей

*yeah, totally reasonable. just try different combinations and see whether the score improves and if this improvement is statistically significant.*

Статистическая значимость как получить?
- Несколько фолдов
- Несколько запусков не фиксируя сид

1. Смотрим на тест скор
2. Измеряем стандартное отклонение

Если улучшение меньше чем std - это не значимый результат?

Как связано с p-value?
- [[Statistics]]
- Statistical tests

vs. Cross-Validation
- Есть ли смысл использовать эту технику когда есть **кросс-валидация**?
- Единственное преимущество это очень легко имплементировать

