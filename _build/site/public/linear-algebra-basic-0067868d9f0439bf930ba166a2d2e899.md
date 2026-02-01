# Linear Algebra: Basics

## Vector

A vector is a mathematical quantity that has both **magnitude** (or size) and **direction**. 

Geometrically, a vector is represented as a directed line segment, like an arrow, where the length signifies the magnitude and the arrowhead indicates the direction.

<img src="figs/ihat-jhat.png" alt="Basis Vectors" width="50%"/>

More conveniently, you may write a vector as $\begin{bmatrix} 1 \\ 2 \end{bmatrix}$ or simply $\vec{v}$. Can you tell what the magnitude (or length or norm) of the above vector is? 

Another way to represent a vector is by using basis vectors, i.e. $\hat{\imath}$ and $\hat{\jmath}$, where $\hat{\imath} = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $\hat{\jmath} = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$. Hence the vector $\begin{bmatrix} 1 \\ 2 \end{bmatrix}$ can be written as $\vec{v} = 1 \hat{\imath} + 2 \hat{\jmath}$.

Make sure you know how to add, subtract vectors, and also multiply/scale vectors by some scalar.

::::{dropdown} **Try these ^^**

<img src="figs/ihat-jhat2.png" alt="Vectors" width="300"/>

(1) Express the above two vectors as column vectors and in $\hat{\imath}, \hat{\jmath}$ notation.

(2) Find also:

(a) $\vec{v} + \vec{w}$ &emsp;&emsp; (b) $\vec{v} - \vec{w}$ &emsp;&emsp; 
(c) $\vec{v} + 2\vec{w}$ &emsp;&emsp; (d) $\vec{v} - 2\vec{w}$

(3) Consider the following vectors:

:::{math}
:enumerated: false
\vec{u} = \begin{bmatrix} -1 \\ 2 \\ 3 \end{bmatrix}, \quad
\vec{v} = \begin{bmatrix} -1 \\ 2 \\ 3 \end{bmatrix}, \quad
\vec{w} = \begin{bmatrix} 4 \\ 5 \\ -2 \end{bmatrix}
:::

Find:  

(a) $\vec{u} + \vec{v}$  &emsp;&emsp; (b) $-\vec{u} + 2\vec{v} - \vec{w}$  
(c) $\vec{u} \cdot \vec{v}$ (i.e. the dot product) &emsp;&emsp; (d) $\vec{u}^T \vec{v}$  
(e) Which of the above vectors are orthogonal?  
(f) Express each of the vectors in $\hat{\imath}, \hat{\jmath}, \hat{k}$ notation.
::::

## Matrix Basics

We have already introduced the basis vectors $\hat{\imath}$ and $\hat{\jmath}$, which we can put into a matrix. That is, the $\hat{\imath}$ and $\hat{\jmath}$ vectors placed side-by-side in a $2 \times 2$ matrix:

$$
\begin{bmatrix} 
1 & 0 \\ 
0 & 1 
\end{bmatrix}
$$

Now suppose we want to rotate $\vec{v} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$ anticlockwise by 90°. Where will it go?

We can rotate the 2-D space, such that $\hat{\imath}$ will go to $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$ and $\hat{\jmath}$ will go to $\begin{bmatrix} -1 \\ 0 \end{bmatrix}$. Combining these into a matrix gives:

$$\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$$

This can easily be done by pre-multiplying the vector by the transformation matrix, as follows:

:::{math}
:enumerated: false
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix} = \begin{bmatrix} -2 \\ 1 \end{bmatrix}
:::

Basically, a matrix can be viewed as a way to transform/change a vector!

::::{admonition} Matrix multiplication
:class: note
The proper way to multiply a matrix and a vector is:

:::{math}
:enumerated: false
1 \begin{bmatrix} 0 \\ 1 \end{bmatrix} + 2 \begin{bmatrix} -1 \\ 0 \end{bmatrix} = \begin{bmatrix} -2 \\ 1 \end{bmatrix}
:::
::::

**Matrix addition and subtraction:** If $\mathbf{A} = (a_{ij})$ and $\mathbf{B} = (b_{ij})$ are two $m \times n$ matrices of same dimension, then $\mathbf{A} + \mathbf{B}$ is defined as $(a_{ij} + b_{ij})$. That is, we add element by element the two matrices.  
Clearly $\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}$. The rule applies to matrix subtraction.

