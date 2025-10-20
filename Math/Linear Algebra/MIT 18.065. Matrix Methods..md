
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
If we want to take combinations of its columns, we postmultiply by C to get BC. 

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

## PS I.5

4.
Lengths and angles are never changed by Q.
Computations with Q are never overflow.

5.
https://chatgpt.com/c/68e1737d-51c8-8329-9f7e-02ff1c6c307e
multiplying orthogonal matrices produces an orthogonal matrix

8.
Haar wavelets
TODO

## PS I.6

7.
The determinant of A equals the product of it's eigenvalues
Can we consider this exercise as a proof of this fact?

10.
Companion matrices

12.
This matrix is singular with rank one. Find three eigenvalues and three eigenvectors.

14.
zero eigenvalue
https://chatgpt.com/c/68e637fc-8bbc-832a-8329-e89b4331c095
eigenspace

17.
If the columns of X (eigenvectors of A) are linearly independent
https://chatgpt.com/c/68e64467-124c-8325-bb89-0645c0edbe1d
❌




# Book

Linear Algebra and Learning from Data (2019)
https://math.mit.edu/~gs/learningfromdata/
https://www.amazon.com/Linear-Algebra-Learning-Gilbert-Strang/dp/0692196382

TODO
- Determinant in more details

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
TODO (Look at matrix inverse in more details)

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
See 1.7


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

Orthogonal vectors
Complex components
[[Complex numbers]]

Hadamard matrix
Hadamard conjecture

For an orthogonal basis subtract away from b it's component in the direction of a.
Gram-Schmidt idea

Orthogonal subspaces
- [[Singular Value Decomposition (SVD)]]
- SVD finds orthonormal bases in row space and column space of A. And those bases are connected by A.

Tall thin Q
- Matrix Q with orthogonal columns
- Tall thin Q with orthonormal columns $Q^TQ = I$
- Only for square matrix Q the true also that $QQ^T = I$
	- Proof below
- if Q multiplies any vector x, the length of x does not change
	- Proof in the book
- if m>n, then m rows cannot be orthogonal in R^n 

Projection matrix
- $P = QQ^T$
- $P^2 = P = P^T$
- Pb is orthogonal projection of b into column space of P
- How related column space of Q and P?
- Projection lies in the heart of [[Least Squares]] (Section 2.2)

Orthogonal matrix
- square matrix with orthonormal columns
- The name "orthogonal matrix" should really be "orthonormal matrix"
- For square matrix $Q^TQ = I$ leads to $QQ^T = I$
	- https://chatgpt.com/c/68e1737d-51c8-8329-9f7e-02ff1c6c307e
	- inverse transformation acts on rows
	- left inverse and right inverse
	- see PS I.5.5
- From above we directly get that $Q^{-1} = Q^T$ 


Orthogonal basis
Formula for coefficients in orthonormal basis


## 1.6 Eigenvalues and Eigenvectors

Most n by n matrices have n independent eigenvectors $x_1$ to $x_n$ with n different eigenvalues $\lambda_1$ to $\lambda_n$. In that case every n-dimensional vector $v$ will be a combination of the eigenvectors.

http://chatgpt.com/c/68e96ff7-b888-8327-be67-95fca092ad74
Is every nxn matrix A with rank has n independent eigenvectors?
No, breaks with repeated eigenvalues.
Is it possible that some matrix has no eigenvectors?
Over the complex numbers C, every matrix has at least one eigenvalue and corresponding eigenvector.

Different eigenvalues and different eigenvectors.
A is nxn matrix.
When rank of the matrix r < n, the matrix still can have more than r different eigenvalues and different eigenvectors.
Can the matrix have more than n different eigenvalues and different eigenvectors?
See Problem PS 1.6.12
https://chatgpt.com/c/68e62bb5-5ad8-8325-a04a-a0d35907c56b
Characteristic polynomial cannot have more then n roots

Orthogonal eigenvectors.
Only true for symmetric matrices?
https://chatgpt.com/c/68e6296b-57d0-832d-bb9f-a04a47dafdac
True for symmetric matrices.
More generally for normal matrices.

Symmetric matrices S=S^T are somehow like real numbers, always have real eigenvalues.
Orthogonal matrices like complex numbers of magnitude one.

Rotation Q has complex eigenvectors
Complex dot product

The matrix A also controls the systems of linear differential equations
Solution vector - TODO

Computing the eigenvalues of A
n-th degree equation which gives you n roots

Shift rule
What happens to eigenvalues and eigenvectors if A is shifted to $A + sI$ ?

Similar matrices
Those matrices which have same eigenvalues
$BAB^{-1}$

The eigenvalues of any triangular matrix are placed on the main diagonal

Diagonalizing a Matrix
If we know the eigenvalues and eigenvectors we can easily compute the matrix A
And also we can easily calculate powers of the matrix A
eigenvectors
left eigenvectors

Markov matrix
Steady state

Eigenvalue multiplicity
https://chatgpt.com/c/68e637fc-8bbc-832a-8329-e89b4331c095
See Problem PS 1.6.14
Is it possible that we have repeated eigenvalues but do not have corresponding linearly independent eigenvalues, only one eigenvector (line of eigenvectors) for example?
Algebraic vs Geometric Multiplicity
GM <= AM
The shortage of eigenvectors when GM <= AM means that A is not diagonalizable


## 1.7 Symmetric Positive Definite Matrices

