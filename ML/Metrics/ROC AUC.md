
# External Links

[https://coderun.yandex.ru/problem/generalized-auc](https://coderun.yandex.ru/problem/generalized-auc)

[https://en.wikipedia.org/wiki/Receiver_operating_characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)

[https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)

[https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html)

Тетрадь Теком
# Links

[[Учебник по машинному обучению (Яндекс)]]

# AUC

Other AUC metrics

[https://scikit-learn.org/stable/modules/generated/sklearn.metrics.auc.html](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.auc.html)

# Summary

- Work with predicated probabilities (not 1/0)
- Когда строим ROC кривую перебираем порог t

- Depends on TN
- Учитываем ошибки на обоих классах

- Axis
	- y - TPR
		- TP / (TP+FN)
		- Recall
		- Want to be high
	- x - FPR
		- FP / (FP + TN)
		- Want to be low


# Блог Дьяконова

[https://dyakonov.org/2017/07/28/auc-roc-площадь-под-кривой-ошибок/](https://dyakonov.org/2017/07/28/auc-roc-%d0%bf%d0%bb%d0%be%d1%89%d0%b0%d0%b4%d1%8c-%d0%bf%d0%be%d0%b4-%d0%ba%d1%80%d0%b8%d0%b2%d0%be%d0%b9-%d0%be%d1%88%d0%b8%d0%b1%d0%be%d0%ba/)

Важный момент: если у нескольких объектов значения оценок равны, то мы делаем шаг в точку, которая на a блоков выше и b блоков правее, где a – число единиц в группе объектов с одним значением метки, b – число нулей в ней.

ROC AUC равен доле пар объектов которые алгоритм верно упорядочил

ROC AUC для бинарных ответов классификатора
честная точность

AUC ROC можно использовать для оценки качества признаков.


# Comments

[https://www.kaggle.com/inversion/get-started-mar-tabular-playground-competition](https://www.kaggle.com/inversion/get-started-mar-tabular-playground-competition)
- That approach is less useful when the scoring metric is AUC, since any constant prediction will score 0.5.


[https://www.kaggle.com/competitions/llm-detect-ai-generated-text](https://www.kaggle.com/competitions/llm-detect-ai-generated-text)
- Хотя бы логлосс, чтоб откалиброванные вероятности поощрять. Аук-то по сути метрика ранжирования