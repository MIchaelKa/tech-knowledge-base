
# Overview

How do you deal with unbalanced binary classification?
- Resampling
	- [[Data Sampling]]
	- Законно ли вообще менять распределение для проблемы дисбаланса классов?
	- https://chatgpt.com/c/9d6d819c-3c9d-420f-a234-31788fd36ed0
	- Oversampling the minority class can lead to overfitting
	- It's crucial to evaluate your model on the original unbalanced test set.
- Class Weights
	- assign different weights to the classes in the loss function
	- [[Focal Loss]]
- [[Anomaly Detection]]
- Synthetic Data