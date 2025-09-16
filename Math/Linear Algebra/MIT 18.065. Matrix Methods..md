
Moved
https://www.notion.so/M-MIT-18-065-Matrix-Methods-in-Data-Analysis-aea7e2d224e842ae9f3a3a6698bd1c67

MIT 18.065 Matrix Methods in Data Analysis, Signal Processing, and Machine Learning
Gilbert Strang


# External Links

Main link
[https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/](https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/)

Syllabus/Readings
[https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/readings/](https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/readings/)

YT
https://www.youtube.com/playlist?list=PLUl4u3cNGP63oMNUHXqIUcrkS2PivhN3k


# Links

[[Fourier Transform]]
[[Singular Value Decomposition (SVD)]]


# Lectures

Lecture 1: The Column Space of A Contains All Vectors Ax

Matrix sampling
[https://youtu.be/YiqIkSHSmyc?t=2148](https://youtu.be/YiqIkSHSmyc?t=2148)

# Book

Linear Algebra and Learning from Data (2019)
https://math.mit.edu/~gs/learningfromdata/

## 1.1 Multiplication Ax Using Columns of A

Ax is the linear combination of columns
Column space of A - all possible combinations of the columns of A
C(A)

b in the column space of A when Ax = b has a solution
- What if it have multiple solutions?
- A is rank deficient

For full rank matrix we want all columns to be independent
It means the only combination of these columns that gives zero vector is $A*0$
The proof?

3 independent columns in R^3 produce an invertible matrix
TODO

Basis for the column space of A
$A = C*R$

C - matrix that contains only independent columns of A
R - row-reduced echelon form of A

Theorem
The number of independent columns equals the number of independent rows.

## 1.3 The four fundamental subspaces


Bx = 0
- однородная система уравнений
- TODO винберг

Counting Law
- With n = 3 unknowns and only r = 1 independent equation, Bx = 0 will have 3 - 1 = 2 independent solutions x1 and x2

Null space
- All solutions to Ax = 0
- [[Matrix Rank]]

## 1.5 Orthogonal Matrices and Subspaces

Orthogonal matrix
- square matrix with orthonormal columns
- The name "orthogonal matrix" should really be "orthonormal matrix"