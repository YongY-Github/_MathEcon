# Basic Differentiation

Before we study the differentiation of single-variable functions, we briefly review several foundational mathematical concepts.

## Functions

A function $ f $ from a set $ X $ to a set $ Y $, written $ f: X \to Y $, is a rule that assigns **exactly one** element of $ Y $ to each element of $ X $.

- $X$ is called the **domain**
- The **range** is the set of values in $Y$ that are actually attained

Using $x \in X$ and $y \in Y$, a function is written as
$ y = f(x) $,
where $x$ is the independent variable and $y$ the dependent variable.

## Graphs

If $X$ and $Y$ are sets of real numbers, the **graph** of a function $f$ is the set of points
$(x, y)$ such that $y = f(x)$.

> **Economic convention.**  
> Economists often draw demand curves with quantity on the horizontal axis and price on the vertical axis, even when the function is written as $ q = f(p) $.

## Slope

The slope of a line through points $(x, y)$ and $(x', y')$ is

:::{math}
:enumerated: false
m = \frac{y' - y}{x' - x}.
:::

Differentiation is the method of finding the slope of a function and is denoted by $ f'(x) $.

## Limits

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

## Continuity

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

## Derivative at a Point

Let $y = f(x)$. When $x$ changes by $\Delta x$, the change in $y$ is

:::{math}
:enumerated: false
\frac{\Delta y}{\Delta x}
=
\frac{f(x+\Delta x) - f(x)}{\Delta x}.
:::

## Derivative as a Function

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
- $ Df(x) $

Note that what we usually think of as a variable $x$ is held constant while $\Delta x$ varies and converges to zero. It is useful to keep in mind that the derivative of a function $f$ at $x$ is the slope of a line tangent to the graph of the function $f$ at the point $(x, f(x))$. It is crucial to understand the implications of the existence of the derivative at a point $x$. The function must be smooth—meaning it is both continuous and differentiable—at the point $x$. The tangent line provides a high-quality linear approximation to the graph of the function near $x$. In general, if we know that the function $f$ is differentiable at $a$, then the tangent line approximation to $f$ at $a$ is:

:::{math}
:enumerated: false
y = f(a) + f'(a)(x - a)
:::

where $a, f(a), \text{ and } f'(a)$ are constants, $x$ is the independent variable, and $y$ is the dependent variable. We will see this point again with Taylor series expansions. Many important concepts in economics—such as marginal cost or marginal utility—are based on this derivative function.

## Second Derivative

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

## Basic Rules of Differentiation

Let $y = f(x)$.

### Constant-function Rule
The derivative of a contsant function $y=f(x)=k$ is zero, for all values of x-it has zero slope!

:::{math}
:enumerated: false
\frac{d}{dx}(k) = 0.
:::

### Power-function Rule
The derivative of a power function $f(x) = x^n$ is:

:::{math}
:enumerated: false
\frac{d}{dx}(x^n) = n x^{n-1}.
:::

### Generalized Power-function Rule
When a multiplicaytive constant $k$ appears in the power fuction, so that $f(x) = kx^n$, then:

:::{math}
:enumerated: false
\frac{d}{dx}(k x^n) = k n x^{n-1}.
:::

### Logarithmic Rule
The derivatice of the log-function $f(x) = lnx$ is: 

:::{math}
:enumerated: false
\frac{d}{dx}(\ln x) = \frac{1}{x}.
:::

### Exponential Rule
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

Now, let's consider some further useful rules of differentiation involving two or more functions of the same variable. Specifically, suppose $f(x)$ and $g(x)$ are two different functions of $x$ and that $f'(x)$ and $g'(x)$ exist. That is, let $f(x)$ and $g(x)$ be differentiable, then:

### Sum-difference Rules
The derivative of a sum (difference) of two functions is the sum (difference) of the derivatives of the two functions.

:::{math}
:enumerated: false
\frac{d}{dx}[f(x) \pm g(x)] = f'(x) \pm g'(x).
:::


::::{dropdown} **Try these ^^**
Determine the derivative of each of the functions below.

1. $y = 30x + 10$

2. $y = 8x^2 - 6x + 12$

3. $y = 6$

4. $y = \sqrt{3} - 2x^2$

---

**Answers**

$1.\; f'(x) = 30 \quad
2.\; f'(x) = 16x - 6 \quad
3.\; f'(x) = 0 \quad
4.\; f'(x) = -4x$

::::

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

::::{dropdown} **Try these ^^**
Differentiate the following functions with respect to $x$.

1. $y=\dfrac{3x(2x-1)}{5x-2}$

2. $y=3x(4x-5)^2$

3. $y=(5x-1)(3x+4)^3$

4. $y=(3x-4)\dfrac{5x+1}{2x+7}$

