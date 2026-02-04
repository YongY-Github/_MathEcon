# Basic Differentiation

Before we study the differentiation of single-variable functions, we briefly review several foundational mathematical concepts.

---

## 1. Functions

A function $ f $ from a set $ X $ to a set $ Y $, written $ f: X \to Y $, is a rule that assigns **exactly one** element of $ Y $ to each element of $ X $.

- $X$ is called the **domain**
- The **range** is the set of values in $Y$ that are actually attained

Using $x \in X$ and $y \in Y$, a function is written as
$ y = f(x) $,
where $x$ is the independent variable and $y$ the dependent variable.

---

## 2. Graphs

If $X$ and $Y$ are sets of real numbers, the **graph** of a function $f$ is the set of points
$(x, y)$ such that $y = f(x)$.

> **Economic convention.**  
> Economists often draw demand curves with quantity on the horizontal axis and price on the vertical axis, even when the function is written as $ q = f(p) $.

---

## 3. Slope

The slope of a line through points $(x, y)$ and $(x', y')$ is

:::{math}
:enumerated: false
m = \frac{y' - y}{x' - x}.
:::

Differentiation is the method of finding the slope of a function and is denoted by $ f'(x) $.

---

## 4. Limits

We say that a function $f$ has **limit** $L$ as $x \to a$ if, for any $\varepsilon > 0$, there exists a $\delta > 0$ such that

:::{math}
:enumerated: false
|f(x) - L| < \varepsilon
\quad \text{whenever} \quad
0 < |x - a| < \delta.
:::

When this holds, we write

:::{math}
:enumerated: false
\lim_{x \to a} f(x) = L.
:::

---

## 5. Continuity

A function $f$ is **continuous at $a$** if:

1. $f(a)$ is defined  
2. $\lim_{x \to a} f(x)$ exists  
3. $\lim_{x \to a} f(x) = f(a)$

---

## 6. Derivative at a Point

Let $y = f(x)$. When $x$ changes by $\Delta x$, the change in $y$ is

:::{math}
:enumerated: false
\frac{\Delta y}{\Delta x}
=
\frac{f(x+\Delta x) - f(x)}{\Delta x}.
:::

The **derivative of $f$ at $x$** is defined as

:::{math}
:enumerated: false
f'(x)
=
\lim_{\Delta x \to 0}
\frac{f(x+\Delta x) - f(x)}{\Delta x}.
:::

Geometrically, $f'(x)$ is the slope of the tangent line to the graph of $f$ at $(x, f(x))$.

---

## 7. Derivative as a Function

If the derivative exists for every $x$ in the domain of $f$, then the derivative itself defines a new function, denoted $f'(x)$.

Common notations include:
- $ f'(x) $
- $ \dfrac{dy}{dx} $
- $ Df(x) $

---

## 8. Second Derivative

The **second derivative** is the derivative of the derivative and is written as

:::{math}
:enumerated: false
f''(x)
=
\frac{d^2 f(x)}{dx^2}.
:::

> **Economic interpretation.**  
> If $ \ln p(t) $ describes log prices over time, then:
> - the first derivative is inflation
> - the second derivative is the change in inflation

---

## 9. Basic Rules of Differentiation

Let $y = f(x)$.

### (i) Constant Rule
:::{math}
:enumerated: false
\frac{d}{dx}(k) = 0.
:::

### (ii) Power Rule
:::{math}
:enumerated: false
\frac{d}{dx}(x^n) = n x^{n-1}.
:::

### (iii) Generalized Power Rule
:::{math}
:enumerated: false
\frac{d}{dx}(k x^n) = k n x^{n-1}.
:::

### (iv) Logarithmic Rule
:::{math}
:enumerated: false
\frac{d}{dx}(\ln x) = \frac{1}{x}.
:::

### (v) Exponential Rule
:::{math}
:enumerated: false
\frac{d}{dx}(a^x) = a^x \ln a.
:::

---

## 10. Sum, Product, and Chain Rules

Let $f(x)$ and $g(x)$ be differentiable.

### Sum Rule
:::{math}
:enumerated: false
\frac{d}{dx}[f(x) + g(x)] = f'(x) + g'(x).
:::

### Product Rule
:::{math}
:enumerated: false
\frac{d}{dx}[f(x)g(x)]
=
f'(x)g(x) + f(x)g'(x).
:::

### Chain Rule
If $z = f(y)$ and $y = g(x)$, then

:::{math}
:enumerated: false
\frac{dz}{dx}
=
\frac{dz}{dy}\frac{dy}{dx}.
:::

---

## 11. The Differential

Define $dx$ as an arbitrary change in $x$. The **differential of $y$** is

:::{math}
:enumerated: false
dy = f'(x_0)\, dx.
:::

This represents the change in $y$ along the tangent line at $x_0$.

---

## 12. Taylor Series (Preview)

A smooth function $f(x)$ can be approximated around $x=a$ by

:::{math}
:enumerated: false
f(x)
=
f(a)
+ f'(a)(x-a)
+ \frac{1}{2}f''(a)(x-a)^2
+ \cdots
:::

This idea underlies many approximation methods in economics.
