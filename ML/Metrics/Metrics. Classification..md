
https://www.notion.so/Offline-Metrics-fe8a1130741c42fe917bccf94663e854

Confusion Matrix

Accuracy
- Доля правильных ответов
- Accuracy is a great measure but only when you have balanced datasets where values of FP and FN are almost same.

Precision
- TP / (TP + FP)
- TP + FP - Total positive PRED
- Точность
- ~ FP

FPR
- FP / (FP + TN)
- FP + TN - Total negative GT
- FPR = 1 - TNR
- Interpretation
	- probability of false alarm

FNR
- ?

TPR
- TP / (TP+FN)
- TP + FN - Total positive GT
- Recall
- Sensitivity
- Полнота

TNR
- TN / (TN+FP)
- Specificity


F1 score
- https://en.wikipedia.org/wiki/F-score
- Среднее гармоническое
	- Почему именно среднее гармоническое?
	- [https://ru.wikipedia.org/wiki/Среднее_геометрическое](https://ru.wikipedia.org/wiki/%D0%A1%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%B5_%D0%B3%D0%B5%D0%BE%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5)


[[Average Precision (AP)]]

[[ROC AUC]]



# Class imbalance

## Links

Дисбаланс классов
ROC AUC vs. Average Precision (AP)

How to Use ROC Curves and Precision-Recall Curves for Classification in Python
https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-classification-in-python/

Чувствительность к соотношению классов
- Соколов
	- https://github.com/esokolov/ml-course-hse/blob/master/2020-fall/lecture-notes/lecture04-linclass.pdf
- Дьяконов
	- Таким образом, этот пример не показывает неприменимость AUC ROC в задачах с дисбалансом классов, а лишь в задачах поиска!

В случае ассиметрии классов, можно использовать метрики, которые не учитывают TN и ориентируются на TP
- [[Учебник по машинному обучению (Яндекс)]]

ROC AUC vs. Average Precision (AP)
- ROC AUC vs. Average Precision (AP) when you have class imbalanced dataset
- https://stats.stackexchange.com/questions/7207/roc-vs-precision-and-recall-curves
- https://chatgpt.com/c/74d91f6a-3ec2-40fc-8529-3d124e0f7750

## Overview

Average Precision (AP)
- Как эта метрика помогает с несбалансированным датасетом?
- focuses on the performance of the positive (minority) class

Почему ROC AUC работает плохо?
- Плохо работает если очень мало объектов одного из классов.
- Площадь будет близка к единице.
- Высокий Recall даже при маленьком трешхолде?
- False Positive Rate (FPR) might be small for most thresholds

Зачем выбирать ROC AUC вместо AP?
- AP не обладает недостатком от дисбаланса классов
- Baseline probabilities
- Когда хотим учитывать ошибки на обоих классах
- When you also care about the negative class
- Если важен правильный порядок на объектах

Для ROC AUC также имеет большое значение какой класс мы берем за 1, а какой класс мы берем за 0?