**Transpose of a matrix:** If $\mathbf{A}$ is an $m \times n$ matrix, then $\mathbf{A}'$ is the $n \times m$ matrix whose rows are the columns of $\mathbf{A}$. So $\mathbf{A}' = (a_{ji})$. For example:

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix} = \begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
$$

---
* Note: $(\mathbf{A} + \mathbf{B})' = \mathbf{A}' + \mathbf{B}'$, however $(\mathbf{A}\mathbf{B})' = \mathbf{B}'\mathbf{A}'$.

---

**Null matrix:** Has all elements as 0. Clearly $\mathbf{A} + \mathbf{0}_{m,n} = \mathbf{0}_{m,n} + \mathbf{A} = \mathbf{A}$ for all $m \times n$ matrices.

**Scalar multiplication:** If $\mathbf{A} = (a_{ij})$ then for any constant $k$, define $k\mathbf{A} = (k a_{ij})$. That is, multiply each element in $\mathbf{A}$ by $k$.

**Matrix multiplication:** Say $\mathbf{A}$ is $m \times n$, and $\mathbf{B}$ is $n \times p$, then the $m \times p$ matrix $\mathbf{A}\mathbf{B}$ is the product of $\mathbf{A}$ and $\mathbf{B}$. For example:

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\begin{bmatrix}
e & f \\
g & h
\end{bmatrix}
= \begin{bmatrix}
ae + bg & af + bh \\
ce + dg & cf + dh
\end{bmatrix}
$$

and the matrices $\mathbf{A}$ and $\mathbf{B}$ are conformable.

Fro example, given the matrices:

:::{math}
:enumerated: false
A = \begin{bmatrix} 1 & 2 \\ 3 & -4 \end{bmatrix}, \quad B = \begin{bmatrix} 5 & 0 \\ -6 & 7 \end{bmatrix}
:::

To multiply $A$ and $B$, we apply the row-by-column rule:

:::{math}
:enumerated: false
\begin{align*}
\begin{bmatrix} 1 & 2 \\ 3 & -4 \end{bmatrix}
\begin{bmatrix} 5 & 0 \\ -6 & 7 \end{bmatrix}
&= \begin{bmatrix}
(1 \times 5) + (2 \times -6) & (1 \times 0) + (2 \times 7) \\
(3 \times 5) + (-4 \times -6) & (3 \times 0) + (-4 \times 7)
\end{bmatrix} \\

&= \begin{bmatrix}
5 - 12 & 0 + 14 \\
15 + 24 & 0 - 28
\end{bmatrix} = \begin{bmatrix}
-7 & 14 \\
39 & -28
\end{bmatrix}
\end{align*}
:::

Long story!!

**Matrix Multiplication: The Column-Wise (Basis Vector) Method**

Instead of dot products, we can view $AB$ as taking the columns of $A$ (the transformed $\hat{\imath}$ and $\hat{\jmath}$) and scaling them by the components in each column of $B$.

From the sam eexample above, let the columns of $A$ be:

:::{math}
:enumerated: false
\vec{a}_1 = \begin{bmatrix} 1 \\ 3 \end{bmatrix}, \quad \vec{a}_2 = \begin{bmatrix} 2 \\ -4 \end{bmatrix}
:::

**Finding Column 1 of the Result:**

We use the first column of $B$ $\begin{bmatrix} 5 \\ -6 \end{bmatrix}$ as scalars:

:::{math}
:enumerated: false
5\begin{bmatrix} 1 \\ 3 \end{bmatrix} + (-6)\begin{bmatrix} 2 \\ -4 \end{bmatrix} = \begin{bmatrix} 5 \\ 15 \end{bmatrix} + \begin{bmatrix} -12 \\ 24 \end{bmatrix} = \begin{bmatrix} -7 \\ 39 \end{bmatrix}
:::

**Finding Column 2 of the Result:**

We use the second column of $B$ $\begin{bmatrix} 0 \\ 7 \end{bmatrix}$ as scalars:

:::{math}
:enumerated: false
0\begin{bmatrix} 1 \\ 3 \end{bmatrix} + 7\begin{bmatrix} 2 \\ -4 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 14 \\ -28 \end{bmatrix} = \begin{bmatrix} 14 \\ -28 \end{bmatrix}
:::

