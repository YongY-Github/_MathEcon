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

::::{dropdown} **Try these ^^**
For each of the following functions:

1. Compute the **first-order partial derivatives**
   :::{math}
   :enumerated: false
   \frac{\partial y}{\partial x_1}, \qquad \frac{\partial y}{\partial x_2}.
   :::

2. For each functions, evaluate the first-order partial derivatives at the point
   :::{math}
   :enumerated: false
   x_1 = 1, \quad x_2 = 4.
   :::

3. For each functions, compute the **second-order partial derivatives**
   :::{math}
   :enumerated: false
   \frac{\partial^2 y}{\partial x_1^2}, \qquad
   \frac{\partial^2 y}{\partial x_2^2},
   ::: 
   and the **cross partial derivative**
   :::{math}
   :enumerated: false
   \frac{\partial^2 y}{\partial x_1 \partial x_2}.
   :::

Assume all functions are defined on domains where the expressions are well-defined.

**(i)** $y = f(x_1,x_2) = 12x_1^4 - 6x_1^2x_2 + 4x_2^3$

**(ii)** $y = f(x_1,x_2) = (3x_1^2 + 5x_2 + 1)(x_2 + 4)$

**(iii)** $y = f(x_1,x_2) = \frac{7x_1 - x_1x_2^2}{x_1 - 2}$

**(iv)** $y = f(x_1,x_2) = (2e^{x_1})(e^{2x_1}x_2^2)$

**(v)** $y = f(x_1,x_2) = 2\ln(3x_1) - 4\ln(2x_1x_2)$

**(vi)** $y = f(x_1,x_2) = x_1^2 + 2x_1x_2^{1/2} - 4x_2$

---

**Answers: First-Order Partial Derivatives**

**(i)** $\frac{\partial y}{\partial x_1} = 48x_1^3 - 12x_1x_2,
\qquad
\frac{\partial y}{\partial x_2} = -6x_1^2 + 12x_2^2$

**(ii)** $\frac{\partial y}{\partial x_1} = 6x_1x_2 + 24x_1,
\qquad
\frac{\partial y}{\partial x_2} = 3x_1^2 + 5x_1 + 1
$

**(iii)** $\frac{\partial y}{\partial x_1} = \frac{2x_2^2 - 14}{(x_1 - 2)^2},
\qquad
\frac{\partial y}{\partial x_2} =
-\frac{2x_1x_2}{x_1 - 2}
$

**(iv)** $\frac{\partial y}{\partial x_1} = 6x_2^2 e^{3x_1},
\qquad
\frac{\partial y}{\partial x_2} = 4x_2 e^{3x_1}
$

**(v)** $
\frac{\partial y}{\partial x_1} = -\frac{2}{x_1},
\qquad
\frac{\partial y}{\partial x_2} = -\frac{4}{x_2}
$

**(vi)** $\frac{\partial y}{\partial x_1} = 2x_1 + 2\sqrt{x_2},
\qquad
\frac{\partial y}{\partial x_2} = \frac{x_1}{\sqrt{x_2}} - 4
$

---

**Answers 2**

**(i)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = 0,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = 186
$

**(ii)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = 88,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = 9
$

**(iii)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = 18,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = 8
$

**(iv)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = 1928,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = 321
$

**(v)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = -2,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = -1
$

**(vi)** $\left.\frac{\partial y}{\partial x_1}\right|_{(1,4)} = 6,
\qquad
\left.\frac{\partial y}{\partial x_2}\right|_{(1,4)} = -\frac{7}{2}
$

---

**3. Second-Order and Cross Partial Derivatives**

For each function, compute: $\dfrac{\partial^2 y}{\partial x_1^2}$, $\dfrac{\partial^2 y}{\partial x_2^2}$, and $\dfrac{\partial^2 y}{\partial x_1\partial x_2}$.

**Answers: Second-Order and Cross Partial Derivatives**

