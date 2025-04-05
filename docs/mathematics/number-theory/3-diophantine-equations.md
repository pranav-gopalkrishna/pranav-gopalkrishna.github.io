<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Number Theory**](https://pranav-gopalkrishna.github.io/mathematics/number-theory)

**DIOPHANTINE EQUATIONS**

---

**Contents**:

---

# Theorem 1
The linear Diophantine equation...

$ax + by = c$

... has a solution iff $\gcd(a,b) \mid c$.

**NOTE**: _A solution of a Diophantine means integers for values_ $x$ _and_ $y$ _that satisfy the given equation._

## Proof approach
### Necessary part
For necessary part's proof, note that $\exists x_0, y_0 \in \mathbb{Z}$ such that $ax_0 + by_0 = c$. Now, note that $\gcd(a, b) \mid an + bm \forall \text{ } n,m \in \mathbb{Z} \implies \gcd(a, b) \mid ax_0 + by_0$, since $x_0,y_0 \in \mathbb{Z}$

### Sufficient part
For sufficient part's proof, note that $\gcd(a, b) \mid c \implies c = m \gcd(a, b)$, where $m \in \mathbb{Z}$. Now, note that $\gcd(a, b) = ax + by$ for some $x,y \in \mathbb{Z}$. Hence, $c = m(ax + by) \implies c = a(xm) + b(ym)$. Now, note that since $x,y,m \in \mathbb{Z}, xm,ym \in \mathbb{Z}$.

# Theorem 2
If $(x_0, y_0)$ is a particular solution of the Diophantine equation $ax + by = c$, then the general solution (i.e. the formula for all other solutions) is given by:

- $x = x_0 + bt/d$
- $y = y_0 - at/d$

Here, $d = \gcd(a, b)$.

## Proof approach
We know that $(x_0, y_0)$ is a solution for $ax + by = c$. Hence:

$ax_0 + by_0 = c$ ...(1)

Let $(x_1, y_1)$ be another solution for $ax + by = c$. Hence:

$ax_1 + by_1 = c$ ...(2)

---

(1) and (2)

$\implies ax_0 + by_0 = ax_1 + by_1$

$\implies a(x_1 - x_0) = b(y_0 - y_1)$ ...(3)

---

Let $d = \gcd(a, b)$

$\implies a = q_1 d, b = q_2 d$, where $q_1,q_2 \in \mathbb{Z}$

Show that $q_1$ and $q_2$ are coprime ...(4)

Substitute $a$ and $b$ in (3), and thus obtain:

$q_1(x_1 - x_0) = q_2(y_0 - y_1)$ ...(5)

Hence, we obtain the following:

- $q_1 \mid q_2(y_0 - y_1)$
- (4) $\implies q_1 \mid (y_0 - y_1)$ ...(6)
- $q_2 \mid q_1(x_1 - x_0)$
- (4) $\implies q_2 \mid (x_1 - x_0)$ ...(7)

---

From (6) and substituting $q_1$ with $\frac{a}{d}$, we get:

$y_1 = y_0 - (a/d)t_1$, where $t_1 \in \mathbb{Z}$ ...(8)

From (7) and substituting $q_2$ with $\frac{b}{d}$, we get:

$x_1 = x_0 + (b/d)t_2$, where $t_2 \in \mathbb{Z}$ ...(9)

---

To prove $t_1 = t_2$, substitute $x_1$ and $y_1$ in (2) using (8) and (9) and simplify (equation (1) will also be used).