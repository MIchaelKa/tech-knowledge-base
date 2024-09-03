Here are some possible questions that might come up during your interview on the topics of Probability, Algebra, and Statistics:

# Probability

## Basic Probability Concepts

- What is the difference between independent and mutually exclusive events?
- How do you calculate the probability of the union of two events?
- What is conditional probability, and how is it calculated?

## Bayes’ Theorem

[[Bayesian Statistics]]

- Explain Bayes' theorem. Can you provide an example of how it’s used in a real-world application?
- Привести пример байесовского вывода в реальной задаче, в реальном приложении или модели.
	- https://chatgpt.com/c/9c607984-9048-41cc-ab99-a737bf0ac7a4
	- [[Naive Bayes]]
	- Logistic regression example
		- Incorporating prior knowledge about the probability of the event we predicting.

- Пример Байесовской регрессии
	- [[Bayesian Statistics]]
	- Give me an example of using bayesian linear regression in real world task?
	- https://chatgpt.com/c/b0983b9a-4091-41a8-b75e-5b28d2c3c353

- How would you apply Bayes' theorem in a situation where you need to update the probability of a hypothesis given new evidence?
	- Directly?
	- Use previous distribution as a prior.



## Probability Distributions

- What is the difference between a discrete and a continuous probability distribution?
	- PMF vs. PDF

- Can you explain the properties of a normal distribution? What are some examples of data that follow a normal distribution?

- How do you calculate the expected value and variance of a random variable?

- Как биномиальное распределение может использоваться в реальных задачах машинного обучения?
	- [[Binomial Distribution]]
	- https://chatgpt.com/c/0e28bb5d-70b6-4cb1-9d56-e998dff12e6b

- Какой график будет если сложить два равномерных распределения?
	- [[Convolution]]

## Markov Chains

[[Markov Chain]]

- What is a Markov chain, and where might it be applied?
- How do you determine the steady-state probabilities of a Markov chain?

# Algebra

## Linear Algebra Basics

- What are eigenvalues and eigenvectors, and why are they important in machine learning?

- Can you explain the concept of a matrix inversion? In what scenarios might you use matrix inversion?
	- Solve system of linear equations
	- Linear regression closed form solution

- How do you solve a system of linear equations using matrix methods?

## Vector Spaces

- What is a vector space, and what are its key properties?

- Explain the concepts of linear independence and basis vectors.

- How does the dot product and cross product of vectors differ, and when would you use each?

## Matrix Operations

- How do you perform matrix multiplication, and what are the rules for matrix multiplication?
- Explain the concept of matrix rank and its significance in solving linear systems.
- What is a singular value decomposition (SVD), and why is it useful?

# Statistics

## Descriptive Statistics

- What are the differences between mean, median, and mode? When is each one more appropriate to use?
- Explain standard deviation and variance. How do they relate to each other?

## Inferential Statistics

- What is the central limit theorem, and why is it important?
- How would you conduct a hypothesis test? Can you explain the concepts of p-value and significance level?
- What is the difference between Type I and Type II errors in hypothesis testing?

## Regression Analysis

- What is linear regression, and how do you interpret the coefficients of a linear model?
- Explain the concept of multicollinearity in regression. How would you detect and address it?
- What is the difference between homoscedasticity and heteroscedasticity in regression analysis?

## A/B Testing

- How do you design an A/B test? What are the key considerations to ensure valid results?
- Explain how you would determine if the results of an A/B test are statistically significant.
- What is the importance of sample size in A/B testing?

# ML


Почему для бэггинга мы используем глубокие деревья, а для бустинга наоборот?
- [[Boosting and Bagging]]
- [[Decision Trees]] BVT

K-Means. Что делать если не знаем на сколько классов делить выборку?
- K-Means

Why we need data to be independent and identically distributed?
- [[MLE]]
- independent
	- To model joint probability(dataset likelihood) by just multiplying distinct probabilities of datapoints
- identical
	- ?

[[MSE for classification task]]

## Linear models

Links
- [[Linear Regression]]
- [[Regularization]]

Large weight values and overfitting.
- [[Regularization]]

Why feature scaling is important for linear models?
- [[Linear Models]]