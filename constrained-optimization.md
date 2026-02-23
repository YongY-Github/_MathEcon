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

:::{math}
:enumerated: false
f(x_1, x_2) = 2\sqrt{x_1} + \frac{1}{2}\sqrt{x_2}
:::

subject to

:::{math}
:enumerated: false
4x_1 + x_2 = 20.
:::

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

The Lagrange multiplier measures how much the objective value increases when the constraint is relaxed marginally.

It is the **shadow value** of the constraint.
::::

---

### 8.4 Formal Setup

Maximize:

:::{math}
:enumerated: false
f(x_1, x_2)
:::

subject to:

:::{math}
:enumerated: false
g(x_1, x_2) = c.
:::

Define the Lagrangian:

:::{math}
:enumerated: false
L(x_1, x_2, \lambda)
= f(x_1, x_2)
- \lambda(g(x_1, x_2) - c).
:::

---

#### First-Order Conditions

:::{math}
:enumerated: false
\frac{\partial L}{\partial x_1} = 0, \quad
\frac{\partial L}{\partial x_2} = 0, \quad \text{ and }
\frac{\partial L}{\partial \lambda} = 0.
:::

The last condition reproduces the constraint.

---

### 8.5 Applying to Our Example

Lagrangian:

:::{math}
:enumerated: false
L
=
2\sqrt{x_1}
+
\frac{1}{2}\sqrt{x_2}
-
\lambda(4x_1 + x_2 - 20).
:::

Solving yields:

:::{math}
:enumerated: false
x_1^* = 4, \qquad x_2^* = 4.
:::

Additionally,

:::{math}
:enumerated: false
\lambda = \frac{1}{8}.
:::

::::{admonition} Interpretation of $\lambda$ 
:class: important
Relaxing the constraint by one unit increases the maximum value of the objective by $\lambda$ or 1/8.
::::

---

### 8.6 Second-Order Condition: Bordered Hessian

For constrained problems, we cannot simply examine the Hessian of ( f ). We must use the **bordered Hessian**.

For one constraint in the bivariate case:

* If determinant > 0 → maximum
* If determinant < 0 → minimum

In this example:

:::{math}
:enumerated: false
\frac{5}{16} > 0.
:::

Hence, the stationary point is a maximum.

---

### 8.7 General Case (n variables, m = 1)

Sufficient condition for maximum:

* Determinant of bordered Hessian has sign ( (-1)^n )
* Largest ( n-1 ) leading principal minors alternate in sign

Alternatively:

* If all largest ( n-1 ) minors and determinant are negative → minimum

If neither holds → saddle point.

---

## III — Multiple Constraints

### 8.8 Breakfast Example

Utility:

:::{math}
:enumerated: false
U(S,V,J)
=\frac{1}{3}\ln S
+
\frac{1}{3}\ln V
+
\frac{1}{3}\ln J.
:::

Budget constraint:

:::{math}
:enumerated: false
\frac{S}{4}
+
\frac{V}{2}
+
\frac{J}{12}
= 6.
:::

Lagrangian:

:::{math}
:enumerated: false
L
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

Using the budget:

:::{math}
:enumerated: false
S^* = 8,
\quad
V^* = 4,
\quad
J^* = 24.
:::

---

### Adding a Second Constraint

Suppose:

:::{math}
:enumerated: false
S + J = 24.
:::

New Lagrangian:

:::{math}
:enumerated: false
L
=
\frac{1}{3}\ln S
+
\frac{1}{3}\ln V
+
\frac{1}{3}\ln J
-
\lambda_1(\text{budget})
-
\lambda_2(S + J - 24).
:::

Solving:

:::{math}
:enumerated: false
S^* = 8,
\quad
V^* = 5\frac{1}{3},
\quad
J^* = 16.
:::

Utility is $2.17$, which is lower than $2.21$ (without second constraint).

---

### General Rule (n variables, m constraints)

Maximum if:

* Determinant sign = $(-1)^n$
* Largest $n-m$ minors alternate in sign

Minimum if:

* All largest  $n-m$ minors have sign $(-1)^m$

Otherwise: neither maximum nor minimum.

---

## IV — Inequality Constraints

### 8.9 Why Inequalities Change Everything

With inequalities:

* Constraint may bind
* Constraint may not bind

Interior and corner solutions both possible.

---

### 8.10 Kuhn–Tucker Conditions

Maximize:

:::{math}
:enumerated: false
f(x_1, \dots, x_n)
:::

subject to:

:::{math}
:enumerated: false
g_i(x) \le c_i.
:::

Lagrangian:

:::{math}
:enumerated: false
L
=
f(x)
-
\sum_{i=1}^m
-
\lambda_i(g_i(x) - c_i).
:::

Conditions:

1. Stationarity

:::{math}
:enumerated: false
\frac{\partial L}{\partial x_k} = 0
:::

2. Primal feasibility

:::{math}
:enumerated: false
g_i(x) \le c_i
:::

3. Dual feasibility

:::{math}
:enumerated: false
\lambda_i \ge 0
:::

4. Complementary slackness

:::{math}
:enumerated: false
\lambda_i(c_i - g_i(x)) = 0.
:::

::::{admonition} Complementary Slackness
:class: important

Either:
- Constraint binds and λ > 0  
or  
- Constraint does not bind and λ = 0
::::

---

### 8.11 Worked Inequality Example

Maximize:

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

subject to:

:::{math}
:enumerated: false
\frac{x_1^2}{2} + x_2^2 \le \frac{9}{8}
:::

:::{math}
:enumerated: false
-x_2 \le 0.
:::

---

### Case Analysis

We consider four combinations:

#### Case 1: $\lambda_1 = 0, \lambda_2 = 0$

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

Same as Case 1.

---

#### Case 4: $\lambda_1 ≠ 0, lambda_2 ≠ 0$

No feasible solution.

---

#### Optimal Solution

:::{math}
:enumerated: false
x_1 = \frac{1}{2},
\quad
x_2 = 1.
:::

Constraint 1 binds.
Constraint 2 does not bind.

---

## Final Remarks

* To minimize ( h(x) ), maximize ( -h(x) ).
* Rewrite ( j(x) \ge z ) as ( -j(x) \le z ).
* In mixed problems:

  * Equalities must hold exactly.
  * Inequalities may bind or not bind.