The eigenvector matrix for S *can be chosen to be* orthogonal(orthonormal) $Q^TQ = I$
Is it possible to choose not orthogonal but linear independent eigenvectors for symmetric matrix S?
https://chatgpt.com/c/68e8ba33-82b4-8325-a8bb-21729a2c98da
Think about eigenspaces.
The proof below for all eigenvectors with different eigenvalues.

Spectral theorem
The usual $A = X \Lambda X^{-1}$ becomes $S = Q \Lambda Q^T$
Every matrix of this form $Q \Lambda Q^T$ is symmetric (transpose to see)

Proof for orthogonal eigenvectors in S

Proof for real eigenvalues in S
https://chatgpt.com/c/68e77e52-d31c-8333-bb01-2295987ddff8
Because up to that point, the entire proof used real-space geometric reasoning — orthogonality of the row space and null space.
Why we multiply by $x^∗$ ?
Are we assuming here complex vectors x?
See Problem 4.

Hermitian transpose
https://www.notion.so/Hermitian-transpose-bf77c908d5ab496e937a9c728dd5d58b

### Positive Definite Matrices

Symmetric + additional requirements
Positive Semidefinite Matrices
[[Matrix]]

Test 1. All positive eigenvalues

If all eigenvalues are real can we say that the matrix is symmetric?

Test 2. The energy test
If every eigenvector have positive energy than all non-zero vectors x have positive energy.
Example of using of the energy test.

Test 3.
$S = A^TA$
A should have independent columns
If A have has dependent columns than S is only positive semidefinite
Is a matrix $A^TA$ always symmetric?
https://chatgpt.com/c/68eaad09-ccc0-8325-8205-d9064aca41d2
See Problem 9

Test 4. Determinant test
Second difference matrix
https://chatgpt.com/c/68e8c7e6-d088-832a-a5cd-d5895a86bea4
Leading principal determinants

Pivots = ratios of determinants
Proof?

Test 5. Pivots

Symmetric matrix elimination
$S = LU$
$S = LDL^T$
$S = A^TA$
$A = \sqrt{D}L^T$
Cholesky factorization


### Minimum problems

The energy is [[Quadratic Form]]
How second derivative works? - TODO

The ellipse
Energy ellipse
Principle axis theorem

why we look on quadratic form only, analyzing f(x,y)?
https://chatgpt.com/c/68eac484-4980-832c-b230-7c546e0c60f1
shift the origin to the stationary point


### Problems

9.
Power of a matrix
https://chatgpt.com/c/68ea2bc2-a740-8332-a8b8-80d3c4d3b796
$A^2$ makes sense only if A is square.

[[Combinatorics]]
$2^n$ possible eigenvalue matrices
Up to permutation there are only n+1 canonical forms

$A^TA$ and $AA^T$
Both are symmetric and positive semidefinite

18
A positive definite matrix cannot have a zero (or even worse, a negative number) on it's main diagonal
Proof?

19
Using shift rule

## 1.8 SVD

[[Singular Value Decomposition (SVD)]]

If A is not square $Ax=\lambda x$ is impossible

A is often matrix of data
A is mxn
m - rows
n - cols

Two sets of singular vectors u's and v's
v - n right singular vectors - orthogonal in R^n - row space
u - m left singular vectors - orthogonal in R^m - col space
$Av=\sigma u$

We can have n singular values (at max?)
r - rank of A
r positive singular values in descending order
last (n-r) v's are in the nullspace of A
last (m-r) u's are in the nullspace of A^T

How many u's we have? - m
How many u's in the column space of A? - r, at most n

$A = U\Sigma V^T$
V - is orthogonal nxn matrix
U - is orthogonal mxm matrix
$\Sigma$ - is mxn matrix

Pieces of the SVD
r pieces of rank 1
See 1.2 - columns by rows matrix multiplication

Reduced form of the SVD
Leave only non zero singular values.
$\Sigma$ - is rxr matrix
V - is nxr matrix
U - is mxr matrix

Eckart-Young
Best k-rank approximation of A

How to find U and V?
We need to look at $AA^T$ and $A^TA$
Then find usual eigenvectors and eigenvalues for them
When I choose the v's, that choice will decide the signs of the u's.
Proof of the SVD

Singular values are always positives?
We can select singular vectors so that it will be true?
https://chatgpt.com/c/68f74451-b2fc-8329-ab4d-45505fc50c85

Diagonalizing

Karhunen-Loeve transform
TODO

### The First Singular Vector

The connection between data matrix and transformation matrix.
[[Linear Algebra]]

But we aim for an independent approach to the SVD!
https://chatgpt.com/c/68f750f8-f9dc-8329-b5d5-5359e885f7b6

Rayleigh quotient
Optimizing the Rayleigh quotient over x gives you the principal directions and eigenvalues of a symmetric matrix.

[[Calculus]]
- The quotient rule
- Lagrange multipliers
- Maximize under the condition


### Submatrices have smaller singular values

The norm of the matrix
[[Linear Algebra]]

Proof
https://chatgpt.com/c/68f8a4fe-a408-832b-9eec-fe133206a3d6
because we are maximizing over a smaller set of vectors
corrected proof

See Problem 10.

### The SVD for  Derivatives and Integrals

Finite differences
DST and DCT
JPEG
Sobel operator
[[Image Gradient]]


## Problems

1/2/3/4
Rayleigh quotient
https://chatgpt.com/c/68f892c2-e910-8330-9d4a-752eb421a44d

10.