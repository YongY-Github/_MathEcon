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

### Example - Cobb-Douglass production function

Consider the Cobb–Douglas production function

:::{math}
:enumerated: false
Q = AK^{1-\alpha}L^\alpha.
:::

The marginal product of labor (MPL) can be found by taking the partial derivative of output with respect to labor:

:::{math}
:enumerated: false
\frac{\partial Q}{\partial L} 
= \alpha A K^{1 - \alpha} L^{\alpha - 1} 
= \alpha A \left( \frac{K}{L} \right)^{1 - \alpha}
:::

In neo-classical economics theory, workers are paid a real wage equal to their marginal productivity of labor. So in the equation above we see that the real wage and MPL increase with larger capital stock relative to labor.

Similarly,

:::{math}
:enumerated: false
\frac{\partial Q}{\partial K} 
= (1 - \alpha) A K^{-\alpha} L^{\alpha} 
= (1 - \alpha) A \left( \frac{L}{K} \right)^{\alpha}
:::

Which suggests that the rate of return to capital is relatively high in countries that have a relatively large labor-capital ratios. These high rates of returns should cause capital inflow from rich to poor countries. But why do we not see this in reality? See @Lucas1990.
 
::::{admonition} Economic interpretation
:class: note

In neoclassical theory, factors are paid their marginal products. Hence wages rise with capital intensity, and the return to capital is higher where labor is abundant.
::::

## Multivariate Derivative Rules

**(1) Product Rule**

$$
\begin{aligned}
\frac{\partial}{\partial x}[f(x,y)g(x,y)]
&=
g(x,y)\frac{\partial f(x,y)}{\partial x}
+
f(x,y)\frac{\partial g(x,y)}{\partial x}, \\[2em]
\frac{\partial}{\partial y}[f(x,y)g(x,y)]
&=
g(x,y)\frac{\partial f(x,y)}{\partial y}
+
f(x,y)\frac{\partial g(x,y)}{\partial y}.
\end{aligned}
$$

**(2) Quotient Rule**

The derivative of the quotient of two (differentiable) functions, $f(x,y)/g(x,y)$, is

$$
\begin{aligned}
\frac{\partial}{\partial x}\left[\frac{f(x,y)}{g(x,y)}\right]
&=
\frac{
g(x,y)\frac{\partial f(x,y)}{\partial x}
-
f(x,y)\frac{\partial g(x,y)}{\partial x}
}{
[g(x,y)]^2
}, \\[2em]
\frac{\partial}{\partial y}\left[\frac{f(x,y)}{g(x,y)}\right]
&=
\frac{
g(x,y)\frac{\partial f(x,y)}{\partial y}
-
f(x,y)\frac{\partial g(x,y)}{\partial y}
}{
[g(x,y)]^2
}.
\end{aligned}
$$

where $f(x,y)$ and $g(x,y)$ are differentiable and $g(x,y)\neq 0$.

**(3) Generalized Power Function**

$$
\begin{aligned}
\frac{\partial [g(x,y)]^n}{\partial x}
&=
n[g(x,y)]^{\,n-1}\frac{\partial g(x,y)}{\partial x}, \\[1em]
\frac{\partial [g(x,y)]^n}{\partial y}
&=
n[g(x,y)]^{\,n-1}\frac{\partial g(x,y)}{\partial y}.
\end{aligned}
$$

where $n$ is a constant and $g(x,y)$ is differentiable.

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

Continuing with the examples above, the function

:::{math}
:enumerated: false
f(x_1, x_2) = \sqrt{x_1 + 3x_2^2}
:::

has two second partial derivatives

:::{math}
:enumerated: false
\begin{aligned}
f_{11}(x_1,x_2)
&=
-\frac{1}{4\left(x_1 + 3x_2^2\right)^{3/2}}, \\[2em]
f_{22}(x_1,x_2)
&=
-\frac{9x_2^2}{\left(x_1 + 3x_2^2\right)^{3/2}}
+
\frac{3}{\left(x_1 + 3x_2^2\right)^{1/2}}
\end{aligned}
:::

and the cross partial derivative

:::{math}
:enumerated: false
f_{12}(x_1,x_2)
=
f_{21}(x_1,x_2)
=
-\frac{3x_2}{2\left(x_1 + 3x_2^2\right)^{3/2}}.
:::

