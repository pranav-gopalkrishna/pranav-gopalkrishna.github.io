<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Number Theory**](https://pranav-gopalkrishna.github.io/mathematics/number-theory)

**BASIC AND MISCELLANEOUS RESULTS**

---

**Contents**:

- [Basic results](#basic-results)
  - [1. Well-ordering property:](#1-well-ordering-property)
  - [2. Pigeonhole property:](#2-pigeonhole-property)
  - [3. Principle of mathematical induction:](#3-principle-of-mathematical-induction)
- [Miscellaneous results](#miscellaneous-results)

---

# Basic results
## 1. Well-ordering property:
Every non-empty subset of non-negative integers has a minimum value i.e. a value that is strictly lesser than every other value.

## 2. Pigeonhole property:
If $s$ objects are distributed into $k$ boxes, where $s > k$, then at least one box contains more than one object.

## 3. Principle of mathematical induction:
If $P$ is a set of integers such that...

- $a$ is in $P$
- $\forall \text{ } k \in \mathbb{Z}$ where $k \geq a$, if $k$ is in $P$, then $k+1$ is also in $P$

... then $P$ contains all integers greater than or equal to $a$, i.e. $P = {x \in \mathbb{Z} : x \geq a}$.

# Miscellaneous results

Define $a \mod b$ as the remainder of $\frac{a}{b}$. Then:

$xy \mod z = ((x \mod z)(y \mod z)) \mod z$

Hence, by extension, for a positive integer k:

$x^k \mod y = (x \mod y)^k \mod y$