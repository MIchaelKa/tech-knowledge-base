
https://github.com/kojino/120-Data-Science-Interview-Questions

# Predictive Modeling
(19 questions)

1
- (Given a Dataset) Analyze this dataset and give me a model that can predict this response variable.
	- EDA
	- Start with a simple model
	- Not ML solution

2
- What could be some issues if the distribution of the test data is significantly different than the distribution of the training data?
	- [[Data Distribution Shifts (DDS)]]
	- High training accuracy, low test accuracy.
	- Our training dataset does not represent the general population data
	- Overfitting to train dataset.
	- How to measure generalizability of the algorithm?
	- How to measure generalizability of the dataset?
	- Solutions
		- Cross Validation

3
- What are some ways I can make my model more robust to outliers?
	- Regularization
	- Algorithms
		- Using MAE instead of MSE
		- Using tree based methods instead of regression since it's more robust to outliers
			- [[Decision Trees]]
	- Data
		- Clipping
			- Winsorizing
			- Where you seen this technique recently?
		- Filter outliers out from dataset
			- How to detect them?
			- What if outliers are example of a rare but useful case?
		- Transforming the data (e.g. log)

4
- What are some differences you would expect in a model that minimizes squared error, versus a model that minimizes absolute error? In which cases would each error metric be appropriate?
	- MSE more sensitive to outliers
	- Distribution of the data(noise) assumptions
		- Choosing of loss function corresponds to choosing a distribution for the noise
		- MSE - Normal distribution
		- MAE - Laplace distribution 
		- [[Учебник по машинному обучению (Яндекс)]]
			- 4.1

5
- What error metric would you use to evaluate how good a binary classifier is?
	- Accuracy
	- [[Metrics. Classification.]]
- What if the classes are imbalanced?
	- Precision / Recall, F-measure
	- AP
	- Can we use [[ROC AUC]] ?
- What if there are more than 2 groups?
	- micro and macro averaging

6.
What are various ways to predict a binary response variable? Can you compare two of them and tell me when one would be more appropriate? What’s the difference between these? (SVM, Logistic Regression, Naive Bayes, Decision Tree, etc.)
- [[Comparison of ML Algorithms]]
- Start with a simple algorithm Naive Bayes or RF
- You can start with RF, it works out of the box
- Is data linearly separable?

7.
What is regularization and where might it be helpful?
- [[Regularization]]
- Regularization helps to deal with overfitting and helps us to get a model that generalize well
- Penalize L2 or L1 norm
What is an example of using regularization in a model?
- L1 / L2
- Dropout
- Data augmentation

8.
Why might it be preferable to include fewer predictors over many?
- predictors = feature
- avoiding collinearity between features
	- avoiding correlated feature
	- [[Data Correlation]]
- overfitting
- Part of RF algorithm
- [[Curse of Dimensionality]]
- Computational cost
- Remember competition when you had to predict sentiment analysis of the review
	- Only text features works better out of the box
	- Be lazy

Why might it be preferable to use smaller model
- Avoid overfitting and memorization of the dataset.
- Smaller model can perform better.
- [[Double Descent]]
- [[ResNet]]