For the function

:::{math}
:enumerated: false
h(x,y,z) = \ln(5x + 2y - 3z)
:::

There are three second partial derivatives:

:::{math}
:enumerated: false
h_{xx}(x,y,z)
=
-\frac{25}{(5x + 2y - 3z)^2},
:::

:::{math}
:enumerated: false
h_{yy}(x,y,z)
=
-\frac{4}{(5x + 2y - 3z)^2},
\quad \text{and} \quad
h_{zz}(x,y,z)
=
-\frac{9}{(5x + 2y - 3z)^2}.
:::

The function also has three cross partial derivatives:

:::{math}
:enumerated: false
h_{xy}(x,y,z)
=
h_{yx}(x,y,z)
=
-\frac{10}{(5x + 2y - 3z)^2},
:::

:::{math}
:enumerated: false
h_{xz}(x,y,z)
=
h_{zx}(x,y,z)
=
-\frac{15}{(5x + 2y - 3z)^2},
\quad \text{and} \quad
:::

:::{math}
:enumerated: false
h_{yz}(x,y,z)
=
h_{zy}(x,y,z)
=
-\frac{6}{(5x + 2y - 3z)^2}
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

More generally, if all the partial derivatives of the function

:::{math}
:enumerated: false
f(x_1, x_2, \ldots, x_n)
:::

exist and are themselves differentiable with continuous derivatives, then

:::{math}
:enumerated: false
\frac{\partial}{\partial x_i}
\left(
\frac{\partial f(x_1, x_2, \ldots, x_n)}{\partial x_j}
\right)
=
\frac{\partial}{\partial x_j}
\left(
\frac{\partial f(x_1, x_2, \ldots, x_n)}{\partial x_i}
\right).
:::

Or, written differently,

:::{math}
:enumerated: false
f_{ji}(x_1, x_2, \ldots, x_n)
=
f_{ij}(x_1, x_2, \ldots, x_n),
:::

for any $i$ and $j$ from $1$ to $n$.

::::{admonition} Young’s Theorem and second derivatives
:class: important

Young’s Theorem shows that a multivariate function that is fully differentiable with respect to all its $n$ arguments has, at most, $n$ distinct second partial
derivatives, and $(n^2 - n)/2$ distinct cross partial derivatives.
::::

For our Cobb–Douglas production function,

:::{math}
:enumerated: false
Q = AK^{1-\alpha}L^{\alpha},
:::

the second partial derivative with respect to $L$ and with respect to $K$ is

:::{math}
:enumerated: false
\frac{\partial^2 Q}{\partial L^2}
=
-(1-\alpha)\alpha A K^{1-\alpha}L^{\alpha-1},
:::

:::{math}
:enumerated: false
\frac{\partial^2 Q}{\partial K^2}
=
-(1-\alpha)\alpha A K^{-\alpha-1}L^{\alpha}.
:::

Each of these second partial derivatives is negative, reflecting diminishing
marginal productivity.

The single cross partial derivative is

:::{math}
:enumerated: false
\frac{\partial^2 Q}{\partial K \partial L}
=
\frac{\partial^2 Q}{\partial L \partial K}
=
(1-\alpha)\alpha A K^{-\alpha}L^{\alpha-1},
:::

which is positive since $K$ and $L$ are positive.

::::{admonition} Economic intuition
:class: note

A positive cross partial derivative means that capital and labor are *complements*: increasing the use of one input raises the marginal productivity of the other. At the same time, the negative second partial derivatives capture diminishing marginal productivity of each input on its own.
::::

::::{admonition} Hessian matrix representation (optional)
:class: tip

The second-order derivatives of the Cobb–Douglas production function can be
summarized by the Hessian matrix

:::{math}
:enumerated: false
H(Q)
=
\begin{bmatrix}
\displaystyle \frac{\partial^2 Q}{\partial K^2}
&
\displaystyle \frac{\partial^2 Q}{\partial K \partial L}
\\[1em]
\displaystyle \frac{\partial^2 Q}{\partial L \partial K}
&
\displaystyle \frac{\partial^2 Q}{\partial L^2}
\end{bmatrix}
:::

The signs of the Hessian entries reflect diminishing marginal productivity
(negative diagonal terms) and complementarity between inputs (positive
off-diagonal terms).
::::

## Composite Functions and Multivariate Chain Rules