5. $y=\dfrac{(8x-5)^3}{7x+4}$

6. $y=\left(\dfrac{3x+4}{2x+5}\right)^2$
---
**Answers**

$1.\; y'=\frac{30x^2-24x+6}{(5x-2)^2} \quad
2.\; y'=144x^2-240x+75 \quad
3.\;  y'=(45x-9)(3x+4)^2+5(3x+4)^3 \quad
4.\;  y'=\frac{30x^2+210x-111}{(2x+7)^2} \quad
5.\;  y'=\frac{(168x+96)(8x-5)^2-7(8x-5)^3}{(7x+4)^2} \quad
6.\;  y'=\frac{42x+56}{(2x+5)^3}$

---
Use the quotient rule to differentiate each function.

1. $f(x)=\dfrac{2x+7}{x^2-1}$

2. $f(x)=\dfrac{bx^3+cx^2+x-4}{x}$

3. $f(x)=\dfrac{e^{2x}}{x^2}$

4. $f(x)=\dfrac{(3x+2)^2}{x}$
---
**Answers**

$1.\; f'(x)=\frac{-2x^2-14x-2}{(x^2-1)^2} \quad
2.\; f'(x)=\frac{2bx^3+cx^2+4}{x^2} \\[6pt]
3.\; f'(x)=\frac{2xe^{2x}-2e^{2x}}{x^3} \quad
4.\; f'(x)=\frac{9x^2-4}{x^2}$

---
**Second Derivatives**

Find the second derivative of each function.

1. $y = 9 - 3x + 7x^2 - x^3$

2. $y = \dfrac{4x+5}{x}$

3. $y = \ln(4x)$

4. $y = x^2 e^x$

5. $y = (x-6)^4$
---
**Answers**

$1.\; y'' = 14 - 6x \quad
2.\; y'' = 10x^{-3} \quad
3.\; y'' = -x^{-2} \quad
4.\; y'' = 2e^x + 4xe^x + x^2 e^x \quad
5.\; y'' = 12(x-6)^2$
::::

### Chain Rule
If $z = f(y)$ and $y = g(x)$, then

:::{math}
:enumerated: false
\frac{dz}{dx}
=
\frac{dz}{dy}\frac{dy}{dx}.
:::

The chain rule provides a convenient way to study how one variable (say, $x$) affects another variable ($z$) through its influence on some intermediate variable ($y$).

Sometimes, we can write for a composite function $y = f(g(x))$:

:::{math}
:enumerated: false
\frac{dy}{dx} = f'(g(x)) \cdot g'(x)
:::

### Chain Rule for Exponential and Logarithmic Functions

#### The general exponential function rule

:::{math}
:enumerated: false
\frac{d}{d x} e^{g(x)} = e^{g(x)} g'(x)
:::

For example:

:::{math}
:enumerated: false
\frac{d}{d x} e^{ax} = \frac{d}{d (ax)} e^{ax} \frac{d}{d x} (ax) = e^{ax} a = ae^{ax}
:::

If we are using a base other than $e$:

:::{math}
:enumerated: false
\frac {d}{d x}(a^{g(x)}) = a^{g(x)} g'(x) \ln a, \text{ where } a > 0, a \neq 0
:::

#### The general natural logarithmic function rule

