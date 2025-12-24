
Дифференциальные уравнения
Диффуры

# External

Notion
- https://www.notion.so/C-Differential-equations-696c3ef9a38141e7ac990677c181a6aa

3Blue1Brown
- https://www.youtube.com/playlist?list=PLZHQObOWTQDNPOjrT6KVlfJuKtYTftqH6

Physics
- Теория Колебаний
- Гармонический осциллятор

Navier–Stokes equations
- https://en.wikipedia.org/wiki/Navier–Stokes_equations
- PDE


DE and NN
How to solve DE using neural nets?


# Terms

Линейные однородные дифференциальные уравнения (ЛОДУ)
Linear homogeneous differential equations

Ordinary differential equation (ODE)
Partial differential equations (PDE)
Stochastic differential equations (SDE)


SDE
- stochastic differential equations
- стохастические дифференциальные уравнения

ODE
- https://en.wikipedia.org/wiki/Ordinary_differential_equation
- The term "ordinary" is used in contrast with partial differential equations (PDEs) which may be with respect to more than one independent variable, and, less commonly, in contrast with stochastic differential equations (SDEs) where the progression is random.

ОДУ
- ru.wikipedia.org/wiki/Обыкновенное_дифференциальное_уравнение
- дифференциальное уравнение для функции от одной переменной (этим оно отличается от уравнения в частных производных, где неизвестная — функция нескольких переменных.)

PDE
- ДУ в частных производных
- УМФ - уравнения математической физики
- ru.wikipedia.org/wiki/Дифференциальное_уравнение_в_частных_производных

Зависимые и независимые переменные
Производные зависимой величины по независимой

Homogenous
Однородный
TODO

Ordinary
Single independent variable
3Blue1Brown ep1

Linear
x(t) appears linearly in the equation
TODO

Решение ДУ - Интеграл

Euler's method


# Vector Field

Visualize DE as a vector field
Slope fields
Phase space

Describes the solutions to the DE

Интегральная кривая
ru.wikipedia.org/wiki/Интегральная_кривая


# Начальные условия

Initial Value Problem

Задача Коши
ru.wikipedia.org/wiki/Задача_Коши

Начальные условия
- ru.wikipedia.org/wiki/Начальные_и_граничные_условия
- Обычно дифференциальное уравнение имеет не одно решение, а целое их семейство. Начальные и граничные условия позволяют выбрать из него одно, соответствующее реальному физическому процессу или явлению.
- Общее решение -> Частное решение

ChatGPT
- https://chatgpt.com/c/694b0ae0-b3b8-832d-8933-8a4ad6298b03

Число начальных условий
- Сколько величин нужно определять для полного описания начальных условия?
- Например почему для уравнений 2го порядке, нужно определить 2 величины?
- Число начальных условий равно порядку дифференциального уравнения
- Каждая операция интегрирования добавляет одну произвольную константу
- Начальные условия **не обязательно** задаются в одной точке и **не обязательно** это именно значения производных.
- Начальные условия vs. Краевые условия
- Задача Коши vs. Краевая задача

# Homogenous DE

Homogenous
- https://www.notion.so/homogenous-7bb61f630731418cabd7a6fabb8348d5
- Однородный

https://en.wikipedia.org/wiki/Homogeneous_differential_equation

Есть также _другой?_ тип однородных уравнений. Хотя возможно существует какая-то связь.

Линейные однородные дифференциальные уравнения (ЛОДУ)
уравнения вида (для второго порядка):
$a(x)y^{''} + b(x)y^{'} + c(x)y = 0$

# Exact equations

дифференциальное уравнение в полных дифференциалах
https://dic.academic.ru/dic.nsf/eng_rus_technic/55857/exact

# Interpretation

Interpretation of differential equations
Search for videos from Khan?
3Blue1Brown


Какой-то физический процесс
- Брошенный вверх или вперед мячик
- Груз на пружинке


# Гармонический осциллятор

FLP T1.21

Зависимые и независимые переменные
Производные зависимой величины по независимой

Численное интегрирование для нахождения решения

Разве время полного колебания при заданной массе и коэффициенте растяжения не определяет амплитуду?
Нет, время полного колебания будет всегда одинаково. В два раза увеличится амплитуда, в два раза увеличиться ускорение, но время останется тем же.
  
Как связано уравнение движения $x = at^2$  и уравнение движения $x = cos(t)$ ?
В случае груза на пружине ускорение это не постоянная, а также функция от времени
Уравнение $x = at^2$ работает для равно-ускоренного движения

Как решить задачу про грузик на пружинке на школьном уровне?

# khan

Links
- https://www.khanacademy.org/math/differential-equations


Euler's method
- A little bit similar to construction of a slope field
- Start with initial condition.
	- Should we always have initial condition when solve DE using Euler's method?
- Do we always need to get the expression for the derivative to be able to make small steps in the direction of the tangent line?
- For multivariable DE we will go in the direction of the gradient?
	- Similar to gradient descent?
	- What does it mean multivariable DE?
- ChatGPT
	- https://chatgpt.com/c/694bb364-740c-8325-87df-c4fd67e9e9ca
	- ты двигаешься по фазовому пространству по стрелкам векторного поля
- Можно ли решать методом Эйлера уравнения более высокого порядка?
	- Только после приведения к системе уравнений первого порядка?


# Applied Stochastic Differential Equations
(BOOK)

## 2. ODE

- second-order differential equation for a forced spring–mass system
	- Гармонический осциллятор
	- second order
	- linear
	- inhomogeneous
		- forcing term w(t)
		- replacing it with a random process leads to a stochastic differential equation
- solution
	- general solution
	- initial conditions
	- general solution +  initial conditions -> particular solution
- ordinary
	- однородные?
- Differential equations of an arbitrary order n can (almost) always be converted into vector differential equations of order one.


## 3.

- Brownian motion
	- Wiener process
- leap of faith solutions to SDEs

# Щуров

Обыкновенные дифференциальные уравнения
- https://ode.mathbook.info/
- 1. Понятие дифференциального уравнения
	- *чаще всего дифференциальные уравнения не решаются явно*
	- Фазовое пространство
		- ru.wikipedia.org/wiki/Фазовое_пространство
		- Динамические системы
		- Расширенное фазовое пространство
			- Множество точек вида (x,t)
		 - Интегральная кривая
			 - График решения
			 - Строится в расширенном фазовом пространстве
		 - Поле направлений
			 - Поле прямых
			 - Slope field?
 - 2. Автономные ДУ
	 - Численное решение ДУ. Метод Эйлера.
		 - Расхождение увеличивается чем дальше мы отдаляемся от начальной точки
	 - Автономные ДУ
		 - Формула Барроу