**(i)** $
\frac{\partial^2 y}{\partial x_1^2} = 144x_1^2 - 12x_2,
\qquad
\frac{\partial^2 y}{\partial x_2^2} = 24x_2,
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} = -12x_1
$

**(ii)** $
\frac{\partial^2 y}{\partial x_1^2} = 6x_2 + 24,
\qquad
\frac{\partial^2 y}{\partial x_2^2} = 6x_1 + 5,
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} = 6x_1
$

**(iii)** $
\frac{\partial^2 y}{\partial x_1^2} =
-\frac{4(x_1x_2^2 - 2x_2^2 - 7x_1 + 14)}{(x_1 - 2)^3},
\qquad
\frac{\partial^2 y}{\partial x_2^2} =
\frac{4x_1}{(x_1 - 2)^2},
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} =
-\frac{4x_2}{(x_1 - 2)^2}
$

**(iv)** $
\frac{\partial^2 y}{\partial x_1^2} = 18x_2^2 e^{3x_1},
\qquad
\frac{\partial^2 y}{\partial x_2^2} = 4e^{3x_1},
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} = 12e^{3x_1}x_2
$

**(v)** $
\frac{\partial^2 y}{\partial x_1^2} = \frac{2}{x_1^2},
\qquad
\frac{\partial^2 y}{\partial x_2^2} = \frac{4}{x_2^2},
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} = 0
$

**(vi)** $
\frac{\partial^2 y}{\partial x_1^2} = 2,
\qquad
\frac{\partial^2 y}{\partial x_2^2} = -\frac{1}{2}x_1 x_2^{-3/2},
\qquad
\frac{\partial^2 y}{\partial x_1\partial x_2} = x_2^{-1/2}
$

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

:::::{dropdown} **Try these ^^**
### Partial Derivatives with Change of Variables

For each of the following cases, find the partial derivatives $\displaystyle \frac{\partial Z}{\partial u}$ and $\displaystyle \frac{\partial Z}{\partial v}$.

**(i)** Let $Z = f(x,y) = 4x^2 + 2xy + y^2,$ where $x = 3u^2 \text{ and } y = u - 2v$

**(ii)** Let $Z = f(x,y) = ax^3 - bx^2y + cy,$ where $x = \gamma u + \theta v \text{ and } y = \theta u - \gamma v^2$

**(iii)** Let $Z = f(x,y) = 2e^x + \tfrac{1}{2}x^2y - 4y,$ where $x = \tfrac{1}{4}u \text{ and } y = u^2 + 6v$

**(iv)** Let $Z = f(x,y,u) = 2x^3 - 3xy^2 + 0.75yu - 5u^2,$ where $x = \sqrt{u+v} \text{ and } y = v^2$

---

**Answers**

**(i)** $\frac{\partial Z}{\partial u} = 48xu + 12yu + 2x + 2y, \text{ and } \frac{\partial Z}{\partial v} = -4x - 4y$

**(ii)** $\frac{\partial Z}{\partial u} = (3ax^2 - 2bxy)\gamma + (-bx^2 + c)\theta, \text{ and } \frac{\partial Z}{\partial v} = (3ax^2 - 2bxy)\theta + (-bx^2 + c)(-2\gamma v)$

**(iii)** $\frac{\partial Z}{\partial u} = (2e^x + xy)\tfrac{1}{4} + \left(\tfrac{1}{2}x^2 - 4\right)2u, \text{ and } \frac{\partial Z}{\partial v} = 3x^2 - 24$

**(iv)** $\frac{\partial Z}{\partial u} = (6x^2 - 3y^2)\frac{1}{2\sqrt{u+v}} + 0.75y - 10u, \text{ and } \frac{\partial Z}{\partial v} = (6x^2 - 3y^2)\frac{1}{2\sqrt{u+v}} + (-6xy + 0.75u)2v$

