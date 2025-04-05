<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Linear Algebra**](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra)

**SOLVING A SYSTEM OF OF LINEAR EQUATIONS**

---

**Contents**:

- [Introduction](#introduction)
- [Elimination using matrices](#elimination-using-matrices)
  - [Row reduction a.k.a. Gaussian elimination](#row-reduction-aka-gaussian-elimination)
    - [Setting the context](#setting-the-context)
    - [Row echelon form](#row-echelon-form)
    - [Using row reduction to solve a system of linear equations](#using-row-reduction-to-solve-a-system-of-linear-equations)
  - [Row operations through matrix multiplication](#row-operations-through-matrix-multiplication)

---

# Introduction
Consider a system of two-dimensional linear equations:

$a_1x + b_1y = c_1$

$a_2x + b_2y = c_2$

Note that here, $x$ and $y$ are two separate variables representing two separate attributes, while the rest are constants. Drawing from [_Geometry of Linear Equations_](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra/geometry-of-linear-equations), we can rewrite the given system using as follows:

$\begin{bmatrix} a_1 \newline a_2 \end{bmatrix} x + \begin{bmatrix} b_1 \newline b_2 \end{bmatrix} y = \begin{bmatrix} c_1 \newline c_2 \end{bmatrix}$

Putting $\vec{a} = \begin{bmatrix} a_1 \newline a_2 \end{bmatrix}$, $\vec{b} = \begin{bmatrix} b_1 \newline b_2 \end{bmatrix}$ and $\vec{c} = \begin{bmatrix} c_1 \newline c_2 \end{bmatrix}$, we get:

$\vec{a} x + \vec{b} y = \vec{c}$

Defining $\vec{x} = \begin{bmatrix} x \newline y \end{bmatrix}$ and $A = \begin{bmatrix} a_1 & b_1 \newline a_2 & b_2 \end{bmatrix}$, we get:

$A \vec{x} = \vec{c}$

---

Now, if $A^{-1}$ exists, then:

$A^{-1} A \vec{x} = A^{-1} \vec{c}$

$\implies I \vec{x} = A^{-1} \vec{c}$

$\implies \vec{x} = A^{-1} \vec{c}$

If $A^{-1}$ is known, $A^{-1} \vec{c}$ can be easily obtained as a 2D vector of constants where each dimension corresponds to a variable (dimension 1 to $x$ and dimension 2 to $y$); hence, we get the solution of the system. Thus, we see that this last reformulation reframes the solving of a system of equations as a process of performing matrix operations, and makes it possible to analyse the system of equations using matrix properties. We shall see more examples soon, but to take one example, we get that a system of equations has a unique (i.e. single) solution if and only if the coefficient matrix $A$ is invertible, which in turn is true if and only if $A$ has a determinant (i.e. if $A$ is non-singular).

The reformulation also hints at a link between reducing the coefficients in system of equations and reducing the rows/columns of the coefficient matrix. We shall prove this hint to be true, and shall use this to systematise the method of solving a system of linear equations using matrix row/column reduction, which can (1) make the process of solving such systems more efficient (cognitively and practically), especially for larger systems, and (2) make it possible to implement system-solving algorithms, which would be valuable in solving large systems that would be cumbersome or even unfeasible for a human to solve.

---

To generalise the reformulation for $n$-dimensional linear equations:

$a_{11}x_1 + a_{12}x_2 ... + a_{1n}x_n = c_1$

$a_{21}x_1 + a_{22}x_2 ... + a_{2n}x_n = c_2$

...

$a_{k1}x_1 + a_{k2}x_2 ... + a_{kn}x_n = c_k$

Putting $A = \begin{bmatrix} a_{11} & a_{12} & ... & a_{1n} \newline ... \newline a_{k1} & a_{k2} & ... & a_{kn} \end{bmatrix}$, $\vec{x} = \begin{bmatrix} x_1 \newline ... \newline x_n \end{bmatrix}$ and $\vec{c} = \begin{bmatrix} c_1 \newline ... \newline c_k\end{bmatrix}$, the system becomes:

$A \vec{x} = \vec{c} \implies \vec{x} = A^{-1} \vec{c}$

# Elimination using matrices
Layout of the topics:

1. Row reduction, i.e. RR (to help eliminate coefficients)
2. Back substitution
3. Elimination matrices, i.e. RR as matrix multiplication
4. Failure conditions for matrix-based elimination

## Row reduction a.k.a. Gaussian elimination
The define before explaining, row reduction (also called Gaussian elimination) is the process of performing row operations (i.e. linear combinations of rows) to reduce a matrix to its row echelon form. To explain this definition, we need to grasp the context that gives purpose to such a process, and then grasp the meaning of "row echelon" form and how it ties the context to the purpose.

### Setting the context
Consider the coefficient matrix $A$ and the vector of constant sums $\vec{c}$, as defined in the [introduction](#introduction). Since $\vec{x}$ is a vector of unknowns, it contains no information about the system of linear of equations that is not already contained in $A$ and $\vec{c}$, assuming we know the sequence in which the variables and their coefficients must be placed (note that each column of $A$ corresponds to a variable, and likewise for each dimension of $\vec{c}$). Hence, we can represent the whole system using only $A$ and $\vec{c}$. To condense such a representation for efficiency, we can combine the coefficient and the vector of constant sums into one _augmented matrix_, as follows:

$[A \mid \vec{c}] =  \begin{bmatrix} a_{11} & a_{12} & ... & a_{1n} & \mid & c_1 \newline ... \newline a_{k1} & a_{k2} & ... & a_{kn} & \mid & c_k \end{bmatrix}$

Notice that the linear combinations of the rows of the above augmented matrix directly correspond to the linear combinations of the equations of the system. To clarify, a linear combination of a set of equations is an equation whose left-hand side is a linear combination of the left-hand sides of the equations, and whose right-hand side is a matching linear combination of the right-hand sides of the equations. For example, let us take the following equations (where each subscripted symbol stands for an expression):

$P_1 = Q_1$ ... (Eq. 1)

$P_2 = Q_2$ ... (Eq. 2)

$P_3 = Q_3$ ... (Eq. 3)

A linear combination of the above is:

$2 \times$ (Eq. 1) $-$ (Eq. 2) $+ 3 \times$ (Eq. 3) $\implies 2P_1 - P_2 + 3P_3 = 2Q_1 - Q_2 + 3Q_3$

---

Now, note that we eliminate particular coefficients in a system of linear equations using a particular linear combination of equations; in other words, making linear combinations of equations is the basis of solving a linear system of equations. Hence, making linear combinations of the rows, i.e. _performing row operations_ for the augmented matrix is the basis of solving a linear system of equations using matrices. Specifically, we want to focus on row reduction, i.e. the process of using row operations to reduce the coefficient matrix within the augmented matrix to a row echelon form; the value of this form shall be seen in the next section.

### Row echelon form
_First, some definitions_...

<details><summary><b>Pivot (also called "leading entry")</b></summary><p>The leftmost non-zero entry of a row.</p></details>

<details><summary><b>Zero row</b></summary><p>A row whose every entry is zero.</p></details>

<details><summary><b>Non-zero row</b></summary><p>A row with at least one non-zero entry.</p></details>

---

The define before explaining, a matrix in row echelon form is such that:

- All zero rows are below non-zero rows
- The $(n+1)$th non-zero row's pivot is to the right of the $n$th non-zero row's
- An optional condition is that the pivot must always be $1$

The last condition is optional because, as we shall see, the last condition is non-essential with respect to the purpose which the row echelon form serves. What is this purpose? To grasp it, consider a case wherein a system of linear equations is reduced such that: (1) there is one equation, Eq. 1, with the least number of variables, (2) there is another equation, Eq. 2, with all the variables of Eq. 1 plus one or more variables, and the extra variables can be expressed in terms of Eq. 1's variables, (3) there is another equation, Eq. 3, with all the variables of Eq. 2 plus one or more variables, and the extra variables can be expressed in terms of Eq. 2's variables, etc. Now, if the system has a unique solution (wherein only one valid value is obtained for each variable), then the aforementioned reduction would be as follows: (1) Eq. 1 has only one variable equated to a constant, thereby obtaining the variable's value, (2) Eq. 2 has Eq. 1's variable plus one more variable, and the extra variable can be expressed in terms of Eq. 1's variable, (3) Eq. 3 has Eq. 2's variables plus one more variable, and the extra variable can be expressed in terms of Eq. 2's variables, etc

Clearly, if a system has a solution, the way we obtain the solution must in essence be in the form of the aforementioned reduction. Also, if the system has infinite solutions (i.e. wherein one or more variables may have infinite valid values), then we can infer that at least some Eq. (J + 1) has two or more variables than Eq. J, and if a system has no solutions, then we can infer that at least some Eq. J is invalid. Now, we can see that if we take the augmented matrix defined in ["Setting the context"](#setting-the-context) and reduce it such that the coefficient matrix within it is in row echelon form, we are in fact achieving the aforementioned reduction of the system of linear equations, thereby achieving a form of the augmented matrix by which we can obtain the system's solution(s) (if they exist). Hence, we see why the third condition of the row echelon form is optional: whatever the coefficients of the variable(s) of the last equation, we can easily obtain the system's solution(s) (if they exist) since the coefficient of a variable can easily be divided on both sides so as to isolate the variable.

### Using row reduction to solve a system of linear equations
There are ample references for this:

> - [_Gaussian elimination_ from **Wikipedia**](https://en.wikipedia.org/wiki/Gaussian_elimination)
> - [_Gaussian Elimination Method_ from **Byjus.com**](https://byjus.com/maths/gauss-elimination-method/)
> - [_5.4: Solving Systems with Gaussian Elimination_ from **LibreTexts Mathematics**](https://math.libretexts.org/Courses/Palo_Alto_College/College_Algebra/05%3A_Systems_of_Equations_and_Inequalities/5.04%3A_Solving_Systems_with_Gaussian_Elimination)

## Row operations through matrix multiplication
