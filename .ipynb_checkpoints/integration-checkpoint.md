# Integration

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

::::{dropdown} **Try these ^^**

Determine the following integrals. You should also check your answers by finding the derivative of the integral that you find.

i. $\int -\frac{1}{2}x dx$

ii. $\int 4x^3 dx$

iii. $\int 4x^{-2} dx$

iv. $\int x^{-5/2} dx$

v. $\int 5x^{-1} dx$

vi. $\int \frac{1}{3x} dx$

vii. $\int \frac{dx}{\sqrt[3]{x}}$

viii. $\int 2^{4x} dx$

ix. $\int 8^x dx$

x. $\int e^{5x} dx$

xi. $\int 16e^{-4x} dx$

xii. $\int (6e^{3x} - 8e^{-2x}) dx$


2. Find the integral for $y = \int(x^{1/2} + 3x^{-1/2})dx$, given the initial condition $y = 0$ when $x = 0$.

   **answer:** $y = \frac{2}{3}x^{3/2} + 6x^{1/2}$

3. Find the integral for $y = \int(2x^5 - 3x^{-1/4})dx$, given the initial condition $y = 6$ when $x = 0$.

   **answer:** $y = \frac{1}{3}x^6 - 4x^{3/4} + 6$

4. Find the integral for $y = \int(10x^4 - 3)dx$, given the boundary condition $y = 21$ when $x = 1$.

   **answer:** $y = 2x^5 - 3x + 22$

---

### Solutions to Exercises

**i. $\int -\frac{1}{2}x \, dx$**
* **Step:** Apply the power rule: $\int x^n dx = \frac{1}{n+1}x^{n+1} + c$.
* **Solution:** $-\frac{1}{2} \cdot \frac{x^2}{2} + c = -\frac{1}{4}x^2 + c$
* **Check:** $\frac{d}{dx}(-\frac{1}{4}x^2 + c) = -\frac{1}{4}(2x) = -\frac{1}{2}x$

**ii. $\int 4x^3 \, dx$**
* **Step:** Factor out the constant and apply the power rule.
* **Solution:** $4 \cdot \frac{x^4}{4} + c = x^4 + c$
* **Check:** $\frac{d}{dx}(x^4 + c) = 4x^3$

**iii. $\int 4x^{-2} \, dx$**
* **Step:** Apply the power rule for $n = -2$.
* **Solution:** $4 \cdot \frac{x^{-1}}{-1} + c = -4x^{-1} + c = -\frac{4}{x} + c$
* **Check:** $\frac{d}{dx}(-4x^{-1} + c) = -4(-1)x^{-2} = 4x^{-2}$

**iv. $\int x^{-5/2} \, dx$**
* **Step:** Apply the power rule: $n+1 = -5/2 + 2/2 = -3/2$.
* **Solution:** $\frac{x^{-3/2}}{-3/2} + c = -\frac{2}{3}x^{-3/2} + c$
* **Check:** $\frac{d}{dx}(-\frac{2}{3}x^{-3/2} + c) = -\frac{2}{3}(-\frac{3}{2})x^{-5/2} = x^{-5/2}$

**v. $\int 5x^{-1} \, dx$**
* **Step:** Apply the log rule: $\int x^{-1} dx = \ln|x| + c$.
* **Solution:** $5 \ln|x| + c$
* **Check:** $\frac{d}{dx}(5 \ln|x| + c) = 5 \cdot \frac{1}{x} = 5x^{-1}$

**vi. $\int \frac{1}{3x} \, dx$**
* **Step:** Factor out $1/3$ and apply the log rule.
* **Solution:** $\frac{1}{3} \int \frac{1}{x} \, dx = \frac{1}{3} \ln|x| + c$
* **Check:** $\frac{d}{dx}(\frac{1}{3} \ln|x| + c) = \frac{1}{3} \cdot \frac{1}{x} = \frac{1}{3x}$

