<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Linear Algebra**](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra)

**LINEAR COMBINATIONS OF VECTORS**

---

**Contents**

- [Vector representations](#vector-representations)
- [Linear combinations of vectors](#linear-combinations-of-vectors)
- [Dealing with linear combinations of vectors using matrices](#dealing-with-linear-combinations-of-vectors-using-matrices)
  - [Scaling multiple vectors at once](#scaling-multiple-vectors-at-once)
  - [Translating multiple vectors at once](#translating-multiple-vectors-at-once)
  - [Linear combination by multiplication with a vector](#linear-combination-by-multiplication-with-a-vector)
  - [Matrix multiplication](#matrix-multiplication)

---

# Vector representations
> **Related material**: [_Vectors_](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra/vectors.html)

---

- **Row vector**: A horizontally ordered sequence of values
- **Column vector**: A vertically ordered sequence of values

When dealing with vectors alone, both representations are logically equivalent, since both representations can be easily mapped to each other one-to-one. However, when trying to deal with multiple vectors at once, it is important to maintain the same representation so as to maintain visual and mathematical clarity.

# Linear combinations of vectors
A linear combination of a set of vectors $\set{v_1, v_2 ... v_n}$ is the summation of the scalar multiples of each vector; each scalar multiple of a vector is linearly related to the vector, hence the name "linear combination". However, note that for such a summation to be meaningful, the vectors being summed must have the same size (i.e. the same number of dimensions) and must represent the same attributes in the same order. Why? Because, as stated in [_Vectors_](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra/vectors.html), a vector is a quantification of magnitudes in two or more dimensions, wherein each dimension refers to a specific attribute being considered, while a magnitude for a given dimension refers to the measurement of the specific attribute the dimension represents. Since different dimensions represent different attributes, two different dimensions are incommensurable to each other. Hence, the only meaningful summation of two vectors is if the magnitudes of commensurable attributes (i.e. attributes represented by the same dimension) are summed. Evidently, then, for the summation of two vectors to be meaningful, the vectors must have the same number of dimensions with the same corresponding definitions for corresponding dimensions.

**NOTE**: _As we shall see, linear combinations of vectors form the basis of dealing with linear equations and transformations, which is why it is important to understand what linear combinations are and under what conditions they are valid._

# Dealing with linear combinations of vectors using matrices
A matrix is a sequence of commensurable vectors (i.e. vectors with the same number of dimensions representing the same attributes). Hence, since matrices are useful in efficiently representing commensurable vectors, matrices can be useful tools in efficiently representing and effectively facilitating the application and results of the linear combinations of vectors. We shall soon see how.

## Scaling multiple vectors at once
Consider the following vectors:

$v_1 = \begin{bmatrix} 1 \newline 2 \end{bmatrix}$, $v_2 = \begin{bmatrix} 3 \newline 4 \end{bmatrix}$, $v_3 = \begin{bmatrix} 5 \newline 6 \end{bmatrix}$

Consolidating them as a matrix:

$M = \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix}$

To scale them all by a factor of $2$:

$2M$

$= 2 \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix}$

$= \begin{bmatrix} 1 \times 2 & 3 \times 2 & 5 \times 2 \newline 2 \times 2 & 4 \times 2 & 6 \times 2 \end{bmatrix}$

$= \begin{bmatrix} 2 & 6 & 10 \newline 4 & 8 & 12 \end{bmatrix}$

## Translating multiple vectors at once
Consider the same vectors and matrix as above:

$M = \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix}$

To translate them all by $2$ units:

$M + 2$

$= \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix} + 2$

$= \begin{bmatrix} 1 + 2 & 3 + 2 & 5 + 2 \newline 2 + 2 & 4 + 2 & 6 + 2 \end{bmatrix}$

$= \begin{bmatrix} 3 & 5 & 7 \newline 4 & 6 & 8 \end{bmatrix}$

## Linear combination by multiplication with a vector
Consider the same vectors and matrix as above:

$M = \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix}$

Suppose we want the linear combination:

$2v_1 + 3v_2 + 4v_3$

This can be done as follows:

$M \begin{bmatrix} 2 \newline 3 \newline 4 \end{bmatrix}$

$= \begin{bmatrix} 1 & 3 & 5 \newline 2 & 4 & 6 \end{bmatrix} \begin{bmatrix} 2 \newline 3 \newline 4 \end{bmatrix}$

$= 2 \begin{bmatrix} 1 \newline 2 \end{bmatrix} + 3 \begin{bmatrix} 3 \newline 4 \end{bmatrix} + 4 \begin{bmatrix} 5 \newline 6 \end{bmatrix}$

We see that this is exactly the same as:

$= 2v_1 + 3v_2 + 4v_3$

---

Note that if we use row vectors instead, we have:

$v_1 = \begin{bmatrix} 1 & 2 \end{bmatrix}$, $v_2 = \begin{bmatrix} 3 & 4 \end{bmatrix}$, $v_3 = \begin{bmatrix} 5 & 6 \end{bmatrix}$

Then, we can represent them as the following matrix:

$M = \begin{bmatrix} 1 & 2 \newline 3 & 4 \newline 5 & 6 \end{bmatrix}$

The vector multiplication needed would then be:

$\begin{bmatrix} 2 & 3 & 4 \end{bmatrix} M$

$= \begin{bmatrix} 2 & 3 & 4 \end{bmatrix} \begin{bmatrix} 1 & 2 \newline 3 & 4 \newline 5 & 6 \end{bmatrix}$

If we take this further, we see the equivalence.

## Matrix multiplication
If matrix multiplication of a matrix $M$ with a vector $v$ represents a linear combination of the vectors consolidated by $M$, then naturally, matrix multiplication of a matrix $M$ with a matrix $N$ represents a sequence of linear combinations of the vectors consolidated by $M$, where the sequence of linear combinations is represented by the vectors consolidated by $N$. Hence, just as the first case results in a vector that is a linear combination of the vectors, the second case results in a matrix that consolidates a sequence of vectors that are linear combinations of vectors.

**NOTE**: _As we shall see, this understanding of matrix multiplication helps us understand how a whole sequence of linear transformations can be encapsulated as a single matrix._