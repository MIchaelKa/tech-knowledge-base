
MP
https://www.notion.so/Eigenvalues-and-Eigenvectors-3e05164d80754961a06659d8c721ae28

Собственные вектора и собственные значение матрицы

# External Links

https://chatgpt.com/c/0d972d70-6b4f-4167-9d55-2907b3bb5f88

3Blue1Brown
Eigenvectors and eigenvalues | Chapter 14, Essence of linear algebra
https://www.youtube.com/watch?v=PFDu9oVAE-g

Савватеев

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
- Copilot

Harris
- Реализовать Harris самому?
- Write sample app where you can move the window and look for computed matrix and look for its eigenvalues.

# Discussion

Собственные вектора - это направления, вдоль которых данная матрица искажает (растягивает, скейлит) вектора на которые она действует сильнее всего.

Смотреть логику по интерпретации собственных значений в матрице [[Harris Corner Detection]]

# Overview

Собственный вектор умноженный на константу, также является собственным вектором с тем же самым собственным значением.
$A(\alpha u) = \alpha(Au) = \alpha(\lambda u) = \lambda(\alpha u)$

In 3D space the eigenvector of rotation matrix represents the axis of rotation
- See Матрица поворота

Нулевые собственные значения
- If $A$ is singular, $\lambda=0$
	- singular == rank deficient ?
- нулевое собственное значение говорит о том что матрица не полного ранга

Trace
- It can be proved that the trace of a matrix is the sum of its eigenvalues
- https://en.wikipedia.org/wiki/Trace_(linear_algebra)

Calculation
- $(A-\lambda I) v = 0$
	- we want to find non zero $v$
- $det(A-\lambda I) = 0$


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
- Одно собственное значение

Shear matrix
- one eigenvalue
- Всем собственные вектора имеют одно и тоже собственное значение
- И только одно собственное направление

Eigenbasis
- If you transformation matrix has enough eigenvectors (to span the full space) the you can change your coordinate system so that these eigenvectors are your basis vectors
- This is called [[Eigendecomposion]]
- В этом новом базисе изначальная матрица это диагональная матрица, с собственными значениями на диагонали.
	- $A = PDP^{-1}$
	- $D = PAP^{-1}$