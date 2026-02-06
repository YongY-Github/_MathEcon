# Multivariate Calculus

## Functions of Several Variables and Partial Derivatives

While there are some subtleties involved in moving from univariate to multivariate calculus, much of the intuition carries over.

Consider a function

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n).
:::

The partial derivative of $y$ with respect to its $i$-th argument $x_i$ is defined as

$$
\frac{\partial y}{\partial x_i} 
= \lim_{\Delta x_i \to 0} 
\frac{f(x_1, \ldots, x_i + \Delta x_i, \ldots, x_n) 
- f(x_1, \ldots, x_i, \ldots, x_n)}{\Delta x_i}
$$

provided the limit exists.

Common notations include

:::{math}
:enumerated: false
\frac{\partial y}{\partial x_i},
\quad
\frac{\partial}{\partial x_i} f(x_1,\ldots,x_n),
\quad
f_i.
:::

For a function $f(x,y)$, the partial derivative with respect to $x$ is written $f_x(x,y)$ or $f_x$; For a function $f(x_1,x_2)$, the partial derivative with respect to $x_1$ is written $f_1(x,y)$ or just $f_1$, and so on.

::::{admonition} Intuition
:class: note

A partial derivative measures how the function changes when **one variable changes and all others are held constant**.
::::

## Rules of Partial Differentiation

The rules of partial differentiation are the same as those for univariate calculus, except that **all other variables are treated as constants**.

**Examples**

**a)** Let

:::{math}
:enumerated: false
f(x_1,x_2) = \sqrt{x_1 + 3x_2^2}.
:::

has two partial derivatives:

:::{math}
:enumerated: false
f_1 = \frac{1}{2\sqrt{x_1 + 3x_2^2}},
\qquad
f_2 = \frac{3x_2}{\sqrt{x_1 + 3x_2^2}}.
:::

**b)** Similarly, let

:::{math}
:enumerated: false
h(x,y,z) = \ln(5x + 2y - 3z).
:::

then

:::{math}
:enumerated: false
h_x = \frac{5}{5x+2y-3z}, \quad
h_y = \frac{2}{5x+2y-3z}, \quad
h_z = \frac{-3}{5x+2y-3z}.
:::

##  Partial Derivatives in Economics

Consider the Cobb–Douglas production function

:::{math}
:enumerated: false
Q = AK^{1-\alpha}L^\alpha.
:::

The marginal product of labor is

:::{math}
:enumerated: false
\frac{\partial Q}{\partial L} 
= \alpha A K^{1 - \alpha} L^{\alpha - 1} 
= \alpha A \left( \frac{K}{L} \right)^{1 - \alpha}
:::

Similarly,

:::{math}
:enumerated: false
\frac{\partial Q}{\partial K} 
= (1 - \alpha) A K^{-\alpha} L^{\alpha} 
= (1 - \alpha) A \left( \frac{L}{K} \right)^{\alpha}
:::

::::{admonition} Economic interpretation
:class: note

In neoclassical theory, factors are paid their marginal products. Hence wages rise with capital intensity, and the return to capital is higher where labor is abundant.
::::

## Second-Order and Cross-Partial Derivatives

For

:::{math}
:enumerated: false
y = f(x_1,x_2),
:::

the second partial derivatives are

:::{math}
:enumerated: false
f_{11} = \frac{\partial^2 y}{\partial x_1^2},
\qquad
f_{22} = \frac{\partial^2 y}{\partial x_2^2}.
:::

The cross partial derivatives are

:::{math}
:enumerated: false
f_{12} = \frac{\partial^2 y}{\partial x_1 \partial x_2},
\qquad
f_{21} = \frac{\partial^2 y}{\partial x_2 \partial x_1}.
:::

### Young’s Theorem

If all second-order partial derivatives are continuous, then

:::{math}
:enumerated: false
f_{ij} = f_{ji}.
:::

::::{admonition} Why this matters
:class: note

Young’s Theorem ensures that the order of differentiation does not matter for well-behaved functions, a key assumption in optimization.
::::

## Multivariate Chain Rule

### Chain Rule I (single variable)

If

:::{math}
:enumerated: false
y = f(x_1,\ldots,x_n),
\quad
x_i = g^i(t),
:::

then

:::{math}
:enumerated: false
\frac{dy}{dt} 
= f_1 \frac{dx_1}{dt} 
+ f_2 \frac{dx_2}{dt} 
+ \cdots 
+ f_n \frac{dx_n}{dt}
:::

### Chain Rule II (multiple variables)

If

:::{math}
:enumerated: false
x_i = g^i(t_1,\ldots,t_m),
:::

then

:::{math}
:enumerated: false
\frac{\partial y}{\partial t_i} 
= f_1 \frac{\partial x_1}{\partial t_i} 
+ f_2 \frac{\partial x_2}{\partial t_i} 
+ \cdots 
+ f_n \frac{\partial x_n}{\partial t_i}
:::

## Total Differentials

For

:::{math}
:enumerated: false
y = f(x_1,\ldots,x_n),
:::

the total differential is

:::{math}
:enumerated: false
dz = z_x \, dx + z_y \, dy
:::

**Example**

Let

:::{math}
:enumerated: false
z = x^4 + 8xy + 3y^3.
:::

Then

:::{math}
:enumerated: false
dz = (4x^3 + 8y),dx + (8x + 9y^2),dy.
:::

## Total Derivatives

If $z=f(x,y)$ and $y=g(x)$, then

:::{math}
:enumerated: false
\frac{dz}{dx} = z_x + z_y \frac{dy}{dx}
:::

::::{admonition} Interpretation
:class: note

The total derivative captures **both direct and indirect effects** of a change in $x$.
::::

## Implicit Multivariate Differentiation

For an implicit function

:::{math}
:enumerated: false
F(y,x_1,\ldots,x_n)=k,
:::

with $F_y\neq 0$, there exists a function $y=f(x_1,\ldots,x_n)$ such that

## Homogeneous and Homothetic Functions

A function $f(x_1,\ldots,x_n)$ is **homogeneous of degree $k$** if

:::{math}
:enumerated: false
f(sx_1,\ldots,sx_n) = s^k f(x_1,\ldots,x_n).
:::

### Euler’s Theorem

If $f$ is homogeneous of degree $k$, then

A **homothetic function** is a monotonic transformation of a homogeneous function.


## 5.10 Examples in Economics

For the Cobb–Douglas function,


Proportionate scaling of inputs leaves the slope of the isoquant unchanged.

::::{admonition} Key implication
:class: important

Homogeneous and homothetic functions have **constant slopes along rays from the origin**, a crucial property in production theory.
::::

## Chapter Summary

::::{admonition} Summary
:class: important

* Partial derivatives measure marginal effects holding other variables fixed
* Second and cross partials capture curvature and interaction effects
* The multivariate chain rule links composite functions
* Total differentials and derivatives measure combined effects
* Homogeneity and homotheticity explain scale and substitution properties
* These tools underpin multivariate and constrained optimization in economics
  ::::