::::{admonition} Common pitfall: direct vs indirect effects
:class: warning

In parts (i)–(iii), the variable $Z$ depends on $u$ and $v$ **only through** the intermediate variables $x$ and $y$.
The multivariate chain rule therefore involves **only indirect effects**.

In part (iv), however, $Z = f(x,y,u)$ depends on $u$ **both directly and indirectly** (through $x$).
As a result,

:::{math}
:enumerated: false
\frac{\partial Z}{\partial u}
=
Z_x \frac{\partial x}{\partial u}
+
Z_y \frac{\partial y}{\partial u}
+
Z_u.
:::

A very common mistake is to **omit the direct term $Z_u$**, which leads to an incomplete derivative.
::::

:::::

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

:::::{dropdown} **Try these ^^**
### Total Differentials

**1. Find the total differentials of each function.**

**(i)** $w = 2x^2 + \frac{1}{2}xy - 3y^3$  
**(ii)** $w = 4x_1^3 - \ln(x_1 x_2) + 6x_2$  
**(iii)** $z = \dfrac{x^2}{y^3 + xy}$  
**(iv)** $y = 2x_1^2 e^{3x_2}$

**2. For each function, use the total differential to approximate the change in $y$ due to the given changes in $x$ and $z$.**

**(i)** $y = x^2 + 4x - z^2 - 2xz$,
   where $x = 1$, $z = 4$, $\Delta x = 2$, $\Delta z = -2$

**(ii)** $y = e^{x^2 + 3z}$,
   where $x = 1$, $z = 2$, $\Delta x = 2$, $\Delta z = -2$

**(iii)** $y = \ln x^3 - 4z + 2xz$,
   where $x = 1$, $z = 2$, $\Delta x = 2$, $\Delta z = 4$

**(iv)** $y = x^2 + e^{z/2}$,
   where $x = 2$, $z = 2$, $\Delta x = 1$, $\Delta z = -1$

---

**Answers: Question 1**

**(i)** $dw = (4x + \tfrac{1}{2}y),dx + (\tfrac{1}{2}x - 9y^2),dy$ **(ii)** $dw = \left(12x_1^2 - \frac{1}{x_1}\right),dx_1 + \left(6 - \frac{1}{x_2}\right),dx_2$ **(iii)** $dz = \dfrac{2xy^3 + x^2y}{(y^3 + xy)^2},dx - \dfrac{3x^2y^2 + x^3}{(y^3 + xy)^2},dy$ **(iv)** $dy = (4x_1 e^{3x_2}),dx_1 + (6x_1^2 e^{3x_2}),dx_2$

---

**Answers: Question 2**

**(i)** $\Delta y = 24$, $dy = 16$ **(ii)** $\Delta y = 7007$, $dy = -2194$ **(iii)** $\Delta y = 19.3$, $dy = 6$ **(iv)** $dy = 2x,dx + \tfrac{1}{2}e^{z/2},dz = 4 - \tfrac{1}{2}e = 2.64$. Actual change is $\Delta y = 3.93$

::::{admonition} Interpretation
:class: important

The total differential provides a **local linear approximation** to the actual change in a function.

When changes are small, $dy$ closely approximates $\Delta y$.
When changes are large or the function is highly nonlinear, the approximation may be poor.
::::

:::::

## Total Derivatives

Given a case with
$z = f(x,y)$ and $y = g(x)$,
that is, when $x$ and $y$ are not independent, a change in $x$ will affect $z$ directly through the function $f$ and indirectly through the function $g$.

The total derivative measures the **direct effect** of $x$ on $z$, $\partial z / \partial x$, plus the **indirect effect** of $x$ on $z$ through $y$, $(\partial z/\partial y)(dy/dx)$.

That is,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x + z_y \frac{dy}{dx}.
:::

::::{admonition} Connection to Total Differentiation
:class: tip

An alternative method of finding the total derivative is to take the **total differential** of $z$:

