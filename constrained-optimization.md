# Constrained Optimization

In economics, most optimization problems involve **scarcity**. We want to maximize something (utility, profit, output), but we face constraints (budget, technology, time, policy).

This chapter develops the tools to solve such problems.

We proceed in three stages:

1. Equality constraints (substitution → Lagrangian)
2. Multiple constraints and bordered Hessian
3. Inequality constraints (Kuhn–Tucker conditions)

---

## I — Equality Constraints

### 8.1 The Economic Logic

::::{admonition} Big Idea
:class: important
A constrained optimum occurs where the objective function is as high (or low) as possible **without violating the constraint**.
::::

Think geometrically:

* The objective function gives **indifference curves**
* The constraint gives a **feasible set**
* The optimum occurs where the highest attainable indifference curve touches the constraint

Mathematically, this corresponds to:

* Equal slopes (tangency)
* Constraint satisfied exactly

---

### 8.2 Solving by Substitution

Suppose we maximize

(eq:objective_func)=
$$
f(x_1, x_2) = 2\sqrt{x_1} + \frac{1}{2}\sqrt{x_2}
$$ 

subject to

(eq:constraint)=
$$
4x_1 + x_2 = 20.
$$

---

#### Step 1: Rewrite the Constraint

:::{math}
:enumerated: false
x_2 = 20 - 4x_1.
:::

#### Step 2: Substitute into Objective

:::{math}
:enumerated: false
f(x_1) = 2\sqrt{x_1} + \frac{1}{2}\sqrt{20 - 4x_1}.
:::

Now this is a **single-variable problem**.

#### Step 3: First-Order Condition

:::{math}
:enumerated: false
f'(x_1) = \frac{1}{\sqrt{x_1}} - \frac{1}{\sqrt{20 - 4x_1}} = 0.
:::

Solve:

:::{math}
:enumerated: false
x_1^* = 4.
:::

Then

:::{math}
:enumerated: false
x_2^* = 4.
:::

#### Step 4: Second-Order Condition

:::{math}
:enumerated: false
f''(x_1)
=
-\frac{1}{2} x_1^{-3/2}
=
2(20 - 4x_1)^{-3/2}.
:::

Evaluated at $x_1 = 4$:

:::{math}
:enumerated: false
-\frac{5}{16} < 0.
:::

**Conclusion:** The stationary point is a maximum.

Objective value:

:::{math}
:enumerated: false
2\sqrt{4} + \frac{1}{2}\sqrt{4} = 5.
:::

---

::::{dropdown} **Try these ^^**

**Constrained Optimization and Second-Order Conditions**

Using the substitution method, solve each constrained optimization problem. Determine the optimal values and use the second-order condition to verify whether you have a maximum or a minimum.

**(i)** $f(x,y) = x^2 + 2xy + 4y^2$ subject to $x + y = 8$

**(ii)** $f(x,y) = 3x^2 + y^2 - 2xy$ subject to $x + y = 1$

**(iii)** $f(x,y) = 10x + 40y$ subject to $x^{1/2}y^{1/2} = 2$

**(iv)** $f(x,y) = \ln x + 2\ln y$ subject to $y = 16 - 4x$

**(v)** $f(x,y) = 2x^{1/2}y^{1/2}$ subject to $x + y = 1$

**(vi)** $f(x,y) = 2x^2 - 4xy + 9y^2 - 8y + 36$ subject to $x + y = 12$

**(vii)** $f(x,y,z) = 2x^2 + 5xy - y^2 - 3xz$ subject to $x + y + z = 14$

---

**Answers**

**(i)** $(x, y) = (8, 0)$, minimum  
**(ii)** $(x, y) = \left(\frac{1}{3}, \frac{2}{3}\right)$, minimum  
**(iii)** $(x, y) = (4, 1)$, minimum  
**(iv)** $(x, y) = \left(\frac{4}{3}, \frac{32}{3}\right)$, maximum  
**(v)** $(x, y) = \left(\frac{1}{2}, \frac{1}{2}\right)$, maximum  
**(vi)** [Solution omitted in original, usually solved as $(x,y) = (8, 4)$ minimum]  
**(vii)** $(x, y, z) = (1, 4, 9)$, a saddle point

::::

---

#### Limitation of Substitution

::::{admonition} Why This Method Is Limited
:class: important

Substitution works only when:
- The constraint can be solved explicitly
- There is only one constraint
- The algebra remains manageable
::::

We now introduce a more powerful method.

---

## II — Lagrange Multiplier Method

An alternative to the substitution method is the Lagrange multiplier method. 

Given an optimization problem say, to maximize an **objective** function 

:::{math}
:enumerated: false
f(x_1, x_2)
:::

subject to a constraint:

:::{math}
:enumerated: false
g(x_1, x_2) = c.
:::

Begin by defining the Lagrangian function:

:::{math}
:enumerated: false
\mathcal{L}(x_1, x_2, \lambda)
= f(x_1, x_2)
- \lambda(g(x_1, x_2) - c).
:::

where $\lambda$ is known as the Lagraingain multiplier.

Then the **First-Order Conditions (F.O.C)**: simply get the first partials of the Lagrangian function

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}(x_1, x_2, \lambda)}{\partial x_1} = 0, \quad 
\frac{\partial \mathcal{L}(x_1, x_2, \lambda)}{\partial x_2} = 0 \quad \text{ and }
\frac{\partial \mathcal{L}(x_1, x_2, \lambda)}{\partial \lambda} = 0
:::

And solve for the critical values of $x_1^*$ and $x_2^*$.

Note that the last condition simply reproduces the constraint.