**Final Result:**

:::{math}
:enumerated: false
AB = \begin{bmatrix} -7 & 14 \\ 39 & -28 \end{bmatrix}
:::

as before!

::::{dropdown} **Try these ^^**

(1) For the following matrices:

:::{math}
:enumerated: false
A = \begin{bmatrix} 1 & 2 \\ 3 & -4 \end{bmatrix}, \quad
B = \begin{bmatrix} 5 & 0 \\ -6 & 7 \end{bmatrix},
:::

:::{math}
:enumerated: false
C = \begin{bmatrix} 1 & -3 & 4 \\ 2 & 6 & -5 \end{bmatrix}, \quad
D = \begin{bmatrix} 3 & 7 & -1 \\ 4 & -8 & 9 \end{bmatrix}.
:::

Find:

(a) $5A - 2B$ &emsp;&emsp; (b)  $2A + 3B$ &emsp;&emsp; (c)  $2C - 3D$  
(d)  $AB$ and $(AB)C$ &emsp;&emsp; (e) $BC$ and $A(BC)$ *[Note that $(AB)C = A(BC)$]*  
(f) $A^2$ and $A^3$ &emsp;&emsp; (g) $AD$ and $BD$  
(h) $C^T D$ *[Note that we cannot get $CD$. Why?]*  
(i) $A'$ &emsp;&emsp; (j) $B'$ &emsp;&emsp; (k) $A' B'$ &emsp;&emsp; (l) $(AB)'$ *[Note that $A' B' \neq (AB)'$]*
::::

**Diagonal matrix:** A square $n \times n$ matrix $\mathbf{A}$ is diagonal if all entries off the 'main diagonal' are zero, i.e.

$$
\mathbf{A} = \begin{bmatrix}
a_{11} & 0 & \cdots & 0 \\
0 & a_{22} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & a_{nn}
\end{bmatrix}
$$

Note: The elements in the diagonal of $\mathbf{A}$ are the same as those in $\mathbf{A}'$.

**Trace of a square matrix:** If $\mathbf{A}$ is a square matrix, the trace of $\mathbf{A}$, denoted $\operatorname{tr}(\mathbf{A})$, is the sum of the elements on the main/leading diagonal of $\mathbf{A}$.

**Identity matrix:** Denoted by $\mathbf{I}_n$, the $n \times n$ diagonal matrix with $a_{ii} = 1$ for all $i$. That is:

$$
\mathbf{I}_n = \begin{bmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1
\end{bmatrix}
$$

**Symmetric matrix:** A square matrix $\mathbf{A}$ is symmetric if $\mathbf{A} = \mathbf{A}'$. The identity matrix and the square null matrix are symmetric.

**Idempotent matrix:** A square matrix is said to be idempotent if $\mathbf{A}^n = \cdots = \mathbf{A}^2 = \mathbf{A}$. Below is an example (try squaring the matrix and see what you get).

:::{math}
:enumerated: false
\begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}
:::

**Singular Matrix:** A matrix that is linearly dependent (in the columns or rows) is singular and has determinant of zero. Note that any two (or three) vectors $\mathbf{x}$ and $\mathbf{y}$ (and $\mathbf{z}$) are said to be linearly dependent iff one can be written as a scalar multiple of the other. Two vectors $\mathbf{x} \neq \mathbf{0}$ and $\mathbf{y} \neq \mathbf{0}$ are said to be **linearly independent** iff the ONLY solution to $a\mathbf{x} + b\mathbf{y} = \mathbf{0}$ is $a = 0$ AND $b = 0$. And $\mathbf{x}$ and $\mathbf{y}$ are said to be **orthogonal**.

::::{dropdown} **Try these ^^**

Find:

:::{math}
:enumerated: false
(a) \quad 
\begin{equation*}
\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}^2 \quad \text{and} \quad \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}^3
:::

:::{math}
:enumerated: false
(b) \quad 
\begin{equation*}
\begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix}^2 \quad \text{and} \quad \begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix}^3
:::
::::

### Some Notes on Matrices

1. Usually $\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$. For example, try $\mathbf{A} = \begin{bmatrix}2 & 0 \\ 3 & 1\end{bmatrix}$ and $\mathbf{B} = \begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}$.