**vii. $\int \frac{dx}{\sqrt[3]{x}}$**
* **Step:** Rewrite as a power: $x^{-1/3}$, then apply the power rule ($n+1 = 2/3$).
* **Solution:** $\int x^{-1/3} \, dx = \frac{x^{2/3}}{2/3} + c = \frac{3}{2}x^{2/3} + c$
* **Check:** $\frac{d}{dx}(\frac{3}{2}x^{2/3} + c) = \frac{3}{2}(\frac{2}{3})x^{-1/3} = x^{-1/3} = \frac{1}{\sqrt[3]{x}}$

**viii. $\int 2^{4x} \, dx$**
* **Step:** Apply the general exponential rule: $\int a^{kx} dx = \frac{a^{kx}}{k \ln a} + c$.
* **Solution:** $\frac{2^{4x}}{4 \ln 2} + c$
* **Check:** $\frac{d}{dx}(\frac{2^{4x}}{4 \ln 2} + c) = \frac{1}{4 \ln 2} \cdot 2^{4x} \cdot \ln 2 \cdot 4 = 2^{4x}$

**ix. $\int 8^x \, dx$**
* **Step:** Apply the exponential rule where $k=1$.
* **Solution:** $\frac{8^x}{\ln 8} + c$
* **Check:** $\frac{d}{dx}(\frac{8^x}{\ln 8} + c) = \frac{1}{\ln 8} \cdot 8^x \cdot \ln 8 = 8^x$

**x. $\int e^{5x} \, dx$**
* **Step:** Apply the natural exponential rule: $\int e^{kx} dx = \frac{e^{kx}}{k} + c$.
* **Solution:** $\frac{1}{5}e^{5x} + c$
* **Check:** $\frac{d}{dx}(\frac{1}{5}e^{5x} + c) = \frac{1}{5} \cdot e^{5x} \cdot 5 = e^{5x}$

**xi. $\int 16e^{-4x} \, dx$**
* **Step:** Factor out 16 and apply the natural exponential rule.
* **Solution:** $16 \cdot \frac{e^{-4x}}{-4} + c = -4e^{-4x} + c$
* **Check:** $\frac{d}{dx}(-4e^{-4x} + c) = -4 \cdot e^{-4x} \cdot (-4) = 16e^{-4x}$

**xii. $\int (6e^{3x} - 8e^{-2x}) \, dx$**
* **Step:** Apply the sum/difference rule and integrate each term individually.
* **Solution:** $6 \cdot \frac{e^{3x}}{3} - 8 \cdot \frac{e^{-2x}}{-2} + c = 2e^{3x} + 4e^{-2x} + c$
* **Check:** $\frac{d}{dx}(2e^{3x} + 4e^{-2x} + c) = 2(3)e^{3x} + 4(-2)e^{-2x} = 6e^{3x} - 8e^{-2x}$
::::


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

::::{dropdown} **Try these ^^**

Determine the following integrals, using the substitution method. Check your answers.

i. $\int 10x(x^2 + 3)^4 dx$

ii. $\int x^4(2x^5 - 5)^4 dx$

iii. $\int (x - 9)^{7/4} dx$

iv. $\int (6x - 11)^{-5} dx$

v. $\int \frac{x^2}{(4x^3 + 7)^2} dx$

vi. $\int \frac{6x^2 + 4x + 10}{(x^3 + x^2 + 5x)^3} dx$

vii. $\int \frac{dx}{(9x - 5)}$

viii. $\int \frac{3x^2 + 2}{4x^3 + 8x} dx$

ix. $\int x^3 e^{x^4} dx$

x. $\int 24x e^{3x^2} dx$

xi. $\int 14 e^{2x+7} dx$

xii. $\int 5x e^{5x^2+3} dx$

---

### Solutions to Substitution Exercises

**i. $\int 10x(x^2 + 3)^4 dx$**
* **Step:** Let $u = x^2 + 3$, then $du = 2x \, dx$, so $10x \, dx = 5 \, du$.
* **Solution:** $\int 5u^4 du = u^5 + c = (x^2 + 3)^5 + c$
* **Check:** $\frac{d}{dx}[(x^2 + 3)^5 + c] = 5(x^2 + 3)^4(2x) = 10x(x^2 + 3)^4$