--- 

Let's continue with the example above: We wish to maximize equation {eq}`eq:objective_func` subject to {eq}`eq:constraint`. To find the first-order conditions (FOCs) for this specific Lagrangian, we take the partial derivative of $\mathcal{L}$ with respect to each of the three arguments ($x_1$, $x_2$, and $\lambda$) and set them equal to zero.

### The Lagrangian Function

$$\mathcal{L}(x_1, x_2, \lambda) = 2\sqrt{x_1} + \frac{1}{2}\sqrt{x_2} - \lambda(4x_1 + x_2 - 20)$$

---

### First-Order Conditions

**(i) Partial derivative with respect to $x_1$:**

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial x_1} = 2 \left( \frac{1}{2}x_1^{-1/2} \right) - 4\lambda = 0
:::

Simplifying gives:

(eq:6)=
$$x_1^{-1/2} - 4\lambda = 0 \quad \Rightarrow \quad \frac{1}{\sqrt{x_1}} = 4\lambda$$

**(ii) Partial derivative with respect to $x_2$:**

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial x_2} = \frac{1}{2} \left( \frac{1}{2}x_2^{-1/2} \right) - \lambda = 0
:::

Simplifying gives:

(eq:7)=
$$\frac{1}{4}x_2^{-1/2} - \lambda = 0 \quad \Rightarrow \quad \frac{1}{4\sqrt{x_2}} = \lambda$$

**(iii) Partial derivative with respect to $\lambda$:**

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial \lambda} = -(4x_1 + x_2 - 20) = 0
:::

This simply returns the original constraint:

:::{math}
:enumerated: false
4x_1 + x_2 = 20
:::

### Solving the System

A common next step is to solve for $\lambda$ in the first two equations to establish a relationship between $x_1$ and $x_2$:

Setting {eq}`eq:6` and {eq}`eq:7` equal gives:

:::{math}
:enumerated: false
\frac{1}{4\sqrt{x_1}} = \frac{1}{4\sqrt{x_2}} \quad \Rightarrow \quad \sqrt{x_1} = \sqrt{x_2} \quad \Rightarrow \quad x_1 = x_2
:::

Substituting $x_1 = x_2$ into the constraint:

:::{math}
:enumerated: false
4(x_1) + x_1 = 20 \quad \Rightarrow \quad 5x_1 = 20 \quad \Rightarrow \quad x_1^* = 4, \quad x_2^* = 4
:::

Note that this is the same solution as we saw with the substitution method above.

Additionally,

:::{math}
:enumerated: false
\lambda = \frac{1}{8}.
:::

::::{admonition} Interpretation of $\lambda$ 
:class: important
Relaxing the constraint by one unit increases the maximum value of the objective by $\lambda$ or 1/8.
::::

### 8.3 Intuition

At an interior optimum with one equality constraint:

* The objective function's gradient must be **parallel** to the constraint's gradient.

In two dimensions:

:::{math}
:enumerated: false
\nabla f = \lambda \nabla g.
:::

::::{admonition} Economic Meaning of $\lambda$
:class: tip

The Lagrange multiplier $\lambda$ measures how much the objective value increases when the constraint is relaxed marginally.

It is the **shadow value** of the constraint.
::::

---

::::{dropdown} **Try these ^^**

**Lagrangian Method and Lagrange Multipliers**

Use the Lagrangian method to find the optimal values for each constrained optimization problem. Solve also for the Lagrange multiplier, $\lambda$.

**(i)** $f(x,y) = x^2 + 2x + 3y^2 - 6y + xy$ subject to $2x + 2y = 32$

**(ii)** $f(a,b,c) = \frac{1}{2}a^2 + 4b^2 - 4a + 8c^2$ subject to $\frac{1}{2}a + 3b + c = 25$

**(iii)** $f(x,y) = x^3y^4$ subject to $\frac{x}{50} + y = 34$

**(iv)** $f(x,y) = \ln(x + y)$ subject to $xy = 16$

---

**Answers**

**(i)** $(x, y, \lambda) = (12, 4, 15)$  
**(ii)** $(a, b, c, \lambda) = (12, 6, 1, 16)$  
**(iii)** $(x, y, \lambda) = \left(\frac{5100}{7}, \frac{136}{7}, \frac{4(5100)^3(136)^3}{7^6}\right)$  
**(iv)** $(x, y, \lambda) = \left(4, 4, \frac{1}{32}\right)$

::::

---

### 8.4 Second-Order Condition: Bordered Hessian

For the constrained problem, we cannot simply examine the Hessian of $f$.

We must use the **bordered Hessian**.[^1]

[^1]: See Chapter on Linear Algebra: Special Matrices. 

The bordered Hessian is:

:::{math}
:enumerated: false
|\mathbf{\bar{H}}| = \begin{vmatrix}
0 & 4 & 1 \\
4 & -\frac{1}{2}x_1^{-3/2} & 0 \\
1 & 0 & -\frac{1}{8}x_2^{-3/2}
\end{vmatrix}
:::

Hence the second principal minor, we have

:::{math}
:enumerated: false
|\bar{H}_2| = |\mathbf{\bar{H}}| = 5/16
:::

which is positive, hence $|\mathbf{\bar{H}}|$ is negative definite and we have met the sufficient condition for a maximum.

That is, evaluate the determinant at the stationary point we found earlier ($x_1 = 4$, $x_2 = 4$), the resulting matrix is:

:::{math}
:enumerated: false
|\mathbf{\bar{H}}| = |\mathbf{\bar{H}_2}| = \begin{vmatrix}
0 & 4 & 1 \\
4 & -1/16 & 0 \\
1 & 0 & -1/64
\end{vmatrix} = 5/16
:::

