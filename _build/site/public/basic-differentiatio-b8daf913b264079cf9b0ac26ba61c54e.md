# Basic Differentiation

Before we study the differentiation of single-variable functions, we briefly review several foundational mathematical concepts.

## 1. Functions

A function $ f $ from a set $ X $ to a set $ Y $, written $ f: X \to Y $, is a rule that assigns **exactly one** element of $ Y $ to each element of $ X $.

- $X$ is called the **domain**
- The **range** is the set of values in $Y$ that are actually attained

Using $x \in X$ and $y \in Y$, a function is written as
$ y = f(x) $,
where $x$ is the independent variable and $y$ the dependent variable.

## 2. Graphs

If $X$ and $Y$ are sets of real numbers, the **graph** of a function $f$ is the set of points
$(x, y)$ such that $y = f(x)$.

> **Economic convention.**  
> Economists often draw demand curves with quantity on the horizontal axis and price on the vertical axis, even when the function is written as $ q = f(p) $.

## 3. Slope

The slope of a line through points $(x, y)$ and $(x', y')$ is

:::{math}
:enumerated: false
m = \frac{y' - y}{x' - x}.
:::

Differentiation is the method of finding the slope of a function and is denoted by $ f'(x) $.

## 4. Limits

We say that a function $f$ has **limit** $L$ as $x \to a$ if, for any $\varepsilon > 0$, there exists a $\delta > 0$ such that[^1]

:::{math}
:enumerated: false
|f(x) - L| < \varepsilon
\quad \text{whenever} \quad
0 < |x - a| < \delta.
:::

When this condition holds, we write

:::{math}
:enumerated: false
\lim_{x \to a} f(x) = L.
:::

[^1]: A function need not be defined at the point $a$ in order to have a limit as $x \to a$.
    For example,

    :::{math}
    :enumerated: false
    f(x) = \frac{x^2 - 1}{x - 1}
    :::

    is not defined at $x = 1$, but

    :::{math}
    :enumerated: false
    \lim_{x \to 1} f(x) = 2.
    :::

## 5. Continuity

A function $f$ is **continuous at $a$** if:[^2]

1. $f(a)$ is defined  
2. $\lim_{x \to a} f(x)$ exists  
3. $\lim_{x \to a} f(x) = f(a)$

[^2]: The two functions discussed above are not continuous.
    The first is not continuous because $f(a)$ is not defined.
    The second is not continuous because $f$ does not converge to a limit as $x \to a$.
    For example, if

    :::{math}
    :enumerated: false
    f(x) =
    \begin{cases}
    -1, & x < 0, \\
    1, & x > 0,
    \end{cases}
    :::

    then $f$ has no limit as $x \to 0$, since the right-hand limit equals $1$ while the left-hand limit equals $-1$.

## 6. Derivative at a Point

Let $y = f(x)$. When $x$ changes by $\Delta x$, the change in $y$ is

:::{math}
:enumerated: false
\frac{\Delta y}{\Delta x}
=
\frac{f(x+\Delta x) - f(x)}{\Delta x}.
:::

## 7. Derivative as a Function

The **derivative of $f$ at $x$** is defined as

:::{math}
:enumerated: false
f'(x)
=
\lim_{\Delta x \to 0}
\frac{f(x+\Delta x) - f(x)}{\Delta x}.
:::

If the derivative exists for every $x$ in the domain of $f$, then the derivative itself defines a new function, denoted $f'(x)$.

Geometrically, $f'(x)$ is the slope of the tangent line to the graph of $f$ at $(x, f(x))$.

Common notations include:
- $ f'(x) $
- $ \dfrac{dy}{dx} $
- $ Df(x) 0$

Note that what we usually think of as a variable $x$ is held constant while $\Delta x$ varies and converges to zero. It is useful to keep in mind that the derivative of a function $f$ at $x$ is the slope of a line tangent to the graph of the function $f$ at the point $(x, f(x))$. It is crucial to understand the implications of the existence of the derivative at a point $x$. The function must be smooth—meaning it is both continuous and differentiable—at the point $x$. The tangent line provides a high-quality linear approximation to the graph of the function near $x$. In general, if we know that the function $f$ is differentiable at $a$, then the tangent line approximation to $f$ at $a$ is:

:::{math}
:enumerated: false
y = f(a) + f'(a)(x - a)
:::

where $a, f(a), \text{ and } f'(a)$ are constants, $x$ is the independent variable, and $y$ is the dependent variable. We will see this point again with Taylor series expansions. Many important concepts in economics—such as marginal cost or marginal utility—are based on this derivative function.

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

### (i) Constant-function Rule
The derivative of a contsant function $y=f(x)=k$ is zero, for all values of x-it has zero slope!

:::{math}
:enumerated: false
\frac{d}{dx}(k) = 0.
:::

### (ii) Power-function Rule
The derivative of a power function $f(x) = x^n$ is:

:::{math}
:enumerated: false
\frac{d}{dx}(x^n) = n x^{n-1}.
:::

### (iii) Generalized Power-function Rule
When a multiplicaytive constant $k$ appears in the power fuction, so that $f(x) = kx^n$, then:

:::{math}
:enumerated: false
\frac{d}{dx}(k x^n) = k n x^{n-1}.
:::

### (iv) Logarithmic Rule
The derivatice of the log-function $f(x) = lnx$ is: 

:::{math}
:enumerated: false
\frac{d}{dx}(\ln x) = \frac{1}{x}.
:::

### (v) Exponential Rule
For some exponential function $f(x) = a^x$, where $a$ is some constant, then:  

:::{math}
:enumerated: false
\frac{d}{dx}(a^x) = a^x \ln a.
:::

Note that a particular case of the above is 

:::{math}
:enumerated: false
\frac{d}{d x} e^x = e^x
:::

While

:::{math}
:enumerated: false
\frac{d}{d x} \ln x = \frac{1}{x}
:::

---

Now, let's consider some further useful rules of differentiation involving two or more functions of the same variable. Specifically, suppose $f(x)$ and $g(x)$ are two different functions of $x$ and that $f'(x)$ and $g'(x)$ exist. That is, let $f(x)$ and $g(x)$ be differentiable, then:

## 10. Sum, Product, and Chain Rules
The derivative of a sum (difference) of two functions is the sum (difference) of the derivatives of the two functions.

### Sum Rule
:::{math}
:enumerated: false
\frac{d}{dx}[f(x) + g(x)] = f'(x) + g'(x).
:::

### Product Rule
The derivative of the product of two (differentiable) functions is equal to the first function times the derivative of the second function plus the second function times the derivative of the first function.

:::{math}
:enumerated: false
\frac{d}{dx}[f(x)g(x)]
=
f'(x)g(x) + f(x)g'(x).
:::

### Quotient Rule
The derivative of the quotient of two (differentiable) functions, $f(x)/g(x)$, is

:::{math}
:enumerated: false
\frac{d}{dx} \left[ \frac{f(x)}{g(x)} \right] = \frac{g(x)f'(x) - f(x)g'(x)}{[g(x)]^2}
:::

provided that $g(x) \neq 0$. Note that $[g(x)]^2 = g^2(x)$.

### Chain Rule
If $z = f(y)$ and $y = g(x)$, then

:::{math}
:enumerated: false
\frac{dz}{dx}
=
\frac{dz}{dy}\frac{dy}{dx}.
:::

Or, say, for a composite function $y = f(g(x))$ is

:::{math}
:enumerated: false
\frac{dy}{dx} = f'(g(x)) \cdot g'(x)
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