In the univariate case, we learnt that the derivative of the composite function

:::{math}
:enumerated: false
y = f(x) = g(h(x))
:::

is

:::{math}
:enumerated: false
\frac{dy}{dx} = g'(h(x))h'(x).
:::

A multivariate form of the chain rule can be used with multivariate compositefunctions.

## Multivariate Chain Rule I (Single Parameter)

If the arguments of the differentiable function  

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n)
:::

are themselves differentiable functions of a single variable $t$ such that  

:::{math}
:enumerated: false
x_1 = g^1(t), \quad x_2 = g^2(t), \quad \ldots, \quad x_n = g^n(t),
:::

where $g^i(t)$ is the $i$th univariate function, then  

:::{math}
:enumerated: false
\frac{dy}{dt}
=
f_1 \frac{dx_1}{dt}
+
f_2 \frac{dx_2}{dt}
+
\cdots
+
f_n \frac{dx_n}{dt},
:::

where  

:::{math}
:enumerated: false
f_i = \frac{\partial y}{\partial x_i}.
:::

**Example**

Consider the function  

:::{math}
:enumerated: false
y = f(x_1, x_2) = x_1^2 x_2,
:::

where  

:::{math}
:enumerated: false
x_1 = t^2
\quad \text{and} \quad
x_2 = 3t - 1.
:::

Then  

:::{math}
:enumerated: false
\frac{dx_1}{dt} = 2t
\quad \text{and} \quad
\frac{dx_2}{dt} = 3,
:::

and  

:::{math}
:enumerated: false
f_1 = 2x_1 x_2
\quad \text{and} \quad
f_2 = x_1^2.
:::

Using the chain rule,  

:::{math}
:enumerated: false
\frac{dy}{dt}
=
(2x_1 x_2)\frac{dx_1}{dt}
+
(x_1^2)\frac{dx_2}{dt}.
:::

Substituting,  

:::{math}
:enumerated: false
\frac{dy}{dt}
=
(2t^2(3t - 1))(2t)
+
3(t^2)^2
=
4t^3(3t - 1) + 3t^4.
:::

Simplifying,  

:::{math}
:enumerated: false
\frac{dy}{dt}
=
15t^4 - 4t^3.
:::

## Multivariate Chain Rule II (Multiple Parameters)

If the arguments of the differentiable function  

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n)
:::

are themselves differentiable functions of variables $t_1, \ldots, t_m$ such that  

:::{math}
:enumerated: false
x_1 = g^1(t_1, \ldots, t_m), \quad
\ldots, \quad
x_n = g^n(t_1, \ldots, t_m),
:::

then, for each $t_i$,  

:::{math}
:enumerated: false
\frac{\partial y}{\partial t_i}
=
f_1 \frac{\partial x_1}{\partial t_i}
+
f_2 \frac{\partial x_2}{\partial t_i}
+
\cdots
+
f_n \frac{\partial x_n}{\partial t_i},
:::

where  

:::{math}
:enumerated: false
f_i = \frac{\partial y}{\partial x_i}.
:::

::::{admonition} Key intuition
:class: important

The multivariate chain rule states that the total change in $y$ with respect to a
parameter is the sum of each marginal effect multiplied by how the corresponding
argument changes.

In other words,

:::{math}
:enumerated: false
\text{Total change}
=
\sum
\left(
\text{marginal effect}
\times
\text{change in argument}
\right).
:::

::::

## Total Differentials

The total differential of the multivariate function  

:::{math}
:enumerated: false
y = f(x_1, \ldots, x_n)
:::

evaluated at the point  

:::{math}
:enumerated: false
(x_1^0, x_2^0, \ldots, x_n^0)
:::

is  

:::{math}
:enumerated: false
\begin{aligned}
dy
&=
f_1(x_1^0, \ldots, x_n^0)\,dx_1
+
f_2(x_1^0, \ldots, x_n^0)\,dx_2 \\
&\quad
+
\cdots
+
f_n(x_1^0, \ldots, x_n^0)\,dx_n.
\end{aligned}
:::

where $f_i(x_1^0, x_2^0, \ldots, x_n^0)$ represents the partial derivative of the function $f(x_1, x_2, \ldots, x_n)$ with respect to its $i$th argument, evaluated at the point $(x_1^0, x_2^0, \ldots, x_n^0)$.