which is positive, hence $|\mathbf{\bar{H}}|$ is negative definite and we have met the sufficient condition for a maximum. In other words, for a bivariate case with one constraint, a Lagrangian function is negative (positive) definite at a stationary point if the determinant of its bordered Hessian is positive (negative) when evaluated at that point. In this case we have sufficient condition for the stationary point identified by the Lagrangian method to be a maximum (minimum).

::::{admonition} S.O.C for Bivatiate Case with One Constraint
:class: tip

For one constraint in the bivariate case:

* If determinant of the bordered Hessian > 0 → maximum
* If determinant < 0 → minimum
::::

---

### 8.5 General Case (n variables, m = 1)

More generally, for the case of $n$ arguments and $m$ constraints, we have a sufficient condition for a maximum if the determinant of the bordered Hessian ($|\bar{\mathbf{H}}_{n+m}|$) has the same sign as $(-1)^n$, and the largest $n-m$ leading principal minors alternate in sign. In this case, the quadratic form is negative definite subject to the constraint.

Alternatively, if the largest $n-m$ leading principal minors of the bordered Hessian (including the determinant of the bordered Hessian itself) all have the same sign as $(-1)^m$, then the quadratic form is positive definite subject to the constraint, and the stationary point represents a minimum.

As a rule, we essentially need to evaluate the determinants of the largest $n-m$ leading principal minors of the bordered Hessian.

:::{admonition} Sufficient Condition for Constrained Extrema
:class: tip

For a Lagrangian with $n$ variables and $m$ constraints:

For a Local Maximum:

* The last $n-m$ leading principal minors of the bordered Hessian must alternate in sign.
* The sign of the full determinant $|\mathbf{\bar{H}}|$ must be the same as the sign of $(-1)^n$.

For a Local Minimum:

* The sign of the full determinant and all relevant leading principal minors must match the sign of $(-1)^m$.

General Rule:

We must evaluate the determinants of the largest $n-m$ leading principal minors of the bordered Hessian. If the signs do not follow either pattern above, the stationary point is typically a saddle point.
:::


Also it is important to note is that the Lagrangian method generates a variable not obtained with the
substitution method i.e., the Lagrangian multiplier λ, which represents the effect of a small
change in the constraint on the optimal value of the objective function.

Although we have seen just a simple case, optimization of a bivariate function subject to one constraint, the
Lagrangian method is powerful enough to deal with multivariate functions and multiple constraints

---

::::{dropdown} **Try these ^^**
Use the sufficient condition to determine whether the stationary points identified in (i), (ii), and (iv) of previous questions above represent a maximum, minimum, or saddle point.

**Answers**

**(i)**
:::{math}
:enumerated: false
\bar{\mathbf{H}} = \begin{bmatrix} 0 & 2 & 2 \\ 2 & 1 & 1 \\ 2 & 1 & 6 \end{bmatrix}
:::

which has the determinant $-24$. Since $m=1$, the sign of a minimum must be $(-1)^1 = -1$. Thus, the stationary point is a **minimum**.

**(ii)**
:::{math}
:enumerated: false
\bar{\mathbf{H}} = \begin{bmatrix} 0 & 1/2 & 3 & 1 \\ 1/2 & 1 & 0 & 0 \\ 3 & 0 & 8 & 0 \\ 1 & 0 & 0 & 16 \end{bmatrix}
:::

The determinant of the leading principal minor $|\bar{\mathbf{H}}_3|$ is $-11$ and the full determinant $|\bar{\mathbf{H}}_4|$ is $-184$. Since $m=1$, all minors must have the sign $(-1)^1 = -1$ for a minimum. Hence, we have a **minimum**.

**(iv)**
:::{math}
:enumerated: false
\bar{\mathbf{H}} = \begin{bmatrix} 0 & 4 & 4 \\ 4 & \frac{1}{64} & \frac{1}{64} - \lambda \\ 4 & \frac{1}{64} - \lambda & \frac{1}{64} \end{bmatrix}
:::

With $\lambda = 1/32$, the determinant is $1$. Since $n=2$ and $m=1$, the sign for a maximum must be $(-1)^n = (-1)^2 = +1$. Thus, we have a **maximum**.

### Worked Example: 

#### Second-Order Analysis of (vii) from Problem Set 1

We consider the function $f(x, y, z) = 2x^2 + 5xy - y^2 - 3xz$ subject to the constraint $x + y + z = 14$.

##### 1. The Bordered Hessian Matrix

The bordered Hessian $\mathbf{\bar{H}}$ for $n=3$ variables and $m=1$ constraint is a $4 \times 4$ matrix. The border consists of the first derivatives of the constraint $g(x,y,z) = x+y+z-14$, which are $g_x=1, g_y=1, g_z=1$. Evaluating the second-order partial derivatives, we obtain:

:::{math}
:enumerated: false
\mathbf{\bar{H}} =
\begin{vmatrix}
0 & 1 & 1 & 1 \\
1 & 4 & 5 & -3 \\
1 & 5 & -2 & 0 \\
1 & -3 & 0 & 0
\end{vmatrix}
:::

##### 2. Checking the Minors ($n-m = 2$ minors)

Since we have one constraint ($m=1$), we will check  $n-m = 2$ princpal minors starting from the largest one and working backwards.

**Minor 1: $|\mathbf{\bar{H}}_3|$ (The full $4 \times 4$ determinant)**

Expanding along the last row to simplify calculations:

:::{math}
:enumerated: false
|\mathbf{\bar{H}}_3| = -(-3) \begin{vmatrix} 0 & 1 & 1 \\ 1 & 5 & -3 \\ 1 & -2 & 0 \end{vmatrix} - (0) + (0) - (0) 
:::

Evaluating the $3 \times 3$ sub-determinant:
:::{math}
:enumerated: false
\begin{vmatrix} 0 & 1 & 1 \\ 1 & 5 & -3 \\ 1 & -2 & 0 \end{vmatrix} = -1(0 - (-3)) + 1(-2 - 5) = -3 - 7 = -10
:::

**Total:** $3 \times (-10) = -30$.
* **Result:** $|\mathbf{\bar{H}}_3| < 0$.

**Minor 2: $|\mathbf{\bar{H}}_2|$ (The $3 \times 3$ upper-left block)**

:::{math}
:enumerated: false
|\mathbf{\bar{H}}_2| =
\begin{vmatrix}
0 & 1 & 1 \\
1 & 4 & 5 \\
1 & 5 & -2
\end{vmatrix}
= -1 \begin{vmatrix} 1 & 5 \\ 1 & -2 \end{vmatrix} + 1 \begin{vmatrix} 1 & 4 \\ 1 & 5 \end{vmatrix} = -1(-7) + 1(1) = 8
:::

* **Result:** $|\mathbf{\bar{H}}_2| > 0$.
* 
##### 3. Conclusion

For a system with $m=1$ constraint:
* **Local Maximum:** Pattern must be $(+, -)$ starting from $|\mathbf{\bar{H}}_2|$.
* **Local Minimum:** Pattern must be $(-, -)$ starting from $|\mathbf{\bar{H}}_2|$.

In this case, our signs are $(+, -)$. This matches the alternating pattern required for a **local maximum**. 
::::

---

## III — Multiple Constraints

In general, we can write the Lagrangian function for a constrained optimization problem with an objective function with $n$ variables subject to $m$ equality constraints as follows:

:::{math}
:enumerated: false
\mathcal{L}(x_1, \dots, x_n, \lambda_1, \dots, \lambda_m) = f(x_1, \dots, x_n) - \sum_{i=1}^{m} \lambda_i (g^i(x_1, \dots, x_n) - c_i)
:::

where $g_i(x_1, \dots, x_n) = c_i$ represents the $i$th constraint.

After which we find the stationary points and check for whether we have a maximum, minimum or neither.

### 8.6 Breakfast Example

Let;s try maximizing the Utility function:

:::{math}
:enumerated: false
U(S,V,J)
=\frac{1}{3}\ln S
+
\frac{1}{3}\ln V
+
\frac{1}{3}\ln J.
:::

Subject to a Budget constraint:

:::{math}
:enumerated: false
\frac{S}{4}
+
\frac{V}{2}
+
\frac{J}{12}
= 6.
:::

The Lagrangian function is:

:::{math}
:enumerated: false
\mathcal{L}
=
\frac{1}{3}\ln S
+
\frac{1}{3}\ln V
+
\frac{1}{3}\ln J
-
\lambda\left(
\frac{S}{4}
+
\frac{V}{2}
+
\frac{J}{12}
-
6
\right).
:::

---

#### First-Order Conditions

:::{math}
:enumerated: false
\frac{1}{3S} - \frac{\lambda}{4} = 0, \quad
\frac{1}{3V} - \frac{\lambda}{2} = 0, \quad
\frac{1}{3J} - \frac{\lambda}{12} = 0.
:::

Solving ratios:

:::{math}
:enumerated: false
S = 2V,
\quad
J = 6V,
\quad
S = \frac{1}{3}J.
:::

And using the budget:

:::{math}
:enumerated: false
S^* = 8,
\quad
V^* = 4,
\quad
J^* = 24.
:::

> As an exercise, verify that we have a maximum by evaluating the bordered Hessian. Note that in this case $m-n = 3-1$, so we need to evaluate the determinants of the largest **two** principal minors, $|\mathbf{\bar{H}}| = |\mathbf{\bar{H}_3}|$ and $|\mathbf{\bar{H}_2}|$. 
 
---

### Adding a Second Constraint

Suppose we have a second constraint:

:::{math}
:enumerated: false
S + J = 24.
:::

Then the Lagrangian function becomes

:::{math}
:enumerated: false
\begin{aligned}
\mathcal{L}(S, V, J, \lambda_1, \lambda_2) &= \frac{1}{3}\ln S + \frac{1}{3}\ln V + \frac{1}{3}\ln J \\
&\quad - \lambda_1 \left( \frac{S}{4} + \frac{V}{2} + \frac{J}{12} - 6 \right) - \lambda_2(S + J - 24)
\end{aligned}
:::

The F.O.C are

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial S} = \frac{1}{3S} - \frac{\lambda_1}{4} - \lambda_2 = 0
:::

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial V} = \frac{1}{3V} - \frac{\lambda_1}{2} = 0
:::

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial J} = \frac{1}{3J} - \frac{\lambda_1}{12} - \lambda_2 = 0
:::

Including the two constraints

:::{math}
:enumerated: false
\frac{S}{4} + \frac{V}{2} + \frac{J}{12} = 6
:::

:::{math}
:enumerated: false
S + J = 24
:::

From the first 3 equations, we find that

:::{math}
:enumerated: false
V = \frac{SJ}{3(J - S)}
:::

Perhaps we should explain this before moving on? We need to eliminate the Lagrange multipliers ($\lambda_1$ and $\lambda_2$) using the first three equations.

**Step 1: Isolate $\lambda_1$:**
From the second FOC ($\frac{\partial \mathcal{L}}{\partial V}$):

