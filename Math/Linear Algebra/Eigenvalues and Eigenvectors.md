
MP
https://www.notion.so/Eigenvalues-and-Eigenvectors-3e05164d80754961a06659d8c721ae28

Собственные вектора и собственные значение матрицы

# External Links

https://chatgpt.com/c/0d972d70-6b4f-4167-9d55-2907b3bb5f88

# Links

[[Eigendecomposion]]

[[Harris Corner Detection]]
[[Singular Value Decomposition (SVD)]]

[[Graph]]

# TODO

Сделать демо для понимания собственных значений и векторов матрицы
- [[Harris Corner Detection]]
- [[Singular Value Decomposition (SVD)]]
- [[Covariance Matrix]]

# Direction of the largest variance.

Eigenvectors are unit vectors representing the direction of the largest variance.

Почему собственные вектора матрицы $A^TA$ показывают направления максимальной дисперсии в этой матрице, а собственные значения величину этой дисперсии?
- v1
	- https://chatgpt.com/c/0d972d70-6b4f-4167-9d55-2907b3bb5f88
- Interpreting Eigenvectors in Terms of Variance
- Variance of the data vs. Variance of the matrix
	- What is variance in the matrix?
- v2
	- https://chatgpt.com/c/66ddfcaa-12f8-8000-ab30-9e07f3fd2aeb
- Lagrange Multipliers

Covariance Matrix
- squared matrix, we can apply it to vectors in the feature space of the data.


# Overview

Собственный вектор умноженный на константу, также является собственным вектором с тем же самым собственным значением.
$A(\alpha u) = \alpha(Au) = \alpha(\lambda u) = \lambda(\alpha u)$

In 3D space the eigenvector can represent the axis of rotation

If $A$ is singular, $\lambda=0$
singular == rank deficient ?

Trace
- It can be proved that the trace of a matrix is the sum of its eigenvalues
- https://en.wikipedia.org/wiki/Trace_(linear_algebra)


# Matrix

Eigenvectors of Permutation Matrix
- ?

Eigenvectors of Projection Matrix
- Vectors which already lies in the projection plane
- Vectors which perpendicular to the plane

Матрица поворота
- У матрицы поворота нет собственная векторов?
- Есть но в комплексной плоскости

Матрица растяжения
- У матрицы растяжения все вектора собственные?
- Бесконечное количество векторов.
- Бесконечное количество собственных направлений

Shear matrix
- one eigenvalue
- Всем собственные вектора имеют одно и тоже собственное значение
- И только одно собственное направление

Eigenbasis
- If you transformation matrix has enough eigenvectors (to span the full space) the you can change your coordinate system so that these eigenvectors are your basis vectors
- This is called [[Eigendecomposion]]