:::{math}
:enumerated: false
dz = z_x,dx + z_y,dy.
:::

Dividing through by $dx$ gives

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x \frac{dx}{dx}
+
z_y \frac{dy}{dx}.
:::

Since $dx/dx = 1$, this simplifies to

:::{math}
:enumerated: false
\frac{dz}{dx}
=
z_x + z_y \frac{dy}{dx}.
:::
::::

**Example 1**

Let

:::{math}
:enumerated: false
z = f(x,y) = 6x^3 + 7y,
:::

where

:::{math}
:enumerated: false
y = 4x^2 + 3x.
:::

Then

:::{math}
:enumerated: false
z_x = 18x^2,
\qquad
z_y = 7,
\qquad
\frac{dy}{dx} = 8x + 3.
:::

Substituting into the total derivative formula,

:::{math}
:enumerated: false
\frac{dz}{dx}
=
18x^2 + 7(8x + 3)
=
18x^2 + 56x + 21.
:::

**Example 2 (Parametric Dependence)**

Let

:::{math}
:enumerated: false
z = f(x,y) = 8x^2 + 3y^2,
:::

where

:::{math}
:enumerated: false
x = 4t,
\qquad
y = 5t.
:::

The total derivative of $z$ with respect to $t$ is

:::{math}
:enumerated: false
\frac{dz}{dt}
=
z_x \frac{dx}{dt}
+
z_y \frac{dy}{dt}.
:::

Since

:::{math}
:enumerated: false
z_x = 16x,
\qquad
z_y = 6y,
\qquad
\frac{dx}{dt} = 4,
\qquad
\frac{dy}{dt} = 5,
:::

we obtain

:::{math}
:enumerated: false
\frac{dz}{dt}
=
16x(4) + 6y(5)
=
64x + 30y.
:::

Substituting $x = 4t$ and $y = 5t$ gives

:::{math}
:enumerated: false
\frac{dz}{dt}
=
64(4t) + 30(5t)
=
256t + 150t
=
406t.
:::

:::::{dropdown} **Try these ^^**

### Total Derivatives

In the following questions, the function $f(x,y)$ depends on $x$ **both directly and indirectly** through $y$.
You must therefore compute the **total derivative**, not a partial derivative.

Recall that if $y = y(t)$, then

:::{math}
:enumerated: false
\frac{df}{dt} = f_x \frac{dx}{dt} + f_y \frac{dy}{dt}.
:::

**1. Total derivative with respect to $x$**

Find the total derivative $df(x,y)/dx$ for each of the following functions.

**(i)** $f(x,y) = 6x^2 + 15xy + 3y^2, 
\quad \text{where } y = 7x^2.$

**(ii)** $f(x,y) = \frac{9x - 7y}{2x + 5y},
\quad \text{where } y = 3x - 4.$

**(iii)** $f(x,y) = 8x - 12y,
\quad \text{where } y = \frac{x+1}{x^2}.
$

---

**2. Total derivative with respect to $w$**

Find the total derivative $df(x,y)/dw$ for each of the following functions.

**(i)** $f(x,y) = 7x^2 + 4y^2,
\quad \text{where } x = 5w \text{ and } y = 4w.
$

**(ii)** $f(x,y) = 10x^2 - 6xy - 12y^2,
\quad \text{where } x = 2w \text{ and } y = 3w.
$

---

::::{admonition} Common pitfall
:class: warning

Do **not** compute $f_x$ alone.

Because $y$ depends on the same variable as $x$ (either $x$ itself or $w$),
you must include **both terms**:

:::{math}
:enumerated: false
\frac{df}{dt} = f_x \frac{dx}{dt} + f_y \frac{dy}{dt}.
:::
::::

---

**Answers: Question 1**

**(i)**  $\frac{df}{dx}
= f_x + f_y \frac{dy}{dx}
= 210x^2 + 84xy + 12x + 15y.
$