:::{math}
:enumerated: false
\frac{1}{3V} = \frac{\lambda_1}{2} \implies \lambda_1 = \frac{2}{3V}
:::

**Step 2: Isolate $\lambda_2$:**
Subtract the third FOC from the first FOC to cancel out $\lambda_2$:

:::{math}
:enumerated: false
\left( \frac{1}{3S} - \frac{\lambda_1}{4} - \lambda_2 \right) - \left( \frac{1}{3J} - \frac{\lambda_1}{12} - \lambda_2 \right) = 0
:::

:::{math}
:enumerated: false
\frac{1}{3S} - \frac{1}{3J} - \frac{\lambda_1}{4} + \frac{\lambda_1}{12} = 0
:::

**Step 3: Combine and Solve for $V$:**
Substitute our $\lambda_1$ value ($\frac{2}{3V}$) into that result:

:::{math}
:enumerated: false
\frac{1}{3S} - \frac{1}{3J} = \frac{1}{4}\left(\frac{2}{3V}\right) - \frac{1}{12}\left(\frac{2}{3V}\right)
:::

:::{math}
:enumerated: false
\frac{J - S}{3SJ} = \frac{2}{12V} - \frac{2}{36V}
:::

:::{math}
:enumerated: false
\frac{J - S}{3SJ} = \frac{6}{36V} - \frac{2}{36V} = \frac{4}{36V} = \frac{1}{9V}
:::

Now, rearrange to solve for $V$:

:::{math}
:enumerated: false
9V(J - S) = 3SJ
:::

:::{math}
:enumerated: false
V = \frac{3SJ}{9(J - S)} = \frac{SJ}{3(J - S)}
:::

We proceed by simplify the first constraint by substituting $V = \frac{SJ}{3(J - S)}$ into the first constraint:

:::{math}
:enumerated: false
\frac{S}{4} + \frac{1}{2} \left( \frac{SJ}{3(J - S)} \right) + \frac{J}{12} = 6
:::

:::{math}
:enumerated: false
\frac{S}{4} + \frac{SJ}{6(J - S)} + \frac{J}{12} = 6
:::

To clear the denominators, multiply the entire equation by $12(J - S)$:

:::{math}
:enumerated: false
3S(J - S) + 2SJ + J(J - S) = 72(J - S)
:::

:::{math}
:enumerated: false
3SJ - 3S^2 + 2SJ + J^2 - SJ = 72J - 72S
:::

:::{math}
:enumerated: false
4SJ - 3S^2 + J^2 = 72J - 72S
:::

Next, from the second constraint, we know $J = 24 - S$. We substitute this into our simplified equation:

:::{math}
:enumerated: false
4S(24 - S) - 3S^2 + (24 - S)^2 = 72(24 - S) - 72S
:::

:::{math}
:enumerated: false
96S - 4S^2 - 3S^2 + (576 - 48S + S^2) = 1728 - 72S - 72S
:::

And grouping the $S$ terms:

:::{math}
:enumerated: false
-6S^2 + 48S + 576 = 1728 - 144S
:::

:::{math}
:enumerated: false
-6S^2 + 192S - 1152 = 0
:::

Divide by $-6$ to make it a standard quadratic:

:::{math}
:enumerated: false
S^2 - 32S + 192 = 0
:::

Using the quadratic formula or factoring $(S - 24)(S - 8) = 0$ gives $S = 24$. This would imply $J = 0$, which is impossible given the $\ln J$ term in our objective function. 

$S = 8$: This is our valid solution.

The final Values $S = 8$, $J = 24 - 8 = 16$ and $V = \frac{SJ}{3(J - S)} = \frac{8 \times 16}{3(16 - 8)} = \frac{128}{24} = \frac{16}{3} \text{ or } 5 \frac{1}{3}$

Hence, the optimal point for this system is:

:::{math}
:enumerated: false
S^* = 8,
\quad
V^* = 5\frac{1}{3},
\quad
J^* = 16.
:::

Which gives an utility of $2.17$, which is lower than $2.21$ (without the second constraint).

---

Now the second order conditions, or bordered Hessian.

:::{math}
:enumerated: false
|\mathbf{\bar{H}}| = 
\begin{vmatrix}
0 & 0 & \frac{1}{4} & \frac{1}{2} & \frac{1}{12} \\
0 & 0 & 1 & 0 & 1 \\
\frac{1}{4} & 1 & -\frac{1}{3S^2} & 0 & 0 \\
\frac{1}{2} & 0 & 0 & -\frac{1}{3V^2} & 0 \\
\frac{1}{12} & 1 & 0 & 0 & -\frac{1}{3J^2}
\end{vmatrix}
:::

And

:::{math}
:enumerated: false
|\mathbf{\bar{H}}| = -\left( \frac{1}{12S^2} + \frac{1}{12J^2} + \frac{1}{108V^2} \right) < 0
:::

which matches the sign of $(-1)^n$ where in this case $n=3$, i.e., both are negative.

Hence the stationary point $S^* = 8$, $V^* = 5 \frac{1}{3}$, and $J^* = 16$ represent a maximum.

But don't we have to evaluete the determinant other principal minors of the bordered Hessian as well? No, because in this case, we have to evaluate only $n-m = 3-2 = 1$ largest Hessians. 

In general, for the case of $n$ arguments and $m$ constraints, we have a sufficient condition for a **maximum** if the largest $n - m$ leading principal minors of the bordered Hessian alternate in sign, with the sign of the full determinant ($| \mathbf{\bar{H}}|$) being the same as $(-1)^n$.