**ii. $\int x^4(2x^5 - 5)^4 dx$**
* **Step:** Let $u = 2x^5 - 5$, then $du = 10x^4 \, dx$, so $x^4 \, dx = \frac{1}{10} \, du$.
* **Solution:** $\int \frac{1}{10}u^4 du = \frac{1}{50}u^5 + c = \frac{1}{50}(2x^5 - 5)^5 + c$
* **Check:** $\frac{d}{dx}[\frac{1}{50}(2x^5 - 5)^5 + c] = \frac{5}{50}(2x^5 - 5)^4(10x^4) = x^4(2x^5 - 5)^4$

**iii. $\int (x - 9)^{7/4} dx$**
* **Step:** Let $u = x - 9$, then $du = dx$.
* **Solution:** $\int u^{7/4} du = \frac{u^{11/4}}{11/4} + c = \frac{4}{11}(x - 9)^{11/4} + c$
* **Check:** $\frac{d}{dx}[\frac{4}{11}(x - 9)^{11/4} + c] = \frac{4}{11} \cdot \frac{11}{4}(x - 9)^{7/4} = (x - 9)^{7/4}$

**iv. $\int (6x - 11)^{-5} dx$**
* **Step:** Let $u = 6x - 11$, then $du = 6 \, dx$, so $dx = \frac{1}{6} \, du$.
* **Solution:** $\int \frac{1}{6}u^{-5} du = \frac{1}{6}(\frac{u^{-4}}{-4}) + c = -\frac{1}{24}(6x - 11)^{-4} + c$
* **Check:** $\frac{d}{dx}[-\frac{1}{24}(6x - 11)^{-4} + c] = -\frac{1}{24}(-4)(6x - 11)^{-5}(6) = (6x - 11)^{-5}$

**v. $\int \frac{x^2}{(4x^3 + 7)^2} dx$**
* **Step:** Let $u = 4x^3 + 7$, then $du = 12x^2 \, dx$, so $x^2 \, dx = \frac{1}{12} \, du$.
* **Solution:** $\int \frac{1}{12}u^{-2} du = \frac{1}{12}(\frac{u^{-1}}{-1}) + c = -\frac{1}{12(4x^3 + 7)} + c$
* **Check:** $\frac{d}{dx}[-\frac{1}{12}(4x^3 + 7)^{-1} + c] = -\frac{1}{12}(-1)(4x^3 + 7)^{-2}(12x^2) = \frac{x^2}{(4x^3 + 7)^2}$

**vi. $\int \frac{6x^2 + 4x + 10}{(x^3 + x^2 + 5x)^3} dx$**
* **Step:** Let $u = x^3 + x^2 + 5x$, then $du = (3x^2 + 2x + 5) \, dx$. Note the numerator is $2(3x^2 + 2x + 5)$.
* **Solution:** $\int 2u^{-3} du = \frac{2u^{-2}}{-2} + c = -(x^3 + x^2 + 5x)^{-2} + c = -\frac{1}{(x^3 + x^2 + 5x)^2} + c$
* **Check:** $\frac{d}{dx}[-(x^3 + x^2 + 5x)^{-2} + c] = -(-2)(x^3 + x^2 + 5x)^{-3}(3x^2 + 2x + 5) = \frac{6x^2 + 4x + 10}{(x^3 + x^2 + 5x)^3}$

**vii. $\int \frac{dx}{(9x - 5)}$**
* **Step:** Let $u = 9x - 5$, then $du = 9 \, dx$, so $dx = \frac{1}{9} \, du$.
* **Solution:** $\int \frac{1}{9} \frac{1}{u} du = \frac{1}{9} \ln|9x - 5| + c$
* **Check:** $\frac{d}{dx}[\frac{1}{9} \ln|9x - 5| + c] = \frac{1}{9} \cdot \frac{1}{9x - 5} \cdot 9 = \frac{1}{9x - 5}$

