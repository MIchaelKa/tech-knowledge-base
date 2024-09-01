
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
- What error metric would you use to evaluate how good a binary classifier is? What if the classes are imbalanced? What if there are more than 2 groups?
	- Accuracy
	- ROC AUC
	- [[Metrics - Offline]]
- What if the classes are imbalanced?
	- Precision / Recall, F-measure
- What if there are more than 2 groups?