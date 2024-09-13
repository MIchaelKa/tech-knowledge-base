
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
	- Outliers in train data or during inference?
	- Regularization
	- Algorithms
		- Using MAE instead of MSE
		- Using tree based methods instead of regression since it's more robust to outliers
			- [[Decision Trees]]
	- Data
		- Clipping
			- Winsorizing / Winsorization
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

9.
Given training data on tweets and their retweets, how would you predict the number of retweets of a given tweet after 7 days after only observing 2 days worth of data?
- [[Time Series]]
	- Augmentation
	- Cycle
- Regression model

10.
How could you collect and analyze data to use social media to predict the weather?
- geo position
- nlp analysis
- cv analysis of the photos


12.
How would you design the people you may know feature on LinkedIn or Facebook?
- clustering
- graph analysis
	- GNN
- compare embeddings

# Probability

(19 questions)

2.
In any 15-minute interval, there is a 20% probability that you will see at least one shooting star. What is the probability that you see at least one shooting star in the period of an hour?
- https://chatgpt.com/c/ab97c23a-bca6-459b-bbda-460afc9485dc
- Complementary Probability
- [[Poisson Distribution]]

4.
How can you get a fair coin toss if someone hands you a coin that is weighted to come up heads more often than tails?
- Estimate probability
- Then use Binomial trials


6.
Given draws from a normal distribution with known parameters, how can you simulate draws from a uniform distribution?
- [[Cumulative distribution function (CDF)]]
- [[Histogram Equalization]]

8.
You have a group of couples that decide to have children until they have their first girl, after which they stop having children.
- What is the expected gender ratio of the children that are born?
	- 1:1
	- Easy to answer after solving question 2 (below)
- What is the expected number of children each couple will have?
	- [[Geometric PMF]]
	- $E[X] = 1/p = 2$

9.
How many ways can you split 12 people into 3 teams of 4?
- [[Combinatorics]]
- [[Multinomial Distribution]]
- https://chatgpt.com/c/c2064177-af68-4623-80ca-a85f2728724b

10.
Your hash function assigns each object to a number between 1:10, each with equal probability.
- With 10 objects, what is the probability of a hash collision?
	- [[Combinatorics]]
- What is the expected number of hash collisions?
	- [[Total Expectation Theorem]]
		- ?
	- https://chatgpt.com/c/d3ae9e0e-db01-461c-aacd-e6afe223e056
	- [[Binomial Distribution]]
		- cannot use, p is different on each subsequent step
- What is the expected number of hashes that are unused.

# Statistical Inference

6.
How would you run an A/B test for many variants, say 20 or more?
- Effect of multiple comparisons
- Bonferroni Correction