2. We can have $\mathbf{A}\mathbf{B} = \mathbf{0}$ even if $\mathbf{A}$ or $\mathbf{B}$ are not zero. For example, try $\mathbf{A} = \begin{bmatrix}6 & -12 \\ -3 & 6\end{bmatrix}$ and $\mathbf{B} = \begin{bmatrix}12 & 6 \\ 6 & 3\end{bmatrix}$.

3. Say, $\mathbf{A} = \begin{bmatrix}4 & 8 \\ 1 & 2\end{bmatrix}$, $\mathbf{B} = \begin{bmatrix}2 & 1 \\ 2 & 2\end{bmatrix}$, and $\mathbf{C} = \begin{bmatrix}-2 & 1 \\ 4 & 2\end{bmatrix}$. We find that $\mathbf{A}\mathbf{B} = \mathbf{A}\mathbf{C}$ even though $\mathbf{B} \neq \mathbf{C}$.

4. Say $\mathbf{A}$ and $\mathbf{B}$ are singular matrices. Then $\mathbf{A}\mathbf{B}$ will not be zero, although the product will be a singular matrix.

## Systems of Equations in Matrix Form

One of the uses of linear algebra in economics is to represent and then solve systems of equations. For instance, consider the system of two equations:

$$
2x_1 + x_2 = 5 \\
-x_1 + x_2 = 2
$$

Here, we can define:

$$
\mathbf{A} = \begin{bmatrix} 2 & 1 \\ -1 & 1 \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 5 \\ 2 \end{bmatrix}
$$

Then we see that:

```{math}
\begin{equation*}
\mathbf{A}\mathbf{x} = \begin{bmatrix} 2 & 1 \\ -1 & 1 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 2x_1 + x_2 \\ -x_1 + x_2 \end{bmatrix}
\end{equation*}
```

The original system is in fact equivalent to the matrix form:

$$
\mathbf{A}\mathbf{x} = \mathbf{b}
$$

## Matrix Row Operations

Matrix row operations, also known as elementary row operations, are three basic actions performed on a matrix: **swapping two rows**, **multiplying a row by a non-zero constant**, and **adding a multiple of one row to another row**.

1. **Interchanging two rows** (Row Swapping): You can swap the positions of any two rows in a matrix. As we will see later, this operation is useful for changing the order of equations in a system without altering the solution.
2. **Multiplying a row by a non-zero constant** (Scalar Multiplication): You can multiply every element in a specific row by any non-zero number. This is equivalent to multiplying both sides of an equation by a constant.
3. **Adding a multiple of one row to another row** (Row Addition): You can multiply one row by a constant and then add the result to another row. The original row and the row being multiplied remain unchanged. This operation is often the most powerful for simplifying systems, as it corresponds to adding a modified version of one equation to another.

We can solve system of equation by row operations.

To solve for $x_1$ and $x_2$, we can use an augmented matrix and perform elementary row operations—swapping rows, scalar multiplication, and row addition—to reach **Reduced Row Echelon Form (RREF)**.

**1. Set up the augmented matrix:**

```{math}
\begin{equation*}
\begin{bmatrix} 2 & 1 & | & 5 \\ -1 & 1 & | & 2 \end{bmatrix}
\end{equation*}
```

**2. Create a leading one in Row 1:**

We can swap $R_1$ and $R_2$:

```{math}
\begin{equation*}
\begin{bmatrix} -1 & 1 & | & 2 \\ 2 & 1 & | & 5 \end{bmatrix}
\end{equation*}
```

