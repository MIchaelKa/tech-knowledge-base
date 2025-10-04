
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

[[Linear Algebra]]

[[Fourier Transform]]
[[Singular Value Decomposition (SVD)]]

[[Matrix]]

# Terms

Nullspace - Ядро


# Lectures

Lecture 1: The Column Space of A Contains All Vectors Ax

Matrix sampling
https://youtu.be/YiqIkSHSmyc?t=2148


# Problems

## PS I.1

4.
https://chatgpt.com/c/68c9cfe4-baa4-8320-a79c-780d41849120
1.3 The four fundamental subspaces
nullspace

14.
https://chatgpt.com/c/68cb0863-35a0-8330-8f3a-fd3171896be7

19
Elimination - row operation
Using this operation we can reduce matrix A to R (except zero rows)

## PS I.2

2.

What can you say about aa^T ?

Symmetric

[[Covariance Matrix]] - ?
No, only one value for the correlation matrix.
Yes
- ~~if we consider that the features has dimension = 1~~
- if we consider that we have only one sample

5.

Start with a matrix B
If we want to take combinations of its rows, we premultiply by A to get AB
If we want to take combinations of its columns, we postmultiply by C to get BC

7.

See problem PS I.2.5

The columns of AB are combinations of columns of A.
Then the column space of AB is contained in the column space of A.

C(AB) <= C(A)


## PS I.3

2.
rank⁡(A^2)<rank⁡(A)
https://chatgpt.com/c/68d45a62-a520-8321-9581-c316518770b0
вектор нельзя возвести в квадрат просто так
they have the same nullity and therefore the same rank (by rank–nullity)

3.
The nullspace of a vertical stack C
https://chatgpt.com/c/68d466a0-9e24-8326-b27a-0a3c88d2f51c
❌

4.
If row space of A = column space of A, and also N(A) = N(AT), is A symmetric?
It can be any full-rank matrix A.
https://chatgpt.com/c/68d46aa8-3510-832d-ae95-129b0d9a7245
✅

5.
Four possibilities
https://chatgpt.com/c/68d470d1-f090-8330-b976-f3113680edb5

6
see chatgpt proof for PS I.3.2

## PS I.4

2.
Formula for the elements of rank 1 matrix
https://chatgpt.com/c/68dedf92-9600-832d-ac81-82794853492e
формула которая ломается, лучше формулы которая не ломается
❌

4.
one-step inverses
https://chatgpt.com/c/68e01f4d-d9a4-8330-b086-439ffacc09e7
left multiplication

7.
https://chatgpt.com/c/68e027fe-b9b4-8333-8a72-ffc62f4e27d4

12.
How to perform elimination for rectangular matrices when m < n ?


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
- What if it have no solutions?
- A is rank deficient. b is not in the column space of A.
- See Problem PS I.3.5

For full rank matrix we want all columns to be independent
It means the only combination of these columns that gives zero vector is $A*0$
The proof? - TODO
PS I.1.4

3 independent columns in R^3 produce an invertible matrix
Ax = b has exactly one solution
x = A^-1 b
TODO?

Basis for the column space of A
$A = C*R$
C - matrix that contains only independent columns of A
R - row-reduced echelon form of A

The first row of A is a combination of rows in R
The first column of A is a combination of columns in C
See problem PS I.1.15

The rows of R are basis for the row space of A
See problem PS I.1.16

The Rank Theorem
The number of independent columns equals the number of independent rows.

Why does R have independent rows?
The weak proof in the book

A = CMR
In this form rows in the R matrix also comes directly form the A
M - mixing matrix

## **1.2** Matrix-Matrix Multiplication AB

Inner products
- rows times columns

Outer products
- columns times rows
- $u v^T$
- rank 1 matrix

AB - sum of rank 1 matrices

We can count the multiplication of number by number
Always there are n^3 multiplications if A and B are nxn or mnp if A is mxn and B is nxp

Factoring A into CR is the reverse of multiplying CR=A

Five important factorization

Spectral Theorem
Symmetric matrix
Orthogonal matrix
SQ = QA comes column by column from Sq = Aq

Every real symmetric matrix S has n orthonormal eigenvectors q1 to qn
Why? The proof?
TODO


## 1.3 The four fundamental subspaces

Bx = 0
- однородная система уравнений
- TODO винберг

Counting Law
- With n = 3 unknowns and only r = 1 independent equation, Bx = 0 will have 3 - 1 = 2 independent solutions x1 and x2

Nullspace
- All solutions to Ax = 0
- [[Matrix Rank]]

Left nullspace
- All solutions to (A^T)x = 0

При построении решений для уравнения Bx=0 для нахождения независимых решений, можно каждый раз занулять очередной линейно-зависимый стоблец в B

Solutions to Bx=0 from the eliminations step

Preference to perpendicular basis vectors

The big picture
- Why Null space connected to the row space not the columns space?
- https://chatgpt.com/c/68d45ebe-b7f8-8321-b7c3-330e352d87c0
- if Ax=0, then x is orthogonal to every row of A

Incidence matrix
- [[Matrix]]
- [[Graph]]
- Detection of the loops in the graph
- rows - edges
- columns - nodes
- dependent rows means the loop
- Flows around loops obey Kirchhoff current law: in=out

The ranks of AB and A+B

Subspaces of a matrix
- Which subspace is b belongs to ?
- https://chatgpt.com/c/68daea4f-b9ac-8332-877f-6351da932fed


## 1.4 Elimination and A = LU

Eliminate x1 from n-1 equations to get a smaller system A2x2=b2 of n-1 size

A = LU is the matrix description of elimination

chatgpt
- https://chatgpt.com/c/68dd8aa2-2b30-832a-a72b-5a1b1bb87563

Why elimination is possible for solving Ax=b?
- We should make this process for b as well
- We can subtract one row from another (or any other elementary row operation) because it’s equivalent to left-multiplying by an invertible matrix.

Am I right that if there are matrices L and U such as A = LU, then matrix A is invertible?
- No, L and U can be singular as well, they are singular if any element on the main diagonal is zero.

Note: the elimination steps requires non-zero pivots.
Good codes will choose the largest number to be the pivot.

Row exchanges
Matrix P


Every invertible nxn matrix A leads to PA = LU
P - permutation matrix


## 1.5 Orthogonal Matrices and Subspaces

Orthogonal matrix
- square matrix with orthonormal columns
- The name "orthogonal matrix" should really be "orthonormal matrix"