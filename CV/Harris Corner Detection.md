
# External Links

Moved
https://www.notion.so/Harris-Corner-Detection-62895375ab9249d398f74dca4ecad945

[https://docs.opencv.org/3.4/dc/d0d/tutorial_py_features_harris.html](https://docs.opencv.org/3.4/dc/d0d/tutorial_py_features_harris.html)

[https://en.wikipedia.org/wiki/Harris_corner_detector](https://en.wikipedia.org/wiki/Harris_corner_detector)

[https://en.wikipedia.org/wiki/Corner_detection](https://en.wikipedia.org/wiki/Corner_detection)

https://medium.com/@deepanshut041/introduction-to-harris-corner-detector-32a88850b3f6

# Paper

Harris, C., and M. Stephens. “A combined corner and edge detector,” _Proceedings of the 4th Alvey Vision Conference_ (pp. 147–151), 1988.

# Links

[[Optical Flow]]

See Notes

[[Eigenvalues and Eigenvectors]]
[[Covariance Matrix]]
[[Quadratic Form]]
[[Hessian]]
Structure tensor

Structure tensor
- also referred to as the second-moment matrix
- a matrix derived from the gradient of a function
- https://en.wikipedia.org/wiki/Structure_tensor

Good Features to Track
- https://www.notion.so/Harris-Corner-Detection-62895375ab9249d398f74dca4ecad945

SSD - sum of squared differences

Aperture problem

# Overview

Steps
- Finds the difference in intensity for a displacement of (u,v) in all directions.
- Maximize the above function, greater values corresponds to more chance to have a corner
- Applying Taylor Expansion
- Autocorrelation matrix
	- When this matrix maximize point vector?

Taylor Expansion
- Используем аппроксимацию Тейлора чтобы заменить информацию об интенcивности в точке смещения $(x+u, y+v)$ на информацию которая доступна только в текущей точке, но используя первые производные в обоих направлениях.

Autocorrelation matrix
- Structure tensor
- Matrix from of the equation
- In words, we find the covariance of the partial derivative of the image intensity I with respect to the x and y axes.
- [[Covariance Matrix]]

Harris response
- After we got the matrix the algorithm, provides the score function.
- The algorithm does not have to actually compute the eigenvalue decomposition
	- Therefore, the algorithm does not have to actually compute the eigenvalue decomposition of the matrix A and instead it is sufficient to evaluate the determinant and trace of A to find corners, or rather interest points in general.
- Remember that we want the SSD to be large in shifts for all eight directions, or conversely, for the SSD to be small for none of the directions. By solving for the eigenvectors of M, we can obtain the directions for both the largest and smallest increases in SSD.