**(ii)** $\frac{df}{dx}
= \frac{59(y - 3x)}{(2x + 5y)^2}.
$

**(iii)** $\frac{df}{dx}
= 8 + \frac{12(x+2)}{x^3}.
$

---

**Answers: Question 2**

**(i)** $\frac{df}{dw}
= f_x \frac{dx}{dw} + f_y \frac{dy}{dw}
= 14x(5) + 8y(4)
= 70x + 32y.
$

**(ii)** $\frac{df}{dw}
= (20x - 6y)(2) + (-6x - 24y)(3)
= 22x - 84y.
$

:::::

## Implicit Multivariate Differentiation

An **explicit function** expresses the dependent variable directly as a function of independent variables:

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n).
:::

An **implicit function** combines the dependent and independent variables in a relation of the form

:::{math}
:enumerated: false
F(y, x_1, x_2, \ldots, x_n) = k,
:::

where $k$ is a constant (possibly zero).

**Implicit Function Rule**

For an implicit function

:::{math}
:enumerated: false
F(y, x_1, x_2, \ldots, x_n) = k,
:::

defined at a point $(y^0, x_1^0, x_2^0, \ldots, x_n^0)$, assume $F$ has continuous first partial derivatives and

:::{math}
:enumerated: false
F_y(y^0, x_1^0, x_2^0, \ldots, x_n^0) \neq 0.
:::

Then there exists a function

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n)
:::

defined in a neighborhood of $(x_1^0, x_2^0, \ldots, x_n^0)$ such that:

:::{math}
:enumerated: false
F(f(x_1^0, x_2^0, \ldots, x_n^0), x_1^0, x_2^0, \ldots, x_n^0) = k,
:::

:::{math}
:enumerated: false
y^0 = f(x_1^0, x_2^0, \ldots, x_n^0),
:::

and

:::{math}
:enumerated: false
f_i(x_1^0, x_2^0, \ldots, x_n^0)
=
-
\frac{
F_{x_i}(y^0, x_1^0, x_2^0, \ldots, x_n^0)
}{
F_y(y^0, x_1^0, x_2^0, \ldots, x_n^0)
}.
:::

Here,

:::{math}
:enumerated: false
F_{x_i} = \frac{\partial F}{\partial x_i},
\qquad
F_y = \frac{\partial F}{\partial y},
:::

evaluated at $(y^0, x_1^0, x_2^0, \ldots, x_n^0)$.

This result is sometimes referred to as the **inverse rule for implicit functions**.

::::{admonition} Reminder
:class: warning

When using implicit differentiation, always compute **both** $F_x$ and $F_y$ carefully.
A sign error or a missing term in either partial derivative will lead to an incorrect result.
::::

::::{dropdown} **Try these ^^**

### Implicit and Inverse Function Rule

Find the derivative of each implicit function, where

:::{math}
:enumerated: false
\frac{dy}{dx} = -\frac{F_x}{F_y},
:::

provided that $F_y \neq 0$.

---

**(i)**  $F(x,y) = x^2 + y^2 + (xy)^{1/3} = 0$

**(ii)** $F(x,y) = x^2 y + y^2 x + xy = 0$

**(iii)** $F(x,y) = \ln x^3 + (xy)^2 - 4y = 0$

**(iv)** $F(x,y,w) = w^3 y^3 + x^2 + wxy + 7 = 0$ (Find $\partial y / \partial x$)

**(v)** $F(x,y) = xy^2 e^y = 0$

---

**Answers**

**(i)**  $\frac{dy}{dx} = -\frac{6x + x^{-2/3} y^{1/3}}{6y + y^{-2/3} x^{1/3}}$ **(ii)**  $\frac{dy}{dx} = -\frac{y(2x + y + 1)}{x(2y + x + 1)}$ **(iii)**  $\frac{dy}{dx} = -\frac{3x^{-1} + 2xy^2}{2x^2 y - 4}$ **(iv)**  $\frac{\partial y}{\partial x} = -\frac{3x^2 + wy}{3w^3 y^2 + wx}$ **(v)**  $\frac{dy}{dx} = -\frac{y}{x(2 + y)}$

