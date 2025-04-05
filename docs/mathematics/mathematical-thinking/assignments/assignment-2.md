<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Assignments**](https://pranav-gopalkrishna.github.io/mathematics/mathematical-thinking/assignments)

**ASSIGNMENT 2**

See questions [here](https://pranav-gopalkrishna.github.io/mathematics/mathematical-thinking/assignments/assignment-2.pdf).

---

**Contents**:

- [1](#1)
- [2](#2)
- [3](#3)
- [4](#4)
- [5](#5)
  - [a](#a)
  - [b](#b)
  - [c](#c)
  - [d](#d)
  - [e](#e)
- [6](#6)
- [7](#7)
- [8](#8)
- [9](#9)
  - [a](#a-1)
  - [b](#b-1)
  - [c](#c-1)
  - [d](#d-1)
  - [e](#e-1)
- [10](#10)
- [11.](#11)
  - [a](#a-2)
  - [b](#b-2)
  - [c](#c-2)
  - [d](#d-2)
  - [e](#e-2)
  - [f](#f)
  - [g](#g)
  - [h](#h)

---

# 1
**b.** $7 \leq p < 12$

**c.** $5 < x < 7$

**d.** $x < 4$ (since $x < 4 \implies x < 6$)

**e.** $-3 < y < 3$ (note that $y^2 < 9 \implies y < 4$ and $y^2 < 9 \implies -3 < y < 3$)

**f.** $x = 0$

# 2
**b.**

$p$ ranges from 7 to below 12.

**c.**

$x$ lies between 5 and 7.

**d.**

$x$ is lesser than 4.

**e.**

$x$ lies between -3 and 3.

**f.**

$x$ equals zero.

# 3
To show $\phi_1 \land \phi_2 ... \phi_n$ is true, it is necessary and sufficient to show that each of $\phi_1, \phi_2 ... \phi_n$ is true.

# 4
To show $\phi_1 \land \phi_2 ... \phi_n$ is false, it is sufficient to show that any one of $\phi_1, \phi_2 ... \phi_n$ is false.

# 5
## a
To help see the answer, observe the following:

| _if_ $\pi > 3$ _is_... | _then_ $\pi > 10$ _is_... |
| --- | --- |
| 0 | 0 |
| 1 | 0 or 1 |

In the second row, the truth value of $(\pi > 3) \lor (\pi > 10)$ is independent of the truth value of $\pi > 10$. The first row shows that there is no case where $\pi > 10$ is true if $\pi > 3$ is false.

| _if_ $\pi > 10$ _is_... | _then_ $\pi > 3$ _is_... |
| --- | --- |
| 0 | 0 or 1 |
| 1 | 1 |

In the first row, the truth value of $(\pi > 3) \lor (\pi > 10)$ is dependent on the truth value of $\pi > 3$. The second row shows that there is no case where $\pi > 3$ is false if $\pi > 10$ is true.

---

Already, we see that the truth value of $(\pi > 3) \lor (\pi > 10)$ is independent of the truth value of $\pi > 10$ and dependent entirely on the truth value of $\pi > 3$. To confirm this, see the following truth table:

| $\pi > 3$ | $\pi > 10$ | $(\pi > 3) \lor (\pi > 10)$ |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | NA |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Removing the NA row:

| $\pi > 3$ | $\pi > 10$ | $(\pi > 3) \lor (\pi > 10)$ |
| --- | --- | --- |
| 0 | 0 | 0 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Here, we see that the truth value of $(\pi > 3) \lor (\pi > 10)$ exactly corresponds to the truth value of $\pi > 3$. Hence, $(\pi > 3) \lor (\pi > 10)$  can be simplified to $\pi > 3$.

## b
The only value $x$ cannot take is 0. Hence:

$(x > 0) \lor (x < 0) \equiv x \neq 0$

## c
$x \geq 0$

## d
$x \geq 0$ (the $x > 0$ clause is contained in this)

## e
$x^2 > 9 \implies (x < -3) \lor (x > 3)$

Hence:

$(x > 3) \lor (x^2 > 9)$

$\equiv (x > 3) \lor (x < -3) \lor (x > 3)$

$\equiv (x < -3) \lor (x > 3)$

$\equiv x^2 > 9$

# 6
**a.**

$\pi$ is greater than 3.

**b.**

$x$ is not equal to 0.

**c.**

$x$ is greater than or equal to 0.

**d.**

$x$ is greater than or equal to 0.

**e.**

The square of $x$ is greater than 9.

# 7
To show $\phi_1 \lor \phi_2 ... \phi_n$ is true, it is sufficient to show that any one of $\phi_1, \phi_2 ... \phi_n$ is true.

# 8
To show $\phi_1 \lor \phi_2 ... \phi_n$ is false, it is necessary and sufficient to show that each of $\phi_1, \phi_2 ... \phi_n$ is false.

# 9
## a
$\lnot (\pi > 3.2) \equiv \pi \leq 3.2$

## b
$\lnot (x < 0) \equiv x \geq 0$

## c
$x^2 > 0 \implies x \neq 0$

Hence:

$\lnot (x^2 > 0)$

$\equiv \lnot x \neq 0$

$\equiv x = 0$

## d
$\lnot (x = 1)$

$\equiv (x < 1) \lor (x > 1)$

$\equiv x^2 > 1$

## e
$\lnot \lnot \psi \equiv \psi$

# 10
**a.**

$\pi$ is less than or equal to 3.2.

**b.**

$x$ is greater than or equal to 0.

**c.**

$x$ is not equal to 0.

**d.**

The square of $x$ is greater than 1.

**e.**

$\psi$ holds true.

# 11.
For reference:

$D =$ "Dollar is strong"

$Y =$ "Yuan is strong"

$T=$ "New US–China trade agreement signed"

---

## a
"Dollar and Yuan are both strong."

$D \land Y$ (simple conjunction)

## b
"Trade agreement fails on news of weak Dollar."

$\lnot T \land \lnot D$

The causal relationship between the news and the failure is irrelevant to the truth of the conjunction inherent in the statement, i.e. that the Dollar is not strong ($\lnot D$) and the new US-China trade agreement is not signed ($\lnot T$).

## c
"Dollar weak but Yuan strong, following new trade agreement."

$\lnot D \land Y \land T$

Again, causality is irrelevant to the inherent conjunction.

## d
"Strong Dollar means a weak Yuan."

$D \land \lnot Y$

## e
"Yuan weak despite new trade agreement, but Dollar remains strong."

$T \land \lnot Y \land D$

## f
"Dollar and Yuan can't both be strong at same time."

$(D \land \lnot Y) \lor (\lnot D \land Y)$

## g
"If new trade agreement is signed, Dollar and Yuan can't both remain strong."

$T \implies \lnot (D \land Y)$

## h
"New trade agreement does not prevent fall in Dollar and Yuan."

$T \not \implies \lnot (D \land Y)$