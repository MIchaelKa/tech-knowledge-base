
Линейная Алгебра

# Links

[[Linear Programming]]

# Courses

Савватеев. Линейная Алгебра.

Линейная алгебра и элементы топологии. Курс лекций. Алексей Савватеев
https://www.youtube.com/playlist?list=PLlx2izuC9gji7vdEkiEwIs7IHKY_64Ed2

3Blue1Brown
Essence of linear algebra
https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab

# Books

Кострикин. Введение в алгебру
Винберг.
Гельфанд. Лекции по Линейной Алгебре.
Курош А.Г. Курс высшей алгебры.
Ленг. Алгебра.

Теория чисел
К. Айерленд, М. Роузен, Классическое введение в современную теорию чисел

Abstract Algebra: A First Course
Dan Saracino
https://www.youtube.com/watch?v=pLJSz1KgoOk
https://www.amazon.com/Abstract-Algebra-Course-Dan-Saracino/dp/1577665368


# Strang

Linear Algebra and Learning from Data (2019)
https://math.mit.edu/~gs/learningfromdata/

Introduction to Linear Algebra
https://math.mit.edu/~gs/linearalgebra/ila6/indexila6.html
https://t.me/ai_newz/2377

MIT 18.06
https://web.mit.edu/18.06/www/index.shtml
https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/
https://www.youtube.com/playlist?list=PLE7DDD91010BC51F8

[[MIT 18.065. Matrix Methods.]]

# Discussion

Однозначное соответствие между базисом, матрицей, преобразованием.

# Questions

Do we have a quick test to see if two vectors are linear independent?

Почему определители вводятся только для квадратных матриц?
- Он бы всегда равнялся нулю так как ранг по столбцам равен рангу по строкам, следовательно всегда есть линейно-зависимые столбцы или строки.

Выполняется ли теорема про то что ранг по строкам равен рангу по столбцам для не квадратных матриц?

Если матрица не квадратная значит она может переводить данные из более низкой размерности в более высокую. Значит ли это что данные все же будут лежат на какой то менее многомерной плоскости в этом новом пространстве?

# Data matrix and transformation matrix

The connection between data matrix and transformation matrix.

Матрица может описывать какую либо трансформацию над данными, а может описывать сами данные. В чем большая разница здесь?
https://chatgpt.com/c/68f74bd1-415c-832a-8d33-45fd1fca1041

У нас есть два пространства - строки и столбцы
Сингулярные вектора имеют единичную длину - указывают только направление

**Transformation matrix**
Сингулярные вектора показывают направления максимального растяжения этой матрицей.
А что происходит в направлении собственных векторов? Это направления не является направлением наибольшего растяжения? В направлении собственного вектора происходит только растяжение, без поворота.

**Data matrix** 
Нужно рассмотреть направления максимального воздействия корреляционной матрицы.
Но для корреляционной мы находим не сингулярные, а собственные вектора.
Почему первый сингулярный вектор v​ действительно указывает направление максимальной дисперсии данных?

$Xv$ - проекции всех данных на вектор $v$
Еще один смысл произведения матрицы и вектора?
$(Xv)^2 = v^TX^TXv$ - дисперсия в направлении $v$

Энергия корреляционной матрицы.
Максимум энергии достигается в направлении собственного вектора?
Собственный вектор корреляционной матрицы - сингулярный вектор исходной матрицы. Сингулярный вектор дает направление максимального воздействия, следовательно он также дает максимальное значение для энергии корреляционной.
Справедливо только для симметричных матриц?
TODO: proof (есть по ссылке на chatgpt)

Сингулярные и собственные значения/вектора для симметричных матриц совпадают?
Да, с точностью до знака.

Суммарная дисперсия данных не зависит от выбора базиса
Распределение этой дисперсии по осям зависит от того, какой базис мы выбрали

# Matrix formulas

$(Qx)^T (Qx) = x^TQ^TQx$
$(u+v)^T(u-v) =$ 

Linear algebra formulas
https://chatgpt.com/c/68e18092-d5f8-8328-af1c-4437b8ecb7fb
basic algebraic laws, adapted to matrix multiplication
Matrix algebra identities
Power of a matrix


# Terms

Norm of a matrix
https://chatgpt.com/c/68f7e798-cbe8-8331-91a1-21d22cc0df68