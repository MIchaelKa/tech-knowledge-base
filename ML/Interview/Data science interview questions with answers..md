
https://github.com/iamtodor/data-science-interview-questions-and-answers

1.
Why do you use feature selection?
- [[Feature Selection]]
	- Chi squared test
	- [[Chi-Square]]
- Correlated features can break particular ml models.
	- [[Data Correlation]]
	- [[Linear Regression]]
- Computational resources, faster models
- Less overfitting
- [[Occam's Razor]]


2.
Explain what regularization is and why it is useful.
- Regularization is way to help with overfitting problems
- L1 / L2 - penalize large model weights
- [[Regularization]]

3.
What’s the difference between L1 and L2 regularization?
- Solution uniqueness
	- Manhattan distance vs. Euclidian distance

4.
How would you validate a model you created to generate a predictive model of a quantitative outcome variable using multiple regression?
- Define a suitable regression metric
- [[Учебник по машинному обучению (Яндекс)]]


7.
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