**Example**

Given  

:::{math}
:enumerated: false
z = f(x,y) = x^4 + 8xy + 3y^3,
:::

the total differential is  

:::{math}
:enumerated: false
dz = z_x\,dx + z_y\,dy.
:::

Since  

:::{math}
:enumerated: false
z_x = 4x^3 + 8y
\quad \text{and} \quad
z_y = 8x + 9y^2,
:::

we have  

:::{math}
:enumerated: false
dz = (4x^3 + 8y)\,dx + (8x + 9y^2)\,dy.
:::

### Higher-Order Total Differentials

We can take higher-order total differentials if required. Continuing with the same example, the second-order total differential is  

:::{math}
:enumerated: false
d^2 z
=
12x^2\,dx^2
+
16\,dx\,dy
+
18y\,dy^2.
:::

::::{admonition} Connection to the Multivariate Chain Rule
:class: important

The total differential provides a direct link to the multivariate chain rule.

If each variable $x_i$ depends on a single parameter $t$, then  

:::{math}
:enumerated: false
dx_i = \frac{dx_i}{dt}\,dt.
:::

Substituting into the total differential,

:::{math}
:enumerated: false
dy
=
\sum_{i=1}^n
\frac{\partial f}{\partial x_i}
\frac{dx_i}{dt}\,dt.
:::

Dividing both sides by $dt$ yields  

:::{math}
:enumerated: false
\frac{dy}{dt}
=
\sum_{i=1}^n
\frac{\partial f}{\partial x_i}
\frac{dx_i}{dt},
:::

which is precisely the **multivariate chain rule**.

Thus, the chain rule can be interpreted as applying the total differential to situations in which the arguments of a multivariate function depend on an underlying parameter.

::::

## Total Derivatives

Given a case with $z = f(x,y)$ and $y = g(x)$, that is, when $x$ and $y$ are not
independent, a change in $x$ will affect $z$ directly through the function $f$
and indirectly through the function $g$. The total derivative measures the direct
effect of $x$ on $z$, $\partial z / \partial x$, plus the indirect effect of $x$
on $z$ through $y$, $\partial z / \partial y \cdot dy/dx$.

That is,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x + z_y \frac{dy}{dx}.
:::

An alternative method of finding the total derivative is to take the total
differential of $z$,

:::{math}
:enumerated: false
dz = z_x\,dx + z_y\,dy,
:::

and divide through by $dx$. Thus,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x \frac{dx}{dx} + z_y \frac{dy}{dx}.
:::

But since $\frac{dx}{dx} = 1$,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x + z_y \frac{dy}{dx}.
:::

---

### Example 1

Given

:::{math}
:enumerated: false
z = f(x,y) = 6x^3 + 7y,
:::

where

:::{math}
:enumerated: false
y = 4x^2 + 3x,
:::

we have

:::{math}
:enumerated: false
z_x = 18x^2,
\quad
z_y = 7,
\quad
\frac{dy}{dx} = 8x + 3.
:::

Substituting into the total derivative,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x + z_y \frac{dy}{dx},
:::

gives

:::{math}
:enumerated: false
\frac{dz}{dx}
=
18x^2 + 7(8x + 3)
=
18x^2 + 56x + 21.
:::

---

### Example 2

The total derivative can also accommodate other relationships. Given

:::{math}
:enumerated: false
z = f(x,y) = 8x^2 + 3y^2,
:::

where

:::{math}
:enumerated: false
x = 4t
\quad \text{and} \quad
y = 5t,
:::

the total derivative of $z$ with respect to $t$ becomes

:::{math}
:enumerated: false
\frac{dz}{dt}
=
z_x \frac{dx}{dt} + z_y \frac{dy}{dt}.
:::

Since

:::{math}
:enumerated: false
z_x = 16x,
\quad
z_y = 6y,
\quad
\frac{dx}{dt} = 4,
\quad
\frac{dy}{dt} = 5,
:::

substituting gives

:::{math}
:enumerated: false
\frac{dz}{dt}
=
16x(4) + 6y(5)
=
64x + 30y.
:::

Finally, substituting $x = 4t$ and $y = 5t$ yields

:::{math}
:enumerated: false
\frac{dz}{dt}
=
64(4t) + 30(5t)
=
406t.
:::


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


## Examples in Economics

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