**viii. $\int \frac{3x^2 + 2}{4x^3 + 8x} dx$**
* **Step:** Let $u = 4x^3 + 8x$, then $du = (12x^2 + 8) \, dx = 4(3x^2 + 2) \, dx$.
* **Solution:** $\int \frac{1}{4} \frac{1}{u} du = \frac{1}{4} \ln|4x^3 + 8x| + c$
* **Check:** $\frac{d}{dx}[\frac{1}{4} \ln|4x^3 + 8x| + c] = \frac{1}{4} \cdot \frac{12x^2 + 8}{4x^3 + 8x} = \frac{3x^2 + 2}{4x^3 + 8x}$

**ix. $\int x^3 e^{x^4} dx$**
* **Step:** Let $u = x^4$, then $du = 4x^3 \, dx$, so $x^3 \, dx = \frac{1}{4} \, du$.
* **Solution:** $\int \frac{1}{4} e^u du = \frac{1}{4} e^{x^4} + c$
* **Check:** $\frac{d}{dx}[\frac{1}{4} e^{x^4} + c] = \frac{1}{4} e^{x^4}(4x^3) = x^3 e^{x^4}$

**x. $\int 24x e^{3x^2} dx$**
* **Step:** Let $u = 3x^2$, then $du = 6x \, dx$, so $24x \, dx = 4 \, du$.
* **Solution:** $\int 4e^u du = 4e^{3x^2} + c$
* **Check:** $\frac{d}{dx}[4e^{3x^2} + c] = 4e^{3x^2}(6x) = 24x e^{3x^2}$

**xi. $\int 14 e^{2x+7} dx$**
* **Step:** Let $u = 2x + 7$, then $du = 2 \, dx$, so $14 \, dx = 7 \, du$.
* **Solution:** $\int 7e^u du = 7e^{2x+7} + c$
* **Check:** $\frac{d}{dx}[7e^{2x+7} + c] = 7e^{2x+7}(2) = 14 e^{2x+7}$

**xii. $\int 5x e^{5x^2+3} dx$**
* **Step:** Let $u = 5x^2 + 3$, then $du = 10x \, dx$, so $5x \, dx = \frac{1}{2} \, du$.
* **Solution:** $\int \frac{1}{2} e^u du = \frac{1}{2} e^{5x^2+3} + c$
* **Check:** $\frac{d}{dx}[\frac{1}{2} e^{5x^2+3} + c] = \frac{1}{2} e^{5x^2+3}(10x) = 5x e^{5x^2+3}$

::::

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

---

::: {dropdown} **Try these ^^**

6. Use integration by parts to evaluate the following integrals. Check your answers.

i. $\int 15x(x+4)^{3/2} dx$

ii. $\int \frac{2x}{(x - 8)^3} dx$

iii. $\int \frac{5x}{(x - 1)^2} dx$

iv. $\int 6x e^{x+7} dx$

v. $\int 16x e^{-(x+9)} dx$

vi. $\int x^2 e^{2x} dx$

###  Here are the step-by-step solutions for the **Integration by Parts** exercises.

These solutions use the formula $\int u \, dv = uv - \int v \, du$.

**i. $\int 15x(x+4)^{3/2} dx$**
* **Step:** Let $u = 15x \Rightarrow du = 15 \, dx$. Let $dv = (x+4)^{3/2} dx \Rightarrow v = \frac{2}{5}(x+4)^{5/2}$.
* **Solution:** $15x \cdot \frac{2}{5}(x+4)^{5/2} - \int \frac{2}{5}(x+4)^{5/2} \cdot 15 \, dx = 6x(x+4)^{5/2} - 6 \int (x+4)^{5/2} dx$
* **Final:** $6x(x+4)^{5/2} - \frac{12}{7}(x+4)^{7/2} + c$
* **Check:** $\frac{d}{dx}$ yields $6(x+4)^{5/2} + 15x(x+4)^{3/2} - 6(x+4)^{5/2} = 15x(x+4)^{3/2}$.