::::

## Homogeneous Functions and Euler’s Theorem

A function $y = f(x_1, \ldots, x_n)$ is **homogeneous of degree $k$** if, for any $s > 0$,

:::{math}
:enumerated: false
f(sx_1, \ldots, sx_n) = s^k f(x_1, \ldots, x_n).
:::

::::{admonition} Tip
:class: important

To check homogeneity, scale all arguments by a common factor $s$ and verify whether
$f(sx, sy, sw) = s^k f(x,y,w)$ for some constant $k$.

If different terms scale with **different powers of $s$**, the function is **not homogeneous**.
::::

### Euler’s Theorem

If $y = f(x_1, \ldots, x_n)$ is homogeneous of degree $k$, then

:::{math}
:enumerated: false
k y
===

x_1 f_1(x_1, \ldots, x_n)
+
\cdots
+
x_n f_n(x_1, \ldots, x_n),
:::

where

:::{math}
:enumerated: false
f_i = \frac{\partial f}{\partial x_i}.
:::

### Proof of Euler’s Theorem

By homogeneity,

:::{math}
:enumerated: false
f(sx_1, \ldots, sx_n) = s^k y.
:::

Taking the derivative with respect to $s$ of the left-hand side,

:::{math}
:enumerated: false
\frac{d}{ds} f(sx_1, \ldots, sx_n)
=
x_1 f_1(sx_1, \ldots, sx_n)
+
\cdots
+
x_n f_n(sx_1, \ldots, sx_n).
:::

Differentiating the right-hand side,

:::{math}
:enumerated: false
\frac{d}{ds}(s^k y) = k s^{k-1} y.
:::

Setting $s = 1$ yields Euler’s Theorem.

**Notes**

**Note 1.**
Any function homogeneous of degree $0$ can be written as

:::{math}
:enumerated: false
f!\left(
\frac{x_1}{x_i}, \frac{x_2}{x_i}, \ldots, 1, \ldots, \frac{x_n}{x_i}
\right),
:::

for any $i = 1, \ldots, n$.

**Note 2.**
If $f(x_1, \ldots, x_n)$ is homogeneous of degree $k$, then each partial derivative

:::{math}
:enumerated: false
f_i = \frac{\partial f}{\partial x_i}
:::

is homogeneous of degree $k-1$.

## Homothetic Functions

A homothetic function is a monotonic transformation of a homogeneous function.

That is, if

:::{math}
:enumerated: false
y = f(x_1, \ldots, x_n)
:::

is a homogeneous function, then

:::{math}
:enumerated: false
z = g(y)
:::

is a homothetic function if $g(y)$ is a strictly monotonic transformation, i.e.,

:::{math}
:enumerated: false
g'(y) > 0 \quad \text{for all } y
\quad \text{or} \quad
g'(y) < 0 \quad \text{for all } y.
:::

**Note.** While every homogeneous function is a homothetic function (since we can simply choose $g(y) = y$), not every homothetic function is homogeneous.

**Example**

For example, take

:::{math}
:enumerated: false
y = x_1^{\alpha} x_2^{\beta},
:::

which is homogeneous of degree $\alpha + \beta$.

Taking logarithms, we obtain

:::{math}
:enumerated: false
z = \ln(y) = \alpha \ln(x_1) + \beta \ln(x_2).
:::

The function $z$ is homothetic since the logarithm function is strictly monotonic.

However, this homothetic function is **not homogeneous** in the arguments $x_1$ and $x_2$, since

:::{math}
:enumerated: false
\alpha \ln(sx_1) + \beta \ln(sx_2)
=
\alpha \ln(x_1) + \beta \ln(x_2) + (\alpha + \beta)\ln(s)
:::