Alternatively, we have a sufficient condition for a **minimum** if the largest $n - m$ leading principal minors of the bordered Hessian all have the same sign, which must be the same as the sign of $(-1)^m$. If the minors do not follow either of these patterns, the second-order condition for a local extremum is not satisfied.

::::{admonition} Common Pitfall: Parity of n and m
:class: warning

One might be tempted to say that for a minimum, the sign of the determinant must be "different" from the sign required for a maximum $(-1)^n$. This is not always true.

The relationship between the signs depends on whether the difference between the number of variables $n$ and constraints $m$ is odd or even:

* When $n - m$ is odd: The signs for a maximum $(-1)^n$ and a minimum $(-1)^m$ will be different.
* When $n - m$ is even: The signs for a maximum and a minimum will be the same.

**Rule of Thumb:** Always use the number of constraints $m$ to determine the sign for a minimum $(-1)^m$ and the number of variables $n$ to determine the final sign for a maximum $(-1)^n$.
::::

---

::::{dropdown} **Try these ^^**

**Lagrange Method with Multiple Constraints**

Use the Lagrange method to determine the optimal values for the choice variables in the following problem involving multiple constraints.

**Problem:**
Find the stationary point for the function:
:::{math}
:enumerated: false
z = x^2 + 2xy + w^2
:::

subject to the constraints:
:::{math}
:enumerated: false
2x + y + 3w = 24 \quad \text{and} \quad x + w = 8
:::

---

**Answer**

$(w, x, y) = (2, 2, 6)$

**Worked Solution:**

* **Set up the Lagrangian:**

We introduce two Lagrange multipliers, $\lambda_1$ and $\lambda_2$, for the two constraints:

:::{math}
:enumerated: false
\mathcal{L} = x^2 + 2xy + w^2 - \lambda_1(2x + y + 3w - 24) - \lambda_2(x + w - 8)
:::

* **First-Order Conditions (F.O.C.s):**
   * $\frac{\partial \mathcal{L}}{\partial x} = 2x + 2y - 2\lambda_1 - \lambda_2 = 0$
   * $\frac{\partial \mathcal{L}}{\partial y} = 2x - \lambda_1 = 0 \implies \lambda_1 = 2x$
   * $\frac{\partial \mathcal{L}}{\partial w} = 2w - 3\lambda_1 - \lambda_2 = 0$
   * $\frac{\partial \mathcal{L}}{\partial \lambda_1} = 2x + y + 3w - 24 = 0$
   * $\frac{\partial \mathcal{L}}{\partial \lambda_2} = x + w - 8 = 0$

* **Solving the System:**
   * From the second F.O.C., we have $\lambda_1 = 2x$.
   * Substitute $\lambda_1$ into the third F.O.C.: $2w - 3(2x) - \lambda_2 = 0 \implies \lambda_2 = 2w - 6x$.
   * Substitute both $\lambda_1$ and $\lambda_2$ into the first F.O.C.:

:::{math}
:enumerated: false
2x + 2y - 2(2x) - (2w - 6x) = 0
:::

:::{math}
:enumerated: false
\begin{aligned}
2x + 2y - 4x - 2w + 6x = 0 &\implies 4x + 2y - 2w = 0 \\
&\implies 2x + y - w = 0
\end{aligned}
:::

   * Now use the constraints: From $x + w = 8$, we have $w = 8 - x$.
   * Substitute $w$ into our derived equation: $2x + y - (8 - x) = 0 \implies 3x + y = 8 \implies y = 8 - 3x$.
   * Substitute $w = 8 - x$ and $y = 8 - 3x$ into the first constraint:

:::{math}
:enumerated: false
2x + (8 - 3x) + 3(8 - x) = 24
:::

:::{math}
:enumerated: false
2x + 8 - 3x + 24 - 3x = 24
:::

:::{math}
:enumerated: false
-4x = -8 \implies \mathbf{x = 2}
:::

   * Then, $\mathbf{w = 8 - 2 = 6}$ and $\mathbf{y = 8 - 3(2) = 2}$.
::::

---

## IV — Inequality Constraints

### 8.7 Why Inequalities Change Everything

So far we have considered constraints which are strictly equalities. We now consider the case when
constraints take the form of inequalities rather than equalities. This involves a slight modification to
the Lagrangian method, which we present below.

::::{admonition} Optimization with Inequaity Constraints
:class: tip

With inequalities:

* Constraint may bind
* Constraint may not bind

Interior and corner solutions both possible.
:::::

---

### 8.8 The Kuhn–Tucker Conditions

Maximize:

:::{math}
:enumerated: false
f(x_1, \dots, x_n)
:::

subject to:

:::{math}
:enumerated: false
g_i(x_1, \dots, x_n) \le c_i.
:::

Set up the Lagrangian function as usual:

:::{math}
:enumerated: false
\mathcal{L}
=
f(x_1, \dots, x_n)
-
\sum_{i=1}^m
\lambda_i(g_i(x_1, \dots, x_n) - c_i).
:::

The solutions to this problem satisfies the following conditions:

1. Stationarity

:::{math}
:enumerated: false
\frac{\partial \mathcal{L}}{\partial x_k} = 0, \quad \text{ for } k=1, \dots, n
:::

2. Primal feasibility

:::{math}
:enumerated: false
g_i(x) \le c_i, , \quad \text{ for } i=1, \dots, m
:::

3. Dual feasibility

:::{math}
:enumerated: false
\lambda_i \ge 0, \quad \text{ for } i=1, \dots, m
:::

4. Complementary slackness