**ii. $\int \frac{2x}{(x - 8)^3} dx$**
* **Step:** Let $u = 2x \Rightarrow du = 2 \, dx$. Let $dv = (x-8)^{-3} dx \Rightarrow v = -\frac{1}{2}(x-8)^{-2}$.
* **Solution:** $2x [-\frac{1}{2}(x-8)^{-2}] - \int -\frac{1}{2}(x-8)^{-2} \cdot 2 \, dx = -x(x-8)^{-2} + \int (x-8)^{-2} dx$
* **Final:** $-\frac{x}{(x-8)^2} - \frac{1}{x-8} + c$ (Simplified: $-\frac{2x-8}{(x-8)^2} + c$)
* **Check:** Differentiating the simplified form returns $\frac{2x}{(x-8)^3}$.

**iii. $\int \frac{5x}{(x - 1)^2} dx$**
* **Step:** Let $u = 5x \Rightarrow du = 5 \, dx$. Let $dv = (x-1)^{-2} dx \Rightarrow v = -(x-1)^{-1}$.
* **Solution:** $-5x(x-1)^{-1} - \int -5(x-1)^{-1} dx = -\frac{5x}{x-1} + 5 \ln|x-1| + c$
* **Check:** $\frac{d}{dx}[-\frac{5x}{x-1} + 5 \ln|x-1|] = \frac{-5(x-1) - (-5x)}{(x-1)^2} + \frac{5}{x-1} = \frac{5}{(x-1)^2} + \frac{5(x-1)}{(x-1)^2} = \frac{5x}{(x-1)^2}$.

**iv. $\int 6x e^{x+7} dx$**
* **Step:** Let $u = 6x \Rightarrow du = 6 \, dx$. Let $dv = e^{x+7} dx \Rightarrow v = e^{x+7}$.
* **Solution:** $6x e^{x+7} - \int 6 e^{x+7} dx = 6x e^{x+7} - 6e^{x+7} + c$
* **Final:** $6e^{x+7}(x - 1) + c$
* **Check:** $\frac{d}{dx}[6x e^{x+7} - 6e^{x+7}] = 6e^{x+7} + 6x e^{x+7} - 6e^{x+7} = 6x e^{x+7}$.

**v. $\int 16x e^{-(x+9)} dx$**
* **Step:** Let $u = 16x \Rightarrow du = 16 \, dx$. Let $dv = e^{-(x+9)} dx \Rightarrow v = -e^{-(x+9)}$.
* **Solution:** $-16x e^{-(x+9)} - \int -16 e^{-(x+9)} dx = -16x e^{-(x+9)} - 16e^{-(x+9)} + c$
* **Final:** $-16e^{-(x+9)}(x + 1) + c$
* **Check:** $\frac{d}{dx}[-16x e^{-(x+9)} - 16e^{-(x+9)}] = -16e^{-(x+9)} + 16xe^{-(x+9)} + 16e^{-(x+9)} = 16x e^{-(x+9)}$.

**vi. $\int x^2 e^{2x} dx$**
* **Step 1:** Let $u = x^2 \Rightarrow du = 2x \, dx$. Let $dv = e^{2x} dx \Rightarrow v = \frac{1}{2}e^{2x}$.
* **Apply Parts 1:** $\frac{1}{2}x^2 e^{2x} - \int x e^{2x} dx$
* **Step 2:** Integrate $\int x e^{2x} dx$ by parts again. Let $u = x \Rightarrow du = dx$. Let $dv = e^{2x} dx \Rightarrow v = \frac{1}{2}e^{2x}$.
* **Apply Parts 2:** $\int x e^{2x} dx = \frac{1}{2}xe^{2x} - \int \frac{1}{2}e^{2x} dx = \frac{1}{2}xe^{2x} - \frac{1}{4}e^{2x}$
* **Final Solution:** $\frac{1}{2}x^2 e^{2x} - (\frac{1}{2}xe^{2x} - \frac{1}{4}e^{2x}) + c = e^{2x}(\frac{1}{2}x^2 - \frac{1}{2}x + \frac{1}{4}) + c$
* **Check:** Differentiating via product rule returns $x^2 e^{2x}$.

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


::: {dropdown} **Try these ^^**

