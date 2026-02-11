# Unconstrained Optimization

Finding the “best” way to do a specific task in economics often involves what is called an **optimization problem**.

## Univariate Optimization

## Stationary Points

Generally, we say that $x^*$ is a **stationary point** of a differentiable function $f(x)$ when its slope evaluated at $x^*$ is zero, i.e., when

:::{math}
:enumerated: false
f'(x^*) = 0.
:::

## Necessary First-Order Condition (F.O.C)

More formally, suppose a function $f(x)$ is differentiable in some interval $I$ and that $x^*$ is an interior point of $I$.
Then for $x = x^*$ to be a maximum or minimum point for $f(x)$ in $I$, a **necessary condition** is that it is a stationary point for $f(x)$, i.e., $x = x^*$ satisfies

:::{math}
:enumerated: false
f'(x^*) = 0.
:::

**Example 1**

Let

:::{math}
:enumerated: false
h(x) = -x^2 + 8x - 15.
:::

**F.O.C:**

:::{math}
:enumerated: false
-2x + 8 = 0.
:::

So the stationary point is $x^* = 4$ and $y^* = 1$.

**Example 2**

Let

:::{math}
:enumerated: false
z(x) = x^2 - 8x + 17.
:::

**F.O.C:**

:::{math}
:enumerated: false
2x - 8 = 0.
:::

So the stationary point is $x^* = 4$ and $y^* = 1$.

We have the same stationary point, but clearly these are different functions.
The former is **$\cap$-shaped** and the latter is **$\cup$-shaped**.

## Sufficient Second-Order Condition (S.O.C) for Maximum/Minimum

Following the two examples above, we can characterize a stationary point as a maximum or minimum by taking the second derivative.

* If $f''(x^*) < 0$, the stationary point represents a **maximum**.
* If $f''(x^*) > 0$, the stationary point represents a **minimum**.

**Example 1**

:::{math}
:enumerated: false
h''(x) = -2.
:::

Since this is negative, the stationary point $(4,1)$ is a **maximum**.

**Example 2**

:::{math}
:enumerated: false
z''(x) = 2.
:::

Since this is positive, the stationary point $(4,1)$ is a **minimum**.

---

**Example 3**

Let

:::{math}
:enumerated: false
p(x) = \frac{1}{3}x^3 - \frac{1}{2}x^2 - 2x + 20.
:::

The **F.O.C** gives

:::{math}
:enumerated: false
p'(x) = x^2 - x - 2 = 0,
:::

which implies $x^* = -1$ and $x^* = 2$.

The **S.O.C** gives

:::{math}
:enumerated: false
p''(x) = 2x - 1.
:::

* At $x^* = -1$, $p''(-1) = -3 < 0$ → **maximum**
* At $x^* = 2$, $p''(2) = 3 > 0$ → **minimum**

---

### S.O.C Is Sufficient but Not Necessary

Consider

:::{math}
:enumerated: false
y = x^4.
:::

The **F.O.C** gives $x^* = 0$.

The **S.O.C** also gives $0$, which is neither positive nor negative.
Yet, $x^* = 0$ is clearly a **minimum**.

## Global and Local Minimum/Maximum

We must distinguish between **global** and **local** extrema.

### Global Maximum

If $f(x)$ is everywhere differentiable and has stationary point $x^*$, then $x^*$ is a **global maximum** if

:::{math}
:enumerated: false
f'(x) \ge 0 \text{ for all } x \le x^*,
\quad \text{and} \quad
f'(x) \le 0 \text{ for all } x \ge x^*.
:::

That is, the function increases up to $x^*$ and decreases afterward.

### Global Minimum

Similarly, $x^*$ is a **global minimum** if

:::{math}
:enumerated: false
f'(x) \le 0 \text{ for all } x \le x^*,
\quad \text{and} \quad
f'(x) \ge 0 \text{ for all } x \ge x^*.
:::

### Local Maximum / Minimum

We speak of a **local maximum or minimum** if $x^*$ is a stationary maximum or minimum **only in a neighborhood of $x^*$**, not over the entire domain.

## Concavity and Convexity

* If $f(x)$ is **strictly concave** on $(m,n)$ and has a stationary point $x^*$ with $m < x^* < n$, then $x^*$ is a **local maximum**.
* If $f(x)$ is strictly concave everywhere, it has at most one stationary point, which is a **global maximum**.

