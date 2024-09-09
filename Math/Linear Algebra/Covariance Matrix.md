
Covariance Matrix
Ковариационная матрица

Когда совпадает с корреляционной?
- TBD

semi-definite matrix
- [[Matrix]]

# External Links

[https://ru.wikipedia.org/wiki/Ковариационная_матрица](https://ru.wikipedia.org/wiki/%D0%9A%D0%BE%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F_%D0%BC%D0%B0%D1%82%D1%80%D0%B8%D1%86%D0%B0)

Notebooks
- http://localhost:8888/notebooks/notebooks/covariance_matrix.ipynb
- http://localhost:8888/notebooks/mlcourse.ai-master/jupyter_russian/topic07_unsupervised/lesson7_part1_PCA.ipynb

# Links

[[Singular Value Decomposition (SVD)]]

# Overview
 
Gram matrix
- $X^TX$ - how this matrix is called?
- https://chatgpt.com/c/785002cf-f20e-4efd-9009-b6c9e9d6eebf

Ковариационная матрица — это многомерный аналог дисперсии, для случая, когда у нас не одна случайная величина, а случайный вектор.
- https://temofeev.ru/info/articles/filtr-kalmana-eto-legko/

$X^TX$ - can be seen as a covariance matrix
- Нужно рассмотравить случай когда выполнена нормализация по среднему, и все средние значения у всех признаков равны нулю.

Understanding the Covariance Matrix
- https://datascienceplus.com/understanding-the-covariance-matrix/
- Linear Transformations of the Data Set
	- we can extract the scaling matrix from our covariance matrix
	- This leads to the question of how to decompose the covariance matrix C into a rotation matrix R and a scaling matrix S
- Eigen Decomposition of the Covariance Matrix
	- [[Eigendecomposion]]
	- eigenvectors are unit vectors representing the direction of the largest variance of the data, while the eigenvalues represent the magnitude of this variance in the corresponding directions
		- [[Eigenvalues and Eigenvectors]]

# Direction of the largest variance

Eigenvectors are unit vectors representing the direction of the largest variance.

Почему собственные вектора матрицы $A^TA$ показывают направления максимальной дисперсии в матрице $A$, а собственные значения величину этой дисперсии?
- v1
	- https://chatgpt.com/c/0d972d70-6b4f-4167-9d55-2907b3bb5f88
	- Interpreting Eigenvectors in Terms of Variance
- v2
	- https://chatgpt.com/c/66ddfcaa-12f8-8000-ab30-9e07f3fd2aeb
	- Lagrange Multipliers

Variance of the data vs. Variance of the matrix
- What is variance in the matrix?

Собственные вектора показывают направления вдоль которого матрица максимально скейлит, это можно объяснить, так как отсутствует эффект поворота, который действует на другие направления.

Covariance Matrix
- squared matrix, we can apply it to vectors in the feature space of the data
- почему нам важно то, как скейлит Covariance Matrix?
	- как это связано с Data Matrix?