1. The rate of net investment is $I = 40t^{3/5}$, and the capital stock at $t = 0$ is $75$. Find the capital function $K$.

   **answer:** $K = 25t^{8/5} + 75$

2. Marginal cost given by $\text{MC} = d\text{TC}/dQ = 25 + 30Q - 9Q^2$. Fixed cost is $55$. Find (i) total cost, (ii) average cost, and (iii) variable cost functions.

   **answers:** (i) $\text{TC} = 25Q + 15Q^2 - 3Q^3 + 55$
   (ii) $\text{AC} = \frac{\text{TC}}{Q} = 25 + 15Q - 3Q^2 + \frac{55}{Q}$
   (iii) $\text{VC} = \text{TC} - \text{FC} = 25Q + 15Q^2 - 3Q^3$

3. Marginal revenue is given by $\text{MR} = d\text{TR}/dQ = 60 - 2Q - 2Q^2$.
   Find (i) the TR function and (ii) the demand function $P = f(Q)$.

   **answers:** (i) $\text{TR} = 60Q - Q^2 - \frac{2}{3}Q^3$
   (ii) $P = \text{AR} = \text{TR}/Q = 60 - Q - \frac{2}{3}Q^2$

4. Given $\text{MC} = 16e^{0.4Q}$ and $\text{FC} = 100$, find $\text{TC}$.

    **answer:** $\text{TC} = 40e^{0.4Q} + 60$

### Step-by-step Solutions

**1. Find Capital Function $K(t)$ given $I = 40t^{3/5}$ and $K(0) = 75$**
* **Step 1 (Integrate):** $K(t) = \int 40t^{3/5} dt = 40 \left( \frac{t^{8/5}}{8/5} \right) + c = 40 \left( \frac{5}{8} \right) t^{8/5} + c = 25t^{8/5} + c$.
* **Step 2 (Find $c$):** Use initial condition $K(0) = 75$. $25(0)^{8/5} + c = 75 \Rightarrow c = 75$.
* **Final:** $K = 25t^{8/5} + 75$.

**2. Find Costs given $\text{MC} = 25 + 30Q - 9Q^2$ and $\text{FC} = 55$**
* **Total Cost (TC):** $\int (25 + 30Q - 9Q^2) dQ = 25Q + 15Q^2 - 3Q^3 + c$. Since $\text{TC}(0) = \text{FC} = 55$, then $c = 55$.
    * $\text{TC} = 25Q + 15Q^2 - 3Q^3 + 55$.
* **Average Cost (AC):** $\text{AC} = \frac{\text{TC}}{Q} = \frac{25Q + 15Q^2 - 3Q^3 + 55}{Q}$.
    * $\text{AC} = 25 + 15Q - 3Q^2 + \frac{55}{Q}$.
* **Variable Cost (VC):** $\text{VC} = \text{TC} - \text{FC}$.
    * $\text{VC} = 25Q + 15Q^2 - 3Q^3$.

**3. Find TR and Demand given $\text{MR} = 60 - 2Q - 2Q^2$**
* **Total Revenue (TR):** $\int (60 - 2Q - 2Q^2) dQ = 60Q - Q^2 - \frac{2}{3}Q^3 + c$. Since $\text{TR} = 0$ when $Q = 0$, $c = 0$.
    * $\text{TR} = 60Q - Q^2 - \frac{2}{3}Q^3$.
* **Demand Function (P):** $P = \text{Average Revenue} = \frac{\text{TR}}{Q}$.
    * $P = 60 - Q - \frac{2}{3}Q^2$.

**4. Find TC given $\text{MC} = 16e^{0.4Q}$ and $\text{FC} = 100$**
* **Step 1 (Integrate):** $\text{TC} = \int 16e^{0.4Q} dQ = \frac{16}{0.4}e^{0.4Q} + c = 40e^{0.4Q} + c$.
* **Step 2 (Find $c$):** Set $\text{TC}(0) = 100$. $40e^{0.4(0)} + c = 100 \Rightarrow 40(1) + c = 100 \Rightarrow c = 60$.
* **Final:** $\text{TC} = 40e^{0.4Q} + 60$.
:::
