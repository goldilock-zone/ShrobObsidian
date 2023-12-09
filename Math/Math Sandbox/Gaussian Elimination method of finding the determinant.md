In this mathematical exposition, we will explore the process of finding determinants using Gaussian elimination, providing relevant theorems and presenting a detailed example for a 3x3 matrix. Determinants play a crucial role in linear algebra and have various applications in mathematics and science.

### Gaussian Elimination for Determinants:

Gaussian elimination is a systematic method for solving systems of linear equations and can also be used to find the determinant of a square matrix. The main steps involved are row operations to transform the matrix into an upper triangular form.

#### Theorem 1: Row Operations Preserve Determinants

Let $A$ be an $n \times n$ matrix, and $B$ be the matrix obtained from $A$ by applying a single row operation (e.g., swapping rows, multiplying a row by a constant, or adding a multiple of one row to another). Then, $\det(B) = \det(A)$.

#### Theorem 2: Determinant of an Upper Triangular Matrix

For an upper triangular matrix $U$, the determinant $\det(U)$ is equal to the product of its diagonal entries. In other words, if $U$ has diagonal entries $u_{11}, u_{22}, \ldots, u_{nn}$, then $\det(U) = u_{11} \cdot u_{22} \cdot \ldots \cdot u_{nn}$.

### Example: Finding the Determinant of a 3x3 Matrix

Consider the 3x3 matrix $A$:

$$
A = \begin{bmatrix}
2 & 1 & 3 \\
0 & 4 & 2 \\
1 & 2 & 1
\end{bmatrix}
$$

We will use Gaussian elimination to find $\det(A)$:

#### Step 1: Row Operations

1. Multiply the first row by 2 and subtract the third row:

$$
A' = \begin{bmatrix}
4 & 2 & 6 \\
0 & 4 & 2 \\
1 & 2 & 1
\end{bmatrix}
$$

2. Divide the first row by 4:

$$
A'' = \begin{bmatrix}
1 & \frac{1}{2} & \frac{3}{2} \\
0 & 4 & 2 \\
1 & 2 & 1
\end{bmatrix}
$$

3. Subtract the third row from the first row:

$$
A''' = \begin{bmatrix}
0 & -\frac{3}{2} & \frac{1}{2} \\
0 & 4 & 2 \\
1 & 2 & 1
\end{bmatrix}
$$

#### Step 2: Determinant of Upper Triangular Matrix

Now that we have transformed matrix $A$ into an upper triangular form ($A'''$), we can directly apply Theorem 2 to find its determinant:

$$
\det(A''') = 0 \cdot 4 \cdot 1 = 0
$$

Hence, the determinant of the original matrix $A$ is $\det(A) = \det(A''') = 0$.

In summary, Gaussian elimination is a powerful method for finding determinants, and by using row operations, we can simplify the process. Theorems 1 and 2 provide theoretical support for the validity of this approach. The example demonstrates how to apply these concepts to find the determinant of a 3x3 matrix efficiently.