Conversely,

* If $f(x)$ is **strictly convex** on $(m,n)$ and has a stationary point $x^*$, then $x^*$ is a **local minimum**.
* If $f(x)$ is strictly convex everywhere, that stationary point is a **global minimum**.

## Inflection Points

Consider the function

:::{math}
:enumerated: false
k(x) = 1 + (x - 4)^3.
:::

The **F.O.C** gives a stationary point $(4,1)$.

The **S.O.C** evaluated at this point is $0$, so it is inconclusive.

We must then take higher-order derivatives.

If the **first nonzero higher-order derivative** evaluated at the stationary point is:

* **Odd-order** → inflection point
* **Even-order** → maximum or minimum (depending on sign)

For this example,

:::{math}
:enumerated: false
k'''(4) \ne 0,
:::

which is the third (odd) derivative.
Hence, $(4,1)$ is an **inflection point**.

---

## Economic Applications

* A Monopolist’s Optimal Pricing Scheme
* Strategic Behavior of Duopolists
* Rules versus Discretion in Monetary Policy
* The Inflation Tax and Seigniorage
* The Golden Rule

---

## Multivariate Optimization

We now generalize the univariate techniques to multivariate optimization. 

## Multivariate First-Order Condition

If we have a function

:::{math}
:enumerated: false
y = f(x_1, x_2, \ldots, x_n)
:::

that is differentiable with respect to each of its arguments and has a stationary point at
$(x_1^*, x_2^*, \ldots, x_n^*)$, then each of the partial derivatives at that point equals zero.

That is,

:::{math}
:enumerated: false
f_1(x_1^*, x_2^*, \ldots, x_n^*) = 0 \\
f_2(x_1^*, x_2^*, \ldots, x_n^*) = 0 \\
\vdots \\
f_n(x_1^*, x_2^*, \ldots, x_n^*) = 0
:::

**Example 1**

Consider the bivariate function

:::{math}
:enumerated: false
g(x_1, x_2) = 6x_1 - x_1^2 + 16x_2 - 4x_2^2
:::

The first-order conditions are

:::{math}
:enumerated: false
g_1(x_1, x_2) = 6 - 2x_1 = 0 \\
g_2(x_1, x_2) = 16 - 8x_2 = 0
:::

The single stationary point is therefore

:::{math}
:enumerated: false
x_1^* = 3, \quad x_2^* = 2
:::

and the value of the function at this point is

:::{math}
:enumerated: false
g(3,2) = 25.
:::

We will show later using the second-order condition that this stationary point represents a **maximum**.

Let's visualize the equation and its stationary point.

<img src="figs/max.png" alt="Stationary Point" width="70%"/>

If we take a slice of the function $g(x_1, x_2)$ at $x_2 = 2$, the stationary point is achieved at $x_1 = 3$.
Similarly, taking a slice at $x_1 = 3$ shows a stationary point at $x_2 = 2$. Visually, we have

<img src="figs/slice.png" alt="Stationary Point" width="90%"/>

**Example 2**

Consider the function

:::{math}
:enumerated: false
h(x_1, x_2) = x_1^2 + 4x_2^2 - 2x_1 - 16x_2 + x_1 x_2
:::

The first-order conditions give

:::{math}
:enumerated: false
h_1(x_1, x_2) = 2x_1 - 2 + x_2 = 0 \\
h_2(x_1, x_2) = 8x_2 - 16 + x_1 = 0
:::

Hence the single stationary point is

:::{math}
:enumerated: false
x_1^* = 0, \quad x_2^* = 2
:::

and the value of the function at this point is

:::{math}
:enumerated: false
h(0,2) = -16.
:::

Below is a visualization of this function with the plane tangent and stationary point.

<img src="figs/min.png" alt="Stationary Point" width="70%"/>

## Second-Order Condition in the Bivariate Case

For the univariate case, the second differential of a function can be considered as the differential of the first differential and denoted as

:::{math}
:enumerated: false
d(dy) = d^2 y.
:::

For $y = f(x)$, the second differential is

:::{math}
:enumerated: false
d^2 y = f''(x)(dx)^2,
:::

which is nonnegative for any $dx$.

### Second Differential in the Bivariate Case

For a bivariate function $y = f(x_1, x_2)$, the total differential is

:::{math}
:enumerated: false
dy = f_1(x_1, x_2),dx_1 + f_2(x_1, x_2),dx_2.
:::

Taking the total derivative of this expression yields the second total differential:

:::{math}
:enumerated: false
d^2 y
= f_{11}(dx_1)^2 + f_{22}(dx_2)^2 + 2f_{12}dx_1 dx_2.
:::

## Sufficient Conditions for Local Maxima and Minima

* If $d^2 y < 0$ for all $(dx_1, dx_2)$, the stationary point is a **local maximum**.
* If $d^2 y > 0$ for all $(dx_1, dx_2)$, the stationary point is a **local minimum**.

A necessary condition for a minimum is

:::{math}
:enumerated: false
f_{11} > 0 \quad \text{and} \quad f_{22} > 0,
:::

and for a maximum,

:::{math}
:enumerated: false
f_{11} < 0 \quad \text{and} \quad f_{22} < 0.
:::

However, the cross-partial derivative $f_{12}$ must also be considered.

### Completing the Square

By completing the square, the second differential can be rewritten, leading to the condition:

:::{math}
:enumerated: false
f_{11} f_{22} > (f_{12})^2.
:::

### Second-Order Condition for a Maximum

If $y = f(x_1, x_2)$ has a stationary point $(x_1^*, x_2^*)$ and

:::{math}
:enumerated: false
f_{11}(x_1^*, x_2^*) < 0
\quad \text{and} \quad
f_{11} f_{22} > (f_{12})^2,
:::

then the function reaches a **maximum** at that point.

### Second-Order Condition for a Minimum

If

:::{math}
:enumerated: false
f_{11}(x_1^*, x_2^*) > 0
\quad \text{and} \quad
f_{11} f_{22} > (f_{12})^2,
:::

then the function reaches a **minimum**.


::::{admonition} Special Cases
:class: important

* If $f_{11} f_{22} < (f_{12})^2$, the stationary point is a **saddle point**.
* If $f_{11} f_{22} = (f_{12})^2$, the test is **inconclusive**.
::::

Let's continue with the example above.

The second partial derivatives of  

:::{math}
:enumerated: false
h(x_1,x_2) = x_1^2 + 4x_2^2 - 2x_1 - 16x_2 + x_1x_2
:::

are  

:::{math}
:enumerated: false
h_{11}(x_1,x_2) = 2 \quad \text{and} \quad h_{22}(x_1,x_2) = 8
:::

Both are positive. The cross-partial derivative is  

:::{math}
:enumerated: false
h_{12}(x_1,x_2) = 1.
:::

Since  

:::{math}
:enumerated: false
h_{11} h_{22} > (h_{12})^2,
:::

that is,

:::{math}
:enumerated: false
16 > 1,
:::

the stationary point $(0,2)$ is a **minimum**.

As another example, consider  

:::{math}
:enumerated: false
g(x_1,x_2) = 6x_1 - x_1^2 + 16x_2 - 4x_2^2.
:::

The second partial derivatives are  

:::{math}
:enumerated: false
g_{11}(x_1,x_2) = -2 \quad \text{and} \quad g_{22}(x_1,x_2) = -8,
:::

and the cross-partial derivative is  

:::{math}
:enumerated: false
g_{12}(x_1,x_2) = 0.
:::

Since the second partial derivatives are both negative and  

:::{math}
:enumerated: false
g_{11} g_{22} > (g_{12})^2,
:::

that is,

:::{math}
:enumerated: false
16 > 0,
:::

we have the conditions for a **maximum**.

## Second-Order Condition in the General Multivariate Case

Let us use the tools of matrix algebra to develop a set of conditions that enables us to find the sign of the second total differential of a multivariate function.

First, assume a **bivariate case** for which the second total differential is given by

:::{math}
:enumerated: false
d^2 y
=
f_{11}(dx_1)^2
+
f_{22}(dx_2)^2
+
2 f_{12}(dx_1)(dx_2).
:::

This expression can be written in **matrix form** as the quadratic form of the two variables $dx_1$ and $dx_2$ as follows:

:::{math}
:enumerated: false
d^2 y
=
\begin{bmatrix}
dx_1 & dx_2
\end{bmatrix}
\begin{bmatrix}
f_{11} & f_{12} \\
f_{21} & f_{22}
\end{bmatrix}
\begin{bmatrix}
dx_1 \\
dx_2
\end{bmatrix}.
:::

In other words, the second total differential (or second total derivative) for a multivariate function can be written more generally as

:::{math}
:enumerated: false
d^2 y
=
dx' H dx
=
\begin{bmatrix}
dx_1 & dx_2 & \cdots & dx_n
\end{bmatrix}
\begin{bmatrix}
f_{11} & f_{12} & \cdots & f_{1n} \\
f_{21} & f_{22} & \cdots & f_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
f_{n1} & f_{n2} & \cdots & f_{nn}
\end{bmatrix}
\begin{bmatrix}
dx_1 \\
dx_2 \\
\vdots \\
dx_n
\end{bmatrix}.
:::

Here, $H$ is the **Hessian matrix**, and $dx$ is the column vector of differentials.

All that remains is to determine the **sign definiteness** of the quadratic form by determining the sign definiteness of the Hessian.

### Interpreting the Second-Order Condition

The sign of the second total differential $d^2 y$ determines the local curvature of the function and therefore whether a critical point is a local maximum, minimum, or neither.

Because

:::{math}
:enumerated: false
d^2 y = dx' H dx,
:::

the problem reduces to determining the **sign definiteness of the Hessian matrix $H$**.

### Positive and Negative Definiteness

::::{admonition} Definition
:class: important

Let $H$ be a symmetric matrix.

* $H$ is **positive definite** if
  $dx' H dx > 0$ for all nonzero $dx$.
* $H$ is **negative definite** if
  $dx' H dx < 0$ for all nonzero $dx$.
* $H$ is **indefinite** if the quadratic form takes both positive and negative values.
  ::::

These cases correspond to the curvature of the function at a critical point.

### Second-Order Conditions for Optimization

Suppose $y = f(x_1, \ldots, x_n)$ and $\nabla f = 0$ at a point $x^*$.

::::{admonition} Second-Order Test
:class: important

* If $H(x^*)$ is **negative definite**, then $x^*$ is a **local maximum**.
* If $H(x^*)$ is **positive definite**, then $x^*$ is a **local minimum**.
* If $H(x^*)$ is **indefinite**, then $x^*$ is a **saddle point**.
  ::::

::::{admonition} Key Distinction
:class: important

• In **one variable**, if the first nonzero derivative at a stationary point is of **odd order**, the point is an **inflection point**.

• In **multiple variables**, if the Hessian is **indefinite** (determinant < 0), the stationary point is a **saddle point**.

An inflection point concerns curvature along a single line. A saddle point concerns curvature across different directions.
::::

---

## Sylvester’s Criterion (Practical Test)

In practice, definiteness is checked using **principal minors** of the Hessian.

### Bivariate Case ($n = 2$)

Let

:::{math}
:enumerated: false
H =
\begin{bmatrix}
f_{11} & f_{12} \\
f_{21} & f_{22}
\end{bmatrix}.
:::

Then:

::::{admonition} Sylvester’s Criterion (2 variables)
:class: tip

* $H$ is **positive definite** if
  $f_{11} > 0$ and $\det(H) > 0$.
* $H$ is **negative definite** if
  $f_{11} < 0$ and $\det(H) > 0$.
* $H$ is **indefinite** if
  $\det(H) < 0$.
  ::::

This criterion is widely used in economics because it avoids computing the quadratic form directly.

---

**Example**

Consider the function

:::{math}
:enumerated: false
y = -x_1^2 - 2x_2^2 + 4x_1 x_2.
:::

The Hessian matrix is

:::{math}
:enumerated: false
H =
\begin{bmatrix}
-2 & 4 \
4 & -4
\end{bmatrix}.
:::

Compute the determinant:

:::{math}
:enumerated: false
\det(H) = (-2)(-4) - 16 = -8 < 0.
:::

Since the determinant is negative, the Hessian is **indefinite**, and the critical point is a **saddle point**.

## Economic Interpretation

* Concavity (negative definite Hessian) corresponds to **diminishing marginal returns** and guarantees interior maxima in optimization problems.
* Convexity (positive definite Hessian) corresponds to **cost minimization** problems.
* Indefiniteness indicates **instability** or saddle behavior, common in strategic or general equilibrium settings.

::::{admonition} Key takeaway
:class: important

The second-order condition in multivariate optimization reduces to checking the **sign definiteness of the Hessian matrix**.
Matrix algebra provides a compact and powerful way to characterize curvature, stability, and optimality in economic models.
::::