:::{math}
:enumerated: false
\frac{d}{d x} \ln(g(x)) = \frac{g'(x)}{g(x)}
:::

Interestingly:

:::{math}
:enumerated: false
\frac{d}{d x} \ln(ax) = \frac{d}{d(ax)} \ln(ax) \frac{d}{d x}(ax) = \frac{1}{ax} a = 1/x
:::

while

:::{math}
:enumerated: false
\frac{d}{d x} \ln(x^2) = \frac{d}{d(x^2)} \ln(x^2) \frac{d}{d x}(x^2) = \frac{1}{x^2} 2x = 2/x
:::

::::{dropdown} **Try these ^^**
**Exponential Functions**

Use the rules of differentiating exponential functions to find the derivative with respect to $x$ of each of the following functions.

1. $y = x^2 e^{5x}$

2. $y = \dfrac{e^{5x}-1}{e^{5x}+1}$

3. $y = a^{2x}$

4. $y = a^{5x^2}$

5. $y = 4^{2x+7}$

6. $y = x^3 2^x$
---
**Answers**

$1.\; y' = x e^{5x}(5x+2) \quad
2.\; y' = \frac{10e^{5x}}{(e^{5x}+1)^2} \quad
3.\; y' = 2a^{2x}\ln a \quad
4.\; y' = 10x\,a^{5x^2}\ln a \quad
5.\; y' = 2\ln(4)\,4^{2x+7} \quad
6.\; y' = x^2 2^x(x\ln 2 + 3)$

---
**Logarithmic Functions**

Use the rules of differentiating logarithms to find the derivative of each function.

1. $f(x)=x^{-4}+\ln(ax)$

2. $f(x)=4x^3\ln x^2$

3. $f(x)=\ln x-\ln(1+x)$

4. $f(x)=\ln\!\left(\dfrac{2x^2}{5x}\right)$

5. $f(x)=\log_2(6x)$

6. $f(x)=\log_4(9x^3)$
---
**Answers**

$1.\; f'(x)=-4x^{-5}+x^{-1} \quad
2.\; f'(x)=8x^2+24x^2\ln x \quad
3.\; f'(x)=\frac{1}{x(1+x)} \quad
4.\; f'(x)=\frac{1}{x} \quad
5.\; f'(x)=\frac{1}{x\ln 2} \quad
6.\; f'(x)=\frac{3}{x\ln 4}$

---
**Chain Rule**

Use the chain rule to find the derivative, $f'(x)$, of the following:

1. $f(x) = (x + 1)^3 + (x^2 - 2x)^2 - 5$

2. $f(x) = (2x + 4)^{99}$

3. $f(x) = (5x^2 + 10x + 3)^{20}$

4. $f(x) = (e^x)^{ab}$

5. $f(x) = (e^{x^a})^{b}$

6. $f(x) = (e^{a + bx + cx^2})^{10}$
---
**Answers**

$1.\; f'(x)=4x^3-9x^2+14x+3 \quad
2.\; f'(x)=198(2x+4)^{98} \quad
3.\; f'(x)=(200x+200)(5x^2+10x+3)^{19} \\[6pt]
4.\; f'(x)=ab\,e^{abx} \quad
5.\; f'(x)=ab\,x^{a-1}e^{bx^a} \quad
6.\; f'(x)=10(b+2cx)(e^{a+bx+cx^2})^{10}$

---
**Derivatives of Exponential and Logarithmic Functions**

**1. Exponential Rule with Base $a$**

**Problem:** Find the derivative of $f(x) = 5^{x^3 + 2x}$.

**Solution:**
Using the rule $\frac{d}{d x}(a^{g(x)}) = a^{g(x)} g'(x) \ln a$:
* Let $a = 5$
* Let $g(x) = x^3 + 2x$, so $g'(x) = 3x^2 + 2$

:::{math}
:enumerated: false
f'(x) = 5^{x^3 + 2x} \cdot (3x^2 + 2) \cdot \ln 5
:::

---
**General Natural Logarithmic Rule**

**Problem:** Find the derivative of $f(x) = \ln(\sin(x))$.

**Solution:**
Using the rule $\frac{d}{d x} \ln(g(x)) = \frac{g'(x)}{g(x)}$:
* Let $g(x) = \sin(x)$, so $g'(x) = \cos(x)$

:::{math}
:enumerated: false
f'(x) = \frac{\cos(x)}{\sin(x)} = \cot(x)
:::

---
**Logarithm with Base $b$**

**Problem:** Find the derivative of $f(x) = \log_{10}(x^2 + 1)$.

**Solution:**
Using the rule $\frac{d}{d x} \log_b g(x) = \frac{g'(x)}{g(x) \ln b}$:
* Let $b = 10$
* Let $g(x) = x^2 + 1$, so $g'(x) = 2x$

:::{math}
:enumerated: false
f'(x) = \frac{2x}{(x^2 + 1) \ln(10)}
:::

---
**Comparison of $\ln(ax)$ vs $\ln(x^n)$**

**Problem:** Differentiate $y = \ln(7x)$ and $y = \ln(x^7)$ to see the difference.

**Case A:** For $\ln(7x)$, the constant $a=7$ cancels out:
:::{math}
:enumerated: false
\frac{dy}{dx} = \frac{7}{7x} = \frac{1}{x}
:::

**Case B:** For $\ln(x^7)$, the power $n=7$ remains in the numerator:
:::{math}
:enumerated: false
\frac{dy}{dx} = \frac{7x^6}{x^7} = \frac{7}{x}
:::
::::

Note also when considered base other than $e$. Because

:::{math}
:enumerated: false
\log_b(x) = \frac{\ln(x)}{\ln(b)}
:::

we have

:::{math}
:enumerated: false
\frac{d}{d x} \log_b(x) = \frac{1}{x} \frac{1}{\ln(b)}
:::

Or more generally:

:::{math}
:enumerated: false
\begin{aligned} 
\frac{d}{d x} \log_b g(x) &= \frac{g'(x)}{g(x)} \frac{1}{\ln b}, \text{ where } b > 0, b \neq 1 \\ 
&= \frac{g'(x)}{g(x)} \log_b e 
\end{aligned}
:::

Note that $\log_b e = \displaystyle \frac{1}{\ln b}$.

---

## The Differential

Define $dx$ as an arbitrary change in $x$fro its initial value $x_0$ and $dy$ as teh resulting change in $y$ **along the tangent line** from the initial value of the function $y_0 = f(x_0)$. 

The **differential** of $y=f(x_0)$ evaluated at $x_0$ is

:::{math}
:enumerated: false
dy = f'(x_0)\, dx.
:::

This represents the change in $y$ along the tangent line at $x_0$. Graphically, we have:

<img src="figs/differential.png" alt="Differential" width="300"/>

::::{dropdown} **Try these ^^**
**Differentials**

Find the differential $dy$ for a given change in $x$, $dx$, for each function.

1. $y = 7x^2 - 3x + 5$

2. $y = 10x - \dfrac14 x^2$

3. $y = -x^2$

4. $y = x^3 + 3x - 6$
---
**Answers**

$1.\; dy = (14x - 3)\,dx \quad
2.\; dy = \left(10 - \tfrac12 x\right)dx \quad
3.\; dy = (-2x)\,dx \quad
4.\; dy = (3x^2 + 3)\,dx$
::::

## Taylor Series (Preview)

A smooth complex function $z(x)$ can be approximated around $x=a$ by

:::{math}
:enumerated: false
f(x)
=
z(a)
+ z'(a)(x-a)
+ \frac{1}{2}z''(a)(x-a)^2
+ \frac{1}{6}f'''(a)(x-a)^3
+ \cdots
:::

This idea underlies many approximation methods in economics.

<img src="figs/TaylorSeries.png" alt="Taylor Series" width="500"/>

The image provided illustrates a function $z(x)$ being approximated by three different Taylor polynomials (or Taylor series expansions) centered around the point $x=a$. 

The simplest approximation perhaps would simply be $g(x) = a$. This constant-valued function does not work well, especially if we move away from the point $a$.

A better approximation would be a linear function of the form $h(x) = z(a) + b(x-a)$, where $b$ is some slope. But what would be a good value of $b$? We saw above that the differential is an equation for the tangent line (or slope) at the point $x = a$. So, we could argue that the best **linear approximation** to the function around this point would be

:::{math}
:enumerated: false
h(x) = z(a) + z'(a)(x-a)
:::

where $z'(a)$ is the derivative of the function evaluated at $x=a$.

But why stop here? We could improve on this. A better approximation could allow for some curvature. The general form would then be, say,  $f(x) = z(a) + z'(a) .(x-a) + c.(x-a)^2$. Again, we ask, "What would be the best value for $c$?" The rate of change of the slope of the quadratic approximation should be equal to the rate of change of change of the function at the $a$. And since the second derivative of $z(x)$ is $2c$, then for $f''(x)$ to equal $z''(x)$ at $x = a$, we need $c = 1/2 z''(a)$. Hence the **quadratic approximation** to the function aound $x = a$ is:

:::{math}
:enumerated: false
f(x) = z(a) + z'(a)(x-a) + \frac{1}{2}f''(a)(x-a)^2
:::

Exteding the above argument for cubic and higher-degree approximations, we could find the $n$th-degree approximation to the function $z(x)$, which we could call $m(x)$, around the point $x = a$ is

:::{math}
:enumerated: false
m(x)
=
\frac{z(a)}{0!}
+ \frac{z'(a)}{1!}(x-a)
+ \frac{z''(a)}{2!}(x-a)^2
+ \cdots
+ \frac{f^{(n)}(a)}{n!}(x-a)^n
:::

where $f^{(n)}(a)$ is the $n$ the derivative of $z(x)$ evaluated at $x = a$. The function $m(x)$ above is called the **$n$-th degree Taylor expansion series** of $z(x)$ evaluated at $x=a$. 

To sum, $z(x)$ is the original function being approximated (the solid curve). $g(x)$ represents a constant function. $h(x)$ represents the first-order Taylor polynomial, i.e. a straight line that has the same value and slope as $z(x)$ at $x=a$ (or a tangent to $z(x)$ at $x=a$). The formula for $f(x)$ is $f(x) = z(a) + z^{\prime }(a)(x-a) + \frac{1}{2} z''(a)(x-a)^2$ representing a second-order (quadratic) polynomial-the dashed curve, which matches better the function's value, slope, and concavity (curvature) at $x=a$. It is a better approximation of $z(x)$ near $x=a$ than the linear approximation $h(x)$ and of course the constant function $g(a)$. The graph demonstrates that as more terms are included in the Taylor polynomial, the approximation of the original function becomes more accurate over a larger range around the center point $x=a$. 

## Implicit Differentiation

## Inverse Function Rule for Implicit Functions

## Some Uses of Differentiation in Economics