:::{math}
:enumerated: false
\lambda_i(c_i - g_i(x)) = 0, , \quad \text{ for } i=1, \dots, m.
:::

The above are known as the Kuhn-Tucker conditions for an optimization problem with inequality constraints.

The last two Kuhn-Ticker conditions are known as **complementary slackness** conditions (meaning that both
optimal points and first-partials evaluated at the optimal points cannot simultaneously both be zero).  

::::{admonition} Complementary Slackness
:class: important

Either:
- Constraint binds and λ > 0  
or  
- Constraint does not bind and λ = 0
::::

---

### 8.11 Worked Inequality Example

Consider the problem of maximizing the objective function:

:::{math}
:enumerated: false
f(x_1, x_2)
=
x_1
-
\frac{x_1^2}{2}
+
x_2^2
:::

subject to the constraints:

:::{math}
:enumerated: false
\frac{x_1^2}{2} + x_2^2 \le \frac{9}{8}
:::

:::{math}
:enumerated: false
-x_2 \le 0.
:::

Note that we have written the constraint that $f(X_1, x_2($ is nonnegative in a way to make it conformable with the
setup of the problem above.

---

The Lagrangian is:

:::{math}
:enumerated: false
\mathcal{L} = x_1 - \frac{x_1^2}{2} + x_2^2 - \lambda_1 \left( \frac{x_1^2}{2} + x_2^2 - \frac{9}{8} \right) - \lambda_2(-x_2)
:::

The optimal choice of $x_1$ and $x_2$ satisfies the Kuhn–Tucker conditions

:::{math}
:enumerated: false
\begin{aligned}
\frac{\partial \mathcal{L}}{\partial x_1} &= 1 - x_1 - \lambda_1 x_1 = 0 \\[10pt]
\frac{\partial \mathcal{L}}{\partial x_2} &= 2x_2 - 2\lambda_1 x_2 + \lambda_2 = 0 \\[10pt]
\frac{x_1^2}{2} + x_2^2 &\le \frac{9}{8} \\
-x_2 &\le 0 \\
\lambda_1 &\ge 0 \\
\lambda_2 &\ge 0 \\
\lambda_1 \left( \frac{9}{8} - \frac{x_1^2}{2} - x_2^2 \right) &= 0 \\
\lambda_2 x_2 &= 0
\end{aligned}
:::

We proceed by considering solutions that arise in four cases corresponding to the four possible ways in which the complementary slackness conditions may be met. These cases are

---

#### Case 1: $\lambda_1 = 0, \lambda_2 = 0$

In this case the condition $\partial L / \partial x_1 = 0$ shows that $x_1 = 1$, and the condition $\partial L / \partial x_2 = 0$ shows that $x_2 = 0$. The pair that $x_1 = 1$ and that $x_2 = 0$ satisfies the constraint

:::{math}
:enumerated: false
\frac{x_1^2}{2} + x_2^2 \le \frac{9}{8}
:::

as well as the constraint $x_2$ which s nonnegative. Hence:

:::{math}
:enumerated: false
x_1 = 1,
\quad
x_2 = 0.
:::

Value:

:::{math}
:enumerated: false
\frac{1}{2}.
:::

---

#### Case 2: $\lambda_1 \neq 0, \lambda_2 = 0$

Here the F.O.C $\partial L / \partial x_2 = 0$ requires that $\lambda_1 = 1$, which satisfies the condition that $\lambda_1 \ge 0$. This in turn requires that $x_1 = 1/2$, and satisfy the condition $\partial L / \partial x_1 = 0$. The complementary slack condition requires that

:::{math}
:enumerated: false
\frac{9}{8} - \frac{(1/2)^2}{2} - x_2^2 = 0
:::

which is satisfied for $x_2 = 1$ or $x_2 = -1$. But the constraint that $x_2$ is nonnegative allows us to consider only $x_2 = 1$. Hence:

:::{math}
:enumerated: false
x_1 = \frac{1}{2},
\quad
x_2 = 1.
:::

Value:

:::{math}
:enumerated: false
\frac{11}{8}.
:::

---

#### Case 3: $\lambda_1 = 0, \lambda_2 ≠ 0$

Here the condition $\partial L/\partial x_1 = 0$ gives $x_1 = 1$. The condition $\lambda_2 x_2 = 0$ requires that $x_2 = 0$. Therefore this solution is identical to the one found when $\lambda_1 = 0$ and $\lambda_2 = 0$. Same as Case 1:

---

#### Case 4: $\lambda_1 ≠ 0, \lambda_2 ≠ 0$
Lastly, we consider the case where $\lambda_1 \neq 0$ and $\lambda_2 \neq 0$. The condition $\lambda_2 x_2 = 0$ requires that $x_2 = 0$. But if $x_2 = 0$, the condition $\partial L / \partial x_2 = 0$ requires that $\lambda_2 = 0$. Therefore there is no feasible solution in which $\lambda_1 \neq 0$ and $\lambda_2 \neq 0$.

---

### Conclusion

Comparing the valid cases:

* **Case 1 & 3**: $f(1, 0) = 1/2$
* **Case 2**: $f(1/2, 1) = 11/8$

Ranking the solutions by the value of the objective function, $11/8 > 1/2$, we find that the optimal solution is $x_1^* = 1/2, x_2^* = 1$ since

:::{math}
:enumerated: false
f \left( \frac{1}{2}, 1 \right) > f(1, 0)
:::

corresponding to Case 2 where $\lambda_1 \neq 0$ and $\lambda_2 = 0$. 

Furthermore, note that at the optimal solution,

:::{math}
:enumerated: false
\frac{x_1^2}{2} + x_2^2 = \frac{9}{8}
:::

and this constraint is binding, while

:::{math}
:enumerated: false
-x_2 < 0
:::

and this constraint is not binding.


That is, at

:::{math}
:enumerated: false
x_1 = \frac{1}{2},
\quad
x_2 = 1.
:::

Constraint 1 binds.
But constraint 2 does not bind.

---

::::{admonition} Minimizing
:class: important

To minimize $h(x)$, maximize $-h(x)$.
* Rewrite $j(x) \ge z$ as $-j(x) \le z$.

* In mixed problems:
  * Equalities must hold exactly.
  * Inequalities may bind or not bind.
::::


::::{dropdown} **Try these ^^**

#### Inequality Constraint Problems

Solve the following problems involving inequality constraints.

**i. Find the maximum value of the function**

:::{math}
:enumerated: false
h(x, y) = 2x^2 - y^2
:::

subject to

:::{math}
:enumerated: false
x^2 + y^2 = 1
:::

and the constraints that $x$ and $y$ are nonnegative.

**ii. Find the maximum value of the function**

:::{math}
:enumerated: false
r(a, b) = 2a^2 + b^2
:::

subject to

:::{math}
:enumerated: false
2a + b \le 9 \text{ and } a^2 + b^2 \ge 16
:::

**iii. Consider the three-item breakfast problem with the utility function**

:::{math}
:enumerated: false
U(S, V, J) = \frac{1}{3}\ln S + \frac{1}{3}\ln V + \frac{1}{3}\ln J
:::

subject to

:::{math}
:enumerated: false
\frac{S}{4} + \frac{V}{2} + \frac{J}{12} \le 6 \text{ and } S + J \le 40
:::

---

#### Answers

**(i)** The Lagrangian function for this problem is:

:::{math}
:enumerated: false
\mathcal{L} = 2x^2 - y^2 - \lambda_1(x^2 + y^2 - 1) + \lambda_2 x + \lambda_3 y
:::

The solution that provides the maximum value must satisfy the following first-order and complementary slackness conditions:

:::{math}
:enumerated: false
\begin{aligned}
\frac{\partial \mathcal{L}}{\partial x} &= 4x - 2\lambda_1 x + \lambda_2 = 0 \\
\frac{\partial \mathcal{L}}{\partial y} &= -2y - 2\lambda_1 y + \lambda_3 = 0 \\
\lambda_1(x^2 + y^2 - 1) &= 0 \\
\lambda_2 x &= 0 \\
\lambda_3 y &= 0 \\
\lambda_2 \ge 0, & \quad \lambda_3 \ge 0 \\
x^2 + y^2 &= 1
\end{aligned}
:::

The optimal solution is **$x = 1, y = 0$**, which implies that $\lambda_2 = 0$ (via complementary slackness). At this point, the objective function reaches its maximum value of $h(1, 0) = 2$.

**(ii)** The Lagrangian function is:

:::{math}
:enumerated: false
\mathcal{L} = 2a^2 + b^2 - \lambda_1(2a + b - 9) - \lambda_2(a^2 + b^2 - 16)
:::

The solution that provides the maximum value must satisfy:

:::{math}
:enumerated: false
\begin{aligned}
\frac{\partial \mathcal{L}}{\partial a} &= 4a - 2\lambda_1 - 2a\lambda_2 = 0 \\
\frac{\partial \mathcal{L}}{\partial b} &= 2b - \lambda_1 - 2b\lambda_2 = 0 \\
\lambda_1(2a + b - 9) &= 0 \\
\lambda_2(a^2 + b^2 - 16) &= 0 \\
\lambda_1 \ge 0, & \quad \lambda_2 \ge 0 \\
16 \le a^2 + b^2, & \quad 2a + b \le 9
\end{aligned}
:::

The optimal solution has **$\lambda_1 \neq 0$ and $\lambda_2 = 0$**, with **$a = b = 3$**. At this point, the objective function reaches its maximum value of $r(3, 3) = 27$.

**(iii)**

The Lagrangian function for this problem is:

:::{math}
:enumerated: false
\mathcal{L} = \frac{1}{3}\ln S + \frac{1}{3}\ln V + \frac{1}{3}\ln J - \lambda_1\left(\frac{S}{4} + \frac{V}{2} + \frac{J}{12} - 6\right) - \lambda_2(S + J - 40)
:::

The solution that provides the maximum value must satisfy the following first-order and complementary slackness conditions:

:::{math}
:enumerated: false
\begin{aligned}
\frac{\partial \mathcal{L}}{\partial S} &= \frac{1}{3S} - \frac{\lambda_1}{4} - \lambda_2 = 0 \\
\frac{\partial \mathcal{L}}{\partial V} &= \frac{1}{3V} - \frac{\lambda_1}{2} = 0 \\
\frac{\partial \mathcal{L}}{\partial J} &= \frac{1}{3J} - \frac{\lambda_1}{12} - \lambda_2 = 0 \\
\lambda_1 \left( \frac{S}{4} + \frac{V}{2} + \frac{J}{12} - 6 \right) &= 0 \\
\lambda_2(S + J - 40) &= 0 \\
\lambda_1 \ge 0, & \quad \lambda_2 \ge 0 \\
\frac{S}{4} + \frac{V}{2} + \frac{J}{12} \le 6, & \quad S + J \le 40
\end{aligned}
:::

The optimal solution has **$\lambda_1 \neq 0$ and $\lambda_2 = 0$**, which implies the first constraint is binding. Solving the system yields:
**$S = 8, V = 4, \text{ and } J = 24$**.

::::