Then multiply $R_1$ by $-1$ to get a leading one ($R_1 \leftarrow -1 \cdot R_1$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -1 & | & -2 \\ 2 & 1 & | & 5 \end{bmatrix}
\end{equation*}
```

**3. Create a zero below the leading one:**

Add $-2$ times $R_1$ to $R_2$ ($R_2 \leftarrow R_2 - 2R_1$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -1 & | & -2 \\ 0 & 3 & | & 9 \end{bmatrix}
\end{equation*}
```

**4. Create a leading one in Row 2:**

Multiply $R_2$ by $1/3$ ($R_2 \leftarrow \frac{1}{3}R_2$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -1 & | & -2 \\ 0 & 1 & | & 3 \end{bmatrix}
\end{equation*}
```

**5. Create a zero above the leading one (RREF):**

To reach reduced row echelon form, every column with a leading one must have zeros elsewhere. Add $R_2$ to $R_1$ ($R_1 \leftarrow R_1 + R_2$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & 0 & | & 1 \\ 0 & 1 & | & 3 \end{bmatrix}
\end{equation*}
```

Basically, a matrix can be viewed as a way to transform or change a vector to solve these systems!

**Final Result**

The system provides the unique solution:

```{math}
\begin{equation*}
x_1 = 1, \quad x_2 = 3
\end{equation*}
```

Basically, a matrix can be viewed as a way to transform or change a vector to solve these systems!

> **Note:** We need not reach RREF, and could stop at **Step 4** (or even **Step 3**). At Step 4, the last row tells us that $x_2 = 3$. We can then use **back-substitution** into the first row ($x_1 - x_2 = -2$):
> $$x_1 - 3 = -2 \implies x_1 = 1$$
> This confirms the same result without performing the final row addition.

::::{admonition} Definition: **REF** (Row Echelon Form)
:class: note
A matrix is in **Row Echelon Form** if...
1. Every non-zero row begins with a leading one.  
2. A leading one in a lower row is further to the right.  
3. Zero rows are at the bottom of the matrix.

Note: In some books, leading by one is not required.
::::

::::{admonition} Definition: **RREF** Reduced Row Echelon Form
:class: note
A matrix is in **Reduced Row Echelon Form** if...
1. Every non-zero row begins with a leading one.  
2. A leading one in a lower row is further to the right.  
3. Zero rows are at the bottom of the matrix.  
4. Every **column** with a leading one has zeros elsewhere.

While there can exist several row echelon forms for a matrix, there is only one (a unique) reduced row echelon form.
::::

:::{dropdown} **Try these ^^**

For the following matrices:

```{math}
\begin{equation*}
A = \begin{bmatrix} 2 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 5 \end{bmatrix}, \quad 
B = \begin{bmatrix} 7 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & -4 \end{bmatrix},
\end{equation*}
```

```{math}
\begin{equation*}
C = \begin{bmatrix} 2 & 1 & 2 \\ 0 & 3 & 0 \\ 0 & 0 & 5 \end{bmatrix}, \quad 
D = \begin{bmatrix} 7 & 0 & 0 \\ -2 & 0 & 0 \\ 3 & 1 & -4 \end{bmatrix}.
\end{equation*}
```

Find:

(a) $AB, A^2, B^2$ &emsp;&emsp; (b) $CD, C^2, D^2$ &emsp;&emsp; (c) $AC$ and $BD$  
(d) Determinant of $A, B, C$ and $D$ &emsp;&emsp; (e) Inverse of $A$ and $C$  
(f) Is the matrix $A$ in REF or RREF? What are its pivots?  
(g) How about matrix $B$ and $C$? Explain.  
(h) Change all matrices $A$ to $D$ to RREF (if they aren't in RREF yet) and determine their rank.
:::

## The Determinant of a Matrix

The determinant is a scalar value uniquely associated with a square non-singular matrix, and is usually denoted as $|\mathbf{A}|$. The question of whether or not a matrix is nonsingular and therefore invertible is linked to the value of its determinant.

We can write a generic $2 \times 2$ matrix as:

```{math}
\begin{equation*}
\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}
\end{equation*}
```

and its determinant is defined as:

```{math}
\begin{equation*}
|\mathbf{A}| = a_{11}a_{22} - a_{12}a_{21}
\end{equation*}
```

For a $3 \times 3$ matrix, say:

```{math}
\begin{equation*}
\mathbf{A} = \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix}
\end{equation*}
```

its determinant is:

```{math}
\begin{equation*}
|\mathbf{A}| = a(ei - fh) - b(di - fg) + c(dh - ef)
\end{equation*}
```
Note the sign in front of $b$ is begative, because we imppose (multiply by) the sign matrix $\begin{bmatrix} + & - & + \\ - & + & - \\ + & - & + \end{bmatrix}$.

Visually:

<img src="figs/determinant.png" alt="3x3 Determinant"/>

The 'yellow' bits called **minors** are 'smaller' determinants, now 2 by 2 and easier to handle. Note that the elements of the minor come from remaining elements after deleting the rows and columns of the corresponding elements in the selected row (or column).

Let's take a numerical example.

To find the determinant of matrix $A$ using **Cofactor Expansion** along the first row (technically we could pick any row to work with) involves multiplying each element of the first row by its corresponding $2 \times 2$ minor, following the sign pattern: $(+ , - , +)$ for the first row.

Given:
```{math}
\begin{equation*}
A = \begin{bmatrix} 2 & -3 & 1 \\ 1 & -1 & 2 \\ 3 & 1 & -1 \end{bmatrix}
\end{equation*}
```

The formula for expansion along the first row is:

```{math}
\begin{equation*}
\det(A) = a(M_{11}) - b(M_{12}) + c(M_{13})
\end{equation*}
```

**1. First Element ($a = 2$):**

```{math}
\begin{equation*}
+2 \cdot \begin{vmatrix} -1 & 2 \\ 1 & -1 \end{vmatrix} = 2 \cdot [(-1)(-1) - (2)(1)] = 2(1 - 2) = -2
\end{equation*}
```

**2. Second Element ($b = -3$):**
Note the negative sign from the checkerboard pattern:

```{math}
\begin{equation*}
-(-3) \cdot \begin{vmatrix} 1 & 2 \\ 3 & -1 \end{vmatrix} = 3 \cdot [(1)(-1) - (2)(3)] = 3(-1 - 6) = -21
\end{equation*}
```

**3. Third Element ($c = 1$):**
```{math}
\begin{equation*}
+1 \cdot \begin{vmatrix} 1 & -1 \\ 3 & 1 \end{vmatrix} = 1 \cdot [(1)(1) - (-1)(3)] = 1(1 + 3) = 4
\end{equation*}
```

**Final Result**

Summing the results from each step gives $\det(A) = -2 - 21 + 4 = -19$.

## Properties of Determinants

**Property 1:** $|\mathbf{A}| = |\mathbf{A}'|$ and $|\mathbf{A}| \cdot |\mathbf{B}| = |\mathbf{B}| \cdot |\mathbf{A}|$.

**Property 2:** Interchanging any two rows or columns will affect the sign of the determinant, but not its absolute value.

**Property 3:** Multiplying a single row or column by a scalar will cause the value of the determinant to be multiplied by the scalar.

**Property 4:** Addition or subtraction of a nonzero multiple of any row or column to or from another row or column does not change the value of the determinant.

**Property 5:** The determinant of a triangular matrix is equal to the product of the elements along the principal diagonal.

**Property 6:** If any of the rows or columns equal zero, the determinant is also zero.

**Property 7:** If two rows or columns are identical or proportional, i.e. linearly dependent, then the determinant is zero.


> Note: **Properties 2,3** and **4**  are standard row operations already discussed above.
 
## Matrix Inversion

Consider,the following.

```{math}
\begin{equation*}
\mathbf{A} = \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix}
\end{equation*}
```

Then pre-multiplying by:

```{math}
\begin{equation*}
\begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix}
\end{equation*}
```

Gives:

```{math}
\begin{equation*}
\begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix} \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 10 & 0 \\ 0 & 10 \end{bmatrix} = 10 \mathbf{I}
\end{equation*}
```

Where does the 10 in the matrix after the = sign come from? It is the determinant of $\mathbf{A}$.

Then, (pre-)multiplying both sides of the equation by $\frac{1}{10}$ gives:

```{math}
\begin{equation*}
\frac{1}{10} \begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix} \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix} = \mathbf{I}
\end{equation*}
```

The matrix $\frac{1}{10} \begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix}$ is in fact the inverse of $\mathbf{A}$. 

Hence we have the relationship $\mathbf{A}^{-1} \mathbf{A} = \mathbf{I}$. In fact, $\mathbf{A}^{-1}\mathbf{A} = \mathbf{A}\mathbf{A}^{-1} = \mathbf{I}$.

## Finding the Inverse of a Matrix by Row Operations

We can find the inverse of a matrix using row operations or **Gauss-Jordan Elimination** method. The objective is to transform the matrix $A$ into the Identity matrix $I$. By applying the same sequence of elementary row operations to an Identity matrix simultaneously, that Identity matrix transforms into $A^{-1}$.

Given the matrix $A$ from the example above

```{math}
\begin{equation*}A = \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix}
\end{equation*}
```

We set up an **augmented matrix** $[A | I]$ by placing the $2 \times 2$ Identity matrix to the right of $A$:

```{math}
\begin{equation*}
[A | I] = \begin{bmatrix} 1 & -2 & | & 1 & 0 \\ 3 & 4 & | & 0 & 1 \end{bmatrix}
\end{equation*}
```

**Step-by-Step Row Operations**

**1. Create a zero below the first leading one:**

Subtract 3 times the first row from the second row ($R_2 \leftarrow R_2 - 3R_1$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -2 & | & 1 & 0 \\ 0 & 10 & | & -3 & 1 \end{bmatrix}
\end{equation*}
```

**2. Create a leading one in the second row:**

Multiply the second row by $1/10$ ($R_2 \leftarrow \frac{1}{10}R_2$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -2 & | & 1 & 0 \\ 0 & 1 & | & -3/10 & 1/10 \end{bmatrix}
\end{equation*}
```

**3. Create a zero above the second leading one:**

To reach **Reduced Row Echelon Form (RREF)**, we add 2 times the second row to the first row ($R_1 \leftarrow R_1 + 2R_2$):

```{math}
\begin{equation*}
\begin{bmatrix} 1 & 0 & | & 1 + 2(-3/10) & 0 + 2(1/10) \\ 0 & 1 & | & -3/10 & 1/10 \end{bmatrix}
\end{equation*}
```

Simplifying the arithmetic in the first row:

```{math}
\begin{equation*}
\begin{bmatrix} 1 & 0 & | & 4/10 & 2/10 \\ 0 & 1 & | & -3/10 & 1/10 \end{bmatrix}
\end{equation*}
```

**Final Result**

The left side of the augmented matrix has been transformed into the Identity matrix. Therefore, the right side is now the inverse, $A^{-1}$:

```{math}
\begin{equation*}
A^{-1} = \begin{bmatrix} 0.4 & 0.2 \\ -0.3 & 0.1 \end{bmatrix}
\end{equation*}
```

**Verification**

A matrix multiplied by its inverse must result in the Identity matrix:

```{math}
\begin{equation*}
\begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix}
\begin{bmatrix} 0.4 & 0.2 \\ -0.3 & 0.1 \end{bmatrix}
= \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\end{equation*}
```

## Properties of Inverse

Here are some properties of the inverse of a matrix worth knowing:

**Property 1:** For any nonsingular matrix $\mathbf{A}$, $(\mathbf{A}^{-1})^{-1} = \mathbf{A}$.

**Property 2:** The determinant of the inverse of a matrix is equal to the reciprocal of the determinant of the matrix. That is $|\mathbf{A}^{-1}| = \frac{1}{|\mathbf{A}|}$.

**Property 3:** The inverse of matrix $\mathbf{A}$ is unique.

**Property 4:** For any nonsingular matrix $\mathbf{A}$, the inverse of the transpose of a matrix is equal to the transpose of the inverse of the matrix. $(\mathbf{A}')^{-1} = (\mathbf{A}^{-1})'$.

**Property 5:** If $\mathbf{A}$ and $\mathbf{B}$ are nonsingular and of the same dimension, then $\mathbf{A}\mathbf{B}$ is also nonsingular.

**Property 6:** The inverse of the product of two matrices is equal to the product of their inverses in reverse order. $(\mathbf{A}\mathbf{B})^{-1} = \mathbf{B}^{-1}\mathbf{A}^{-1}$.

## Finding the Inverse of a Matrix (Standard Approach)

The inverse of a matrix is defined as:

$$
\mathbf{A}^{-1} = \frac{1}{|\mathbf{A}|} \operatorname{adj}(\mathbf{A})
$$

Let's say we have the following linear system:

$$
2x_1 - 3x_2 + x_3 = -1 \\
x_1 - x_2 + 2x_3 = -3 \\
3x_1 + x_2 - x_3 = 9
$$

Writing the above system in the form $\mathbf{A}\mathbf{x} = \mathbf{b}$, where:

```{math}
\begin{equation*}
\mathbf{A} = \begin{bmatrix} 2 & -3 & 1 \\ 1 & -1 & 2 \\ 3 & 1 & -1 \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} -1 \\ -3 \\ 9 \end{bmatrix}
\end{equation*}
```
We can therefore solve the system by $\mathbf{x} = \mathbf{A}^{-1}\mathbf{b}$, which means that we need the inverse of $\mathbf{A}$.

**Step 1.** The minor $|M_{ij}|$ is the determinant of the submatrix formed by deleting the $i$-th row and $j$-th column of the original matrix. So we have:

```{math}
\begin{equation*}
\begin{bmatrix}
-1 & -7 & 4 \\
2 & -5 & 11 \\
-5 & 3 & 1
\end{bmatrix}
\end{equation*}
```

**Step 2:** The cofactor $C_{ij}$ is a minor with the prescribed sign that follows the rule:

$$
C_{ij} = (-1)^{i+j} |M_{ij}|
$$

Hence, we have:

```{math}
\begin{equation*}
\begin{bmatrix}
-1 & 7 & 4 \\
-2 & -5 & -11 \\
-5 & -3 & 1
\end{bmatrix}
\end{equation*}
```

**Step 3:** An adjoint matrix is simply the transpose of a cofactor matrix. Continuing the example above, we have:

```{math}
\begin{equation*}
\begin{bmatrix}
-1 & -2 & -5 \\
7 & -5 & -3 \\
4 & -11 & 1
\end{bmatrix}
\end{equation*}
```

Since $|\mathbf{A}| = -19$, we then have:

```{math}
\begin{equation*}
\mathbf{A}^{-1} = - \frac{1}{19} \begin{bmatrix}
-1 & -2 & -5 \\
7 & -5 & -3 \\
4 & -11 & 1
\end{bmatrix}
\end{equation*}
```

and

```{math}
\begin{equation*}
\mathbf{x} = \mathbf{A}^{-1}\mathbf{b} = - \frac{1}{19} \begin{bmatrix}
-1 & -2 & -5 \\
7 & -5 & -3 \\
4 & -11 & 1
\end{bmatrix} \begin{bmatrix} -1 \\ -3 \\ 9 \end{bmatrix}
\end{equation*}
```

which gives $x_1 = 2, x_2 = 1$ and $x_3 = -2$.


## Cramer's Rule

Cramer came up with a simplified method for solving a system of linear equations through the use of determinants.

Basically, given $\mathbf{A}\mathbf{x} = \mathbf{b}$, we have:

$$
\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
$$

Define:

$$
\Delta = |\mathbf{A}|
$$

and

$$
\Delta_1 = \begin{vmatrix} b_1 & a_{12} & a_{13} \\ b_2 & a_{22} & a_{23} \\ b_3 & a_{32} & a_{33} \end{vmatrix}, \quad \Delta_2 = \begin{vmatrix} a_{11} & b_1 & a_{13} \\ a_{21} & b_2 & a_{23} \\ a_{31} & b_3 & a_{33} \end{vmatrix}, \quad \Delta_3 = \begin{vmatrix} a_{11} & a_{12} & b_1 \\ a_{21} & a_{22} & b_2 \\ a_{31} & a_{32} & b_3 \end{vmatrix}
$$

where the columns in the $\mathbf{A}$ matrix are replaced one by one by the $\mathbf{b}$ vector as shown above.

Then:

$$
x_i = \frac{\Delta_i}{\Delta}
$$

So, for the previous example:

```{math}
\begin{equation*}
\mathbf{A} = \begin{bmatrix} 2 & -3 & 1 \\ 1 & -1 & 2 \\ 3 & 1 & -1 \end{bmatrix} \quad \text{and} \quad \det(A) = -19, \quad \mathbf{b} = \begin{bmatrix} -1 \\ -3 \\ 9 \end{bmatrix}
\end{equation*}
```
It follows that

```{math}
\begin{equation*}
\Delta_1 = \begin{vmatrix} -1 & -3 & 1 \\ -3 & -1 & 2 \\ 9 & 1 & -1 \end{vmatrix}, \quad \Delta_2 = \begin{vmatrix} 2 & -1 & 1 \\ 1 & -3 & 2 \\ 3 & 9 & -1 \end{vmatrix}, \quad \Delta_3 = \begin{vmatrix} 2 & -3 & -1 \\ 1 & -1 & -3 \\ 3 & 1 & 9 \end{vmatrix}
\end{equation*}
```
where $\Delta_1 = -38, \Delta_2 = -19$, and $\Delta_3 = 38$. 

So dividing through, you can easily verify that you get the soluitons $\{2, 1, -2\}$ as before!

## Diagonalization

A square matrix A is diagonalizable if it can be written as:

