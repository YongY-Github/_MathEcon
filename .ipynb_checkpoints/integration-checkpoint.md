# 9. Integration

In mathematics for economists, we often need to move from marginal values (slopes) back to total values. 

Reversing the process of differentiation to find the original function from its derivative is called **integration** or **reverse differentiation**.

The original function $F(x)$ is called the **integral** or **antiderivative** of $f'(x)$. 

Symbolically:

$$\int f(x)dx = F(x) + c$$

This chapter covers:

1. Basic rules of integration
2. Integration by substitution
3. Integration by parts
4. Definite integrals and the Fundamental Theorem of Calculus
5. Economic applications

---

## Rules of Integration

1. The integral of a constant $k$ is:

:::{math}
:enumerated: false
\int kdx = kx + c
:::

2. The integral of 1, written simply as $dx$, not $1 dx$, is:

:::{math}
:enumerated: false
\int dx = x + c
:::

3. The integral of a power function $x^n$, where $n \neq -1$, is given by the power rule:

:::{math}
:enumerated: false
\int x^n dx = \frac{1}{n+1}x^{n+1} + c
:::

4. The integral of $x^{-1}$ (or $1/x$) is:

:::{math}
:enumerated: false
\int x^{-1} dx = \ln x + c \quad (x > 0)
:::

The condition $x > 0$ is added because only positive numbers have logarithms. For negative numbers,

:::{math}
:enumerated: false
\int x^{-1} dx = \ln|x| + c \quad (x \neq 0)
:::

A little thought informs us that:

:::{math}
:enumerated: false
\begin{align}
\int \frac{f'(x)}{f(x)} \, dx &= \ln f(x) + C \quad \text{for } f(x) > 0 \\
&= \ln |f(x)| + C \quad \text{for } f(x) \neq 0
\end{align}
:::

5. The integral of a exponential function is

:::{math}
:enumerated: false
\int a^{kx} dx = \frac{a^{kx}}{k \ln x} + c
:::

6. The integral of a natural exponential function is

:::{math}
:enumerated: false
\int e^{kx} dx = \frac{e^{kx}}{k} + c
:::

From our knowledge of differentiation of exponential functions, it goes without saying that

:::{math}
:enumerated: false
\int e^x dx = e^x + c
:::

And with a little thought, we have

:::{math}
:enumerated: false
\int f'(x)e^{f(x)} dx = e^{f(x)} + c
:::


7. The integral of a constant times a function equals the constant times the integral of the function:

:::{math}
:enumerated: false
\int kf(x) dx = k \int f(x) dx
:::

8. The integral of the sum or difference of two or more functions equals the sum or difference of their integrals:

:::{math}
:enumerated: false
\int [f(x) \pm g(x)] dx = \int f(x) dx \pm \int g(x) dx
:::

9. The integral of the negative of a function equals the negative of the integral of that function:

:::{math}
:enumerated: false
\int -f(x) dx = -\int f(x) dx
:::

---

## Integration by Substitution

Integration by substitution is often useful to integrate more complex forms.

$$
\int f(g(x))g'(x) dx = \int f(u) du \quad \text{where } u = g(x)
$$

**Example:**

Say you want to find:

:::{math}
:enumerated: false
\int (x^2 + 4)^3 2x dx
:::

The "trick" is to notice that if $u = g(x) = x^2 + 4$, then $g'(x) = 2x$.

So we can write:

:::{math}
:enumerated: false
\int (x^2 + 4)^3 2x dx &= \int u^3 du \quad \text{since } du = 2x dx \\
&= \frac{u^4}{4} + c = \frac{(x^2 + 4)^4}{4} + c
:::

A slightly more **difficult example:**

Find $\int xe^{-kx^2} dx$.

Let $u = -kx^2$, then $du = -2kx dx$.

Hence, $x dx = -\frac{du}{2k}$, implying:

:::{math}
:enumerated: false
\int xe^{-kx^2} dx = \int -\frac{1}{2k} e^u du = -\frac{1}{2k} e^u + c = -\frac{1}{2k} e^{-kx^2} + c
:::

### Generalized Rules from Substitution

**Generalized Power Rule ($n \neq -1$):**

:::{math}
:enumerated: false
\int [f(x)]^n f'(x) dx = \frac{[f(x)]^{n+1}}{n+1} + c
:::

*Example 1:* 
:::{math}
:enumerated: false
\int (x+1)^2 dx = \frac{(x+1)^3}{3} + c
:::

*Example 2:* 

:::{math}
:enumerated: false
\int (2x+1)^2 dx = \frac{1}{2} \int (2x+1)^2 2 dx = \frac{(2x+1)^3}{6} + c
:::

**Generalized Log Rule:**

:::{math}
:enumerated: false
\int \frac{f'(x)}{f(x)} dx = \ln|f(x)| + c
:::

*Example 1:*
:::{math}
:enumerated: false
\int \frac{2}{x} dx = 2 \ln(x) + c \quad (x > 0)
:::

*Example 2:*
:::{math}
:enumerated: false
\int \frac{x}{(4x^2 + 1)} dx = \frac{1}{8} \int \frac{8x}{(4x^2 + 1)} dx = \frac{1}{8} \ln(4x^2 + 1) + c
:::

**Generalized Exponential Rule:**

:::{math}
:enumerated: false
\int A e^{f(x)} f'(x) dx = A e^{f(x)} + c
:::

*Example:*
:::{math}
:enumerated: false
\int x e^{x^2} dx = \frac{1}{2} e^{x^2} + c
:::

---

## Integration by Parts

The product rule is:

:::{math}
:enumerated: false
\frac{d}{dx}(f(x)g(x)) = f'(x)g(x) + f(x)g'(x)
:::

Taking the indefinite integral of each side gives:

:::{math}
:enumerated: false
f(x)g(x) = \int f'(x)g(x) dx + \int f(x)g'(x) dx
:::

Rearranging gives the formula for **integration by parts**:

$$\int f(x)g'(x) dx = f(x)g(x) - \int f'(x)g(x) dx$$

*Example 1:*

:::{math}
:enumerated: false
\int x e^x dx = x e^x - \int 1 \cdot e^x dx = x e^x - e^x + c
:::

*Example 2:*

:::{math}
:enumerated: false
\int x \ln x dx &= (\ln x)\frac{x^2}{2} - \int \frac{1}{x} \frac{x^2}{2} dx \\
&= \frac{x^2}{2} \ln x - \int \frac{x}{2} dx \\
&= \frac{x^2}{2} \ln x - \frac{x^2}{4} + c 
:::

## Definite Integrals and The Fundamental Theorem of Calculus

The definite integral of $f(x)$ over the interval $a$ to $b$ ($a < x < b$) is written as:

:::{math}
:enumerated: false
\int_{a}^{b} f(x) dx
:::

The **Fundamental Theorem of Calculus** states that the numerical value of the definite integral of a continuous function $f(x)$ over the interval from $a$ to $b$ is given by the indefinite integral $F(x) + c$ evaluated at the upper limit $b$, minus the same evaluated at the lower limit $a$.

Since the constant $c$ is common to both, it is eliminated in subtraction:

$$\int_{a}^{b} f(x) dx = F(x) \Big|_{a}^{b} = F(b) - F(a)$$

**Example:**

:::{math}
:enumerated: false
\int_{1}^{3} (4x^3 + 6x) dx &= (x^4 + 3x^2) \Big|_{1}^{3} \\
&= [ (3^4) + 3(3^2) ] - [ (1^4) + 3(1^2) ] \\
&= 108 - 4 = 104
:::

This represents the **area under the curve** $f(x) = 4x^3 + 6x$ between $x=1$ and $x=3$.

### Improper Integrals

A definite integral with infinity for either an upper or lower limit is known as an **improper integral**:

:::{math}
:enumerated: false
\int_{a}^{\infty} f(x) dx
:::

and

:::{math}
:enumerated: false
\int_{-\infty}^{b} f(x) dx
:::


### Properties of Definite Integrals

1.
:::{math}
:enumerated: false
\int_{a}^{b} f(x) dx = -\int_{b}^{a} f(x) dx
:::

2.
:::{math}
:enumerated: false
\int_{a}^{a} f(x) dx = F(a) - F(a) = 0
:::

4. 
:::{math}
:enumerated: false
\int_{a}^{c} f(x) dx = \int_{a}^{b} f(x) dx + \int_{b}^{c} f(x) dx
:::

5.
:::{math}
:enumerated: false
\int_{a}^{b} f(x) dx \pm \int_{a}^{b} g(x) dx = \int_{a}^{b} [f(x) \pm g(x)] dx
:::

6.
:::{math}
:enumerated: false
\int_{a}^{b} kf(x) dx = k \int_{a}^{b} f(x) dx
:::

---

## Economic Applications of Integral Calculus

* **Area between curves:** Used to calculate Producer and Consumer Surplus.
* **Finding paths:** Finding the capital path $K(t)$ from investment $I(t)$; finding Total Cost (TC) from Marginal Cost (MC), etc.
