
# External Links

yandex
решающий пень
https://coderun.yandex.ru/problem/stump

ANN
desicion tree vs. kd-trees in ANN
https://chatgpt.com/c/32dd9abb-507e-4a1a-8382-993eef8e4dec

Decision Tree for kNN problem
Is that how ANN works?


# Summary

Pros
- Interpretability
- Clear BVT
- Features can have any scale.
- More robust to outliers
	- Why?
	- https://chatgpt.com/c/14db660d-e204-48ab-8c28-2dbe8dfa92f9
Cons
- Prone to overfitting, especially if deep.

# Implementation

leetcode
https://leetcode.com/explore/learn/card/decision-tree/

to apply the decision tree, is to traverse the tree from top to down.

interpretability
chain of rules
divide-and-conquer

Base case
- all samples have one label
- max depth
- number of samples less then minimum allowed

Splitting logic
- find the most distinguishable feature
    - try all the features one by one?
- best value to split on
    - use impurity function
- repeat recursively for two subsets

Metrics for splitting
- gini impurity
    - *probability of finding two samples with different labels in a game of random selection with replacement*
    - gini gain
- entropy
    - information gain

Entropy VS. Gini Impurity
- entropy is a bit more expensive to calculate, in terms of computing

Feature Importance
- accumulate the gain for each feature that appears in the decision tree
- should be weighted by the proportion of samples that the decision node helps to distinguish

# cs4780

ML vs. compression algorithms

Approximate NN search
- no backtracking
- labels for final leafs
- Now we don’t need to store the dataset, only a tree.

NP-Hard problem
- We want to get smallest(minimum depth) tree such that it get all(most of) your dataset right
- It's [[NP-Hard]] problem
- But we have good heuristics

BVT
- You need to understand BVT to make Decision Trees good algorithm.
- Плохой алгоритм сам по себе
- Но имеет очень четкое представление BVT, которое можно исправить
- low depth - high bias - boosting
- high depth - high variance - bagging

Разбиение датасета
- Смотри пункт выше (KD Trees - Чем это отличается от Decision Tree?)
- Вместо того чтобы разбивать датасеты на равные части, разбиваем так чтобы части были максимально чистыми (имели одинаковую метку)

Impurity functions
- Для разбиения нам нужны - Impurity functions
- Gini impurity
- Entropy
- [[Entropy]]

Splitting algorithm
- Optimal solution - NP-Hard
- Try every possible split and pick the minimum one.
- D - dimentions
- N - datapoint
- D*(N-1) - splits
- Greedy approach?

ID3-Algorithm

Regression trees
CART