and therefore

:::{math}
:enumerated: false
z(sx_1, sx_2)
=
z(x_1, x_2) + (\alpha + \beta)\ln(s),
:::

which does not satisfy the definition of homogeneity.


::::{admonition} Homothetic Functions
:class: tip

Homothetic functions preserve **input rankings and marginal rates of substitution**, but not proportional scaling.
::::

## Examples in Economics

Consider a Cobb–Douglas production function

:::{math}
:enumerated: false
Q = A K^{1-\alpha} L^{\alpha}
:::

The tangent (slope) to its isoquant is

:::{math}
:enumerated: false
\frac{dK}{dL}
=
\left( \frac{\alpha}{1-\alpha} \right)\frac{K}{L}
:::

An interesting property of the Cobb–Douglas production function is that the ratio of its marginal products depends on the capital–labor ratio and not on the overall level of production.

Hence multiplying $K$ and $L$ by some factor $s$ leaves the slope unchanged:

:::{math}
:enumerated: false
\frac{dK}{dL}
=
\left( \frac{\alpha}{1-\alpha} \right)\frac{K}{L}
=
\left( \frac{\alpha}{1-\alpha} \right)\frac{sK}{sL}
:::

More generally, the slope of the level curves of any homogeneous function is constant along any ray from the origin.
The slope of a level curve of a function $f(x_1,x_2)$ is

:::{math}
:enumerated: false
\frac{dx_2}{dx_1}
=
\frac{f_1(x_1,x_2)}{f_2(x_1,x_2)}
:::

Now recall that for a homogeneous function of degree $k$,

:::{math}
:enumerated: false
f_i(sx_1,sx_2)
=
s^{k-1} f_i(x_1,x_2)
:::

Thus along a ray from the origin,

:::{math}
:enumerated: false
\begin{aligned}
\frac{dx_2}{dx_1}
&=
\frac{f_1(sx_1,sx_2)}{f_2(sx_1,sx_2)} [0.5em]
&=
\frac{s^{k-1} f_1(x_1,x_2)}{s^{k-1} f_2(x_1,x_2)} [0.5em]
&=
\frac{f_1(x_1,x_2)}{f_2(x_1,x_2)} .
\end{aligned}
:::

Put differently, any proportional scaling $s$ of the two arguments $x_1$ and $x_2$ leaves the slope unchanged.

This property also extends to **homothetic functions**.

Consider the function

:::{math}
:enumerated: false
y = f(x_1,x_2),
:::

which we assume to be homogeneous of degree $k$, and the homothetic transformation

:::{math}
:enumerated: false
z = g(y) = g(f(x_1,x_2)),
:::

where $g'(y) > 0$ for all $y$ or $g'(y) < 0$ for all $y$.

Using the chain rule together with the **Implicit Function Theorem**, we obtain

:::{math}
:enumerated: false
\begin{aligned}
\frac{dx_2}{dx_1}
&=
\frac{g'(y) f_1(sx_1,sx_2)}{g'(y) f_2(sx_1,sx_2)}
&=
\frac{f_1(sx_1,sx_2)}{f_2(sx_1,sx_2)}
&=
\frac{s^{k-1} f_1(x_1,x_2)}{s^{k-1} f_2(x_1,x_2)}
&=
\frac{f_1(x_1,x_2)}{f_2(x_1,x_2)}
\end{aligned}
:::

Thus, as with homogeneous functions, the scaling factor $s$ does not affect the slope of the level curve.
This shows that the slope of the level curves of **any homothetic function**—a class that includes but is not limited to homogeneous functions—is not altered by proportional scaling of all its arguments.

::::{admonition} Key implication
:class: important

Homogeneous and homothetic functions have **constant slopes along rays from the origin**, a crucial property in production theory.
::::

<!--
:::{comment}
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
:::