
Pattern Recognition and Machine Learning
Christopher M. Bishop

bishop pattern recognition and machine learning

# Timeline

- ???
- 03.12.2023
- 30.08.2024

# Links

gamma function

# Terms

independent and identically distributed - i.i.d.
univariate - одномерный

# 1. Intro


Large weight values and overfitting

Model complexity
- *number of parameters is not necessarily the most appropriate measure of model complexity*


## Probability Theory

[[Probability Theory]]

[[Joint Probability]]

Sum rule
- [[Sum Rule]]
- Marginal probability
- Summing up of joint probabilities

Product rule
- joint = conditional x marginal

Applying [[Bayes’ Theorem]] to model weights
How we certain about our hypothesis?

Likelihood function in Bayesian and frequentist paradigms
- frequentist
	- w is a parameter
	- [[MLE]]
	- bootstrap
- Bayesian
	- w is r.v.
	- inclusion of prior knowl- edge

Practical use of Bayesian techniques
sampling methods, such as Markov chain Monte Carlo

## The Gaussian distribution
1.2.4

[[Normal Distribution]]

Estimating parameters
- Estimating gaussian distribution parameters by observed datapoints(dataset) drawn from that distribution
- Определение параметров нормального распределения из данных
- [[MLE]]
- maximum likelihood solution - sample mean and sample variance
- difference from [[Linear Regression]] ?

## Curve fitting re-visited
1.2.5

precision parameter
- reciprocal of the variance

Gaussian noise
- assumption of a Gaussian noise distribution
- gaussian distribution for the model predictions
	- Our model predicts the mean of the gaussian distribution
	- We can express our uncertainty over the value of the target variable using a probability distribution.
- Gaussian noise for datasets == Gaussian distribution for model predictions
	- [[Linear Regression]]
	- https://chatgpt.com/c/af97f096-858a-4fb5-af65-751f337a2ecb
- What is variance?
	- How to get confidence for the regression task?
	- UDL 5.3.3
	- MLE for precision parameter
		- formula with dataset variance using model predictions as a mean

MLE + Gaussian noise
- sum-of-squares error function
- [[Least Squares]] loss function as a result of choice of gaussian distribution for the model predictions
- probability distribution over t, rather than simply a point estimate

Prior distribution over w
- MAP
 - maximum posterior