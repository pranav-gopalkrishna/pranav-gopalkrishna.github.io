<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Number Theory**](https://pranav-gopalkrishna.github.io/mathematics/number-theory)

**CONGRUENCE AND MODULAR ARITHMETIC**

# Properties
## Result 1
A congruence relation, defined as $a\text{R}b \iff a \equiv b \pmod m$ (where $\text{R}$ represents a relation), is an equivalence relation i.e.a relation wherein:

- $\text{R}$ is reflexive i.e. $a\text{R}a$ is true
- $\text{R}$ is symmetrical i.e. $a\text{R}b \iff b\text{R}a$
- $\text{R}$ is transitive i.e. $(a\text{R}b$ and $b\text{R}c) \implies a\text{R}c$

## Result 2
If $a \equiv b \pmod m$ and $c \equiv d \pmod m$, then the following hold true:

1. $a ± c \equiv b ± d \pmod m$
2. $ac \equiv bd \pmod m$

### Proof approach
For each of the above, the proof is easily obtained by using the fact that $a \equiv b \pmod m \implies m \mid (a - b) \implies a = km + b$ for some $k \in \mathbb{Z}$.

## Result 3
If $a \equiv b \pmod m$, then $a^k \equiv b^k \pmod m$ for any positive integer $k$.

---

**NOTE ON CONVERSE**: Converse is not necessarily true. As counterexample, take $a = 2, b = 4, k = 2$ and $m = 3$.

### Proof approach
We can use mathematical induction to prove this.

## Result 4
If $a \equiv b \pmod m$ and $k$ is a constant, then the following hold true:

1. $a ± k \equiv b ± k \pmod m$
2. $ak \equiv bk \pmod m$

---

**NOTE ON CONVERSES**: Converse of (1) is true i.e. $a ± k \equiv b ± k \pmod m \implies a \equiv b \pmod m$. However, converse of (b) is not necessarily true i.e. $ak \equiv bk \pmod m \not \implies a \equiv b \pmod m$. As a counterexample, consider $a = 3, b = 2, k = 2$ and $m = 2$ as a counterexample.

## Result 5
If $ak \equiv bk \pmod m$, then $a \equiv b \pmod m/d$, where $d = \gcd(k, m)$.

### Proof approach
Note that $k = q_1 d$ and $m = q_2 d$, where $q_1,q_2 \in \mathbb{Z}$. Also show that $q_1$ and $q_2$ are coprime. Then, use the fact that:

$ak \equiv bk \pmod m$

$\implies m \mid (ak - bk)$

$\implies ak - bk = cm, where c \in \mathbb{Z}$

(Remember that $q_2 = \frac{m}{d}$)

### Corollary
If $k$ and $m$ are coprime, then $ak \equiv bk \pmod m \implies a \equiv b \pmod m$

## Theorem 1
For any integers $a$ and $b$, $a \equiv b \pmod m$ iff $a$ and $b$ leave the same remainder when divided by $m$.

### First proof approach of the necessary part
Use division algorithm for $a$ and $m$, and $b$ and $m$ (with $m$ always the divisor). Then, use the fact that:

$a \equiv b \pmod m$

$\implies m \mid (a - b)$

$\implies a - b = km$, where $k \in \mathbb{Z}$

Substitute $a$ and $b$ with the expressions obtained using division algorithm. Then, you will obtain the difference of the remainders as an integer multiple of $m$. But note that both remainders are positive integers less than $\mid m \mid$. Hence, they must be less than or equal to the absolute value of any integer multiple of $m$. But these two conditions can only hold if the integer multiple of $m$ here is 0. Hence, the difference of remainders is 0.

### Second proof approach of the necessary part
Use division algorithm for b and m (with m the divisor). So, we would get $b = qm + r$, where $q,r \in \mathbb{Z}$ and $0 \leq r < m$. Then, use the fact that:

$a \equiv b \pmod m$

$\implies m \mid (a - b)$

$\implies a - b = km$, where $k \in \mathbb{Z}$

$\implies a = km + b$

Substitute $b$ with the expression obtained using division algorithm. Then, you will obtain $a = (k+q)m + r$, where $(k+q),r \in \mathbb{Z}$ and $0 \leq r < m$. But by the division algorithm, this means that $r$ is the remainder of the division between $a$ and $m$.

# Equivalence classes using congruence
## Result 1
An equivalence relation $\text{R}$ on a set $S$ partitions the set $S$ into equivalence classes.

# Linear congruence
**_Congruency and modular arithmetic_**

## Theorem 1
The linear congruence $ax \equiv b\pmod n$ has a solution iff $\gcd(a,n) \mid b$.

### Proof approach
Convert the linear congruence into a [linear Diophantine equation](https://pranav-gopalkrishna.github.io/mathematics/number-theory/3-diophantine-equations.html).

## Theorem 2
_(Extension of theorem 1)_

Let $d = \gcd(a,n)$. If $d \mid b$, then the linear congruence $ax \equiv b\pmod n$ has exactly $d$ mutually incongruent (or pairwise incongruent) solutions.

### Proof approach
Use the associated Diophantine equation to obtain the following general solution for $x$, i.e. $x = x_0 + \frac{n}{d}t$, where $x_0$ is a particular solution and $t$ is any integer. Take $t = 0, 1, 2... d-1$, and hence get a list of d solutions. For convenience, let's name this list $S$. You must hence:

- Show these solutions are pairwise incongruent
- Show that any solution outside $S$ is congruent to some element of $S$

## Theorem 3: Chinese remainder theorem
**NOTE**: _This theorem is useful in solving systems of linear congruences, but not strictly a part of linear congruences, and is more part of division and divisibility._

---

**STATEMENT VARIATION 1**:

If we know the remainders of the Euclidean i.e. integer division of an integer x by several integers n_1, n_2... n_k, i.e. if we have...

$r_1 = x \bmod n_1$

$r_2 = x \bmod n_2$

.<br>.<br>.

$r_k = x \bmod n_k$

... then we can uniquely determine the remainder of the division of x by the product of the above integers i.e. by $n_1 n_2... n_k$, **provided that** these integers i.e. $n_1, n_2... n_k$, are pairwise coprime.

---

**STATEMENT VARIATION 2**:

If $n_1, n_2... n_k$ are pairwise coprime, and r_1, r_2... r_k are integers such that $0 \leq r_i < n_i \forall i$, then there exists exactly one integer $x$ such that $0\leq x < N$ (where $N = n_1 n_2... n_k$) and the remainder of the division of $x$ by $n_i$ is $r_i \forall i$, i.e. $x \bmod n_i = a_i \forall i$

---

**STATEMENT VARIATION 3**:

Let $n_1, n_2... n_k$ be integers greater than 1, and let $N = n_1  n_2... n_k$. If $n_1, n_2... n_k$ are pairwise coprime, and $a_1, a_2... a_k$ are any integers (no conditions here), then the following system of linear congruences...

$x \equiv a_1 \pmod n_1$

$x \equiv a_2 \pmod n_2$

.<br>.<br>.

$x \equiv a_k \pmod n_k$

... has a solution (for $x$). Furthermore, if $x_1$ and $x_2$ are two solutions of the above system, then $x_1 \equiv x_2 \pmod N$.

# Fermat's little theorem
Let $p$ be a prime such that $p$ does not divide $a$. Then:

$a^(p-1) \equiv 1 \pmod p$

## Proof approach
**a)**:

Consider 1st $p-1$ multiples of $a$ i.e. $S = a, 2a, 3a... (p-1)a$

---

**b)**:

Prove that the elements of $S$ are mutually incongruent.

---

**c)**:

Show that if elements of S are divided by p, the only remainders possible are $1, 2... (p-1)$

---

**d)**:

Note that steps (b) and (c) $\implies$ remainders for every division between $S$ and $p$ are unique $\implies$

$r_1 = a \bmod p$

$r_2 = 2a \bmod p$

.<br>.<br>.

$r_(p-1) = (p-1) \bmod p$

such that $r_1, r_2... r_(p-1)$ are all distinct.

---

**e)**
Hence, from (d), we obtain:

$p \mid a - r_1$

$p \mid 2a - r_2$

.<br>.<br>.

$p \mid (p-1)a - r_(p-1)$

Hence, we obtain:

$a \equiv r_1 \pmod p$

$2a \equiv r_2 \pmod p$

.<br>.<br>.

$(p-1)a \equiv r_(p-1) \pmod p$

Hence, we obtain:

$(p-1)! a^(p-1) = r_1 r_2...r_(p-1) \pmod p$

But, from (d), we have that:

$\set{r_1, r_2... r_(p-1)} = \set{1, 2... p-1}$

$\implies (p-1)! a^(p-1) \equiv 1 \cdot 2...(p-1) \pmod p$
\
$\implies (p-1)! a^(p-1) \equiv (p-1)! \pmod p$

From the result $uk = vk \pmod w \implies u = v \pmod w/d$, where $d = \gcd(k, w)$. Hence, we get $a^(p-1) \equiv 1 \pmod p$ (since $\gcd((p-1)!, p) = 1$)

# Wilson's theorem
If $p$ is a prime, then:

$(p-1)! \equiv -1 \pmod p$ i.e.

$(p-1)! + 1 \equiv 0 \pmod p$ i.e.

$(p-1)! \equiv (p-1) \pmod p$

## Proof approach
### Setup
Let $p$ be a prime. Define $S = \set{1, 2 ... p-1}$. Since $p$ is prime, all elements of $S$ are coprime to $p$. Now, define $a \in S \implies \gcd(a,p) = 1$, since $a$ is coprime to $p$. Now, consider the linear congruence:

$ax \equiv 1 \pmod p$ ...(1)

Note that $\gcd(a,p) = 1 \mid 1 \implies$ (1) has a solution for $x$. Let $x_0$ be a solution of $(1)$. This implies that:

$ax_0 \equiv 1 \pmod p$ is true

$\implies x = x_0 + \frac{tp}{\gcd(a,p)} = x_0 + tp$ for some $t \in \mathbb{Z}$ ...(2)

**NOTE**: _The above gives the general solution for (1). Note also that the above result is given in the section for linear congruences._

---

Now, note that (2) implies we can always get an $x$ for (1) such that $0 < x < p$. To justify this statement, observe the cases given in the following side note (note that $\text{div}$ means integer division, i.e. obtaining only the integer quotient of a division).

---

_Start of side note_...

**Case 1**:

If $\mid x_0 \mid > p$ and $x_0 < 0$, put $t = (x_0 \text{div} p) + 1$.

**Case 2**:

If $\mid x_0 \mid > p$ and $x_0 > 0$, put $t = -(x_0 \text{div} p)$.

**Case 3**:

If $\mid x_0 \mid < p$ and $x_0 < 0$, put $t = 1$.

**Case 4**:

If $\mid x_0 \mid < p and x_0 > 0$, put $t = 0$

In all the above cases, we would get 0<x<p by choosing the right t.

---

_Back to the main proof_...

Let $x_1$ be a solution of (1) such that $0 < x_1 < p$ i.e. such that $x_1 \in S$. Hence, we have that:

$ax_1 \equiv 1 \pmod p$ is true, where $x_1 \in S$ ...(3)

---

### PART 1: Proving that $a = x_1 \iff (x_1 = 1$ or $x_1 = p-1)$
#### Necessary part
(3) $\implies a^2 \equiv 1 \pmod p$

$\implies p \mid a^2 - 1$

$\implies p \mid (a-1)(a+1)$

Since $a \in S$, we have that:

- If $p \mid (a-1)$, then $a = 1$
- If $p \mid (a+1)$, then $a = p-1$

#### Sufficient part
Note that $(a = 1$ or $a = p-1) \implies a=x_1$. To justify this:

**Consider** $a=1$:

(3) $\implies x_1 \equiv 1 \pmod p, x_1 \in S$

i.e $x_1$ leaves 1 as remainder when divided by $p$

$\implies x_1 = 1 \implies x_1 = a = 1$

**Consider** $a = p-1$

(3) $\implies (p-1)x_1 \equiv 1 \pmod p, x_1 \in S$

$\implies px_1 - x_1 \equiv 1 \pmod p, x_1 \in S$

$\implies p \mid px_1 - x_1 - 1$

Now, note that:

$p \mid px_1 \implies p \mid - x_1 -1$

$\implies p \mid x_1 + 1$

Since $x_1 \in S$, we must have:

$x_1 = p-1$

$\implies x_1 = p \implies x_1 = a = p-1$

### PART 2: The case when $a \neq x_1$
We have seen above that $a=x_1 iff a=1 or a=p-1$. Hence, if $a \neq x_1, a \neq 1$ and $a \neq -1$. Hence, $a \in T = \set{2, 3 ... p-2}$. Now, (3) $\implies$ we can always find a solution for $x$ in (1) such that $x \in S$. But we found that that $a = x \iff (x = 1$ or $x = p-1)$. Hence, equivalently, we have $a \neq x \iff (x \neq 1$ and $x \neq p-1)$. Hence, if a \in T, then $x \in T$. Hence, we can obtain...

$2x_2 \equiv 1 \pmod p$

$3x_3 \equiv 1 \pmod p$

.<br>.<br>.

$(p-2)x_(p-2) \equiv 1 \pmod p$

... where $x_i \in T \forall \text{ } i = 1, 2 ... (p-2)$ ... (\*)

Now, we must prove $x_2, x_3 ... x_(p-2)$ are distinct form each other. To prove this, we can use proof by contradiction, where we assume the following congruences from (\*) hold...

$a_i x_k \equiv 1 \pmod p$

$a_j x_k \equiv 1 \pmod p$

... such that $a_i \neq a_j$

---

Hence, note that $\set{x_2, x_3 ... x_(p-2)} = T$. Also note that $\set{a_2, x_3 ... a_(p-2)} = T$, by definition. Now, also note that $p$ is a prime greater than 3. Hence, $T$, which has $p-3$ elements, has an even number of elements. Hence, we can divide $T$ into two equally sized partitions. Hence, consider the following selection process:

Define a list $L$

Consider $2x_2 \equiv 1 \pmod p$; put 2 and $x_2$ in $L$

Consider $3x_3 \equiv 1 \pmod p$; pnly if $3,x_3 \not \in L$, put both in $L$

Consider $4x_4 \equiv 1 \pmod p$; only if $4,x_4 \not \in L$, put both in L

.<br>.<br>.

Consider $(p-2)x_(p-2) \equiv 1 \pmod p)$; Only if $(p-2),x_(p-2) \not \in L$, put both in $L$

---

Hence, we obtain:

$a_1 x_{q_1} \equiv 1 \pmod p$

$a_2 x_{q_2} \equiv 1 \pmod p$

.<br>.<br>.

$a_k x_{q_k} \equiv 1 \pmod p$

Since we have that...

- If $a_i \neq a_j$, then $x_i \neq x_j$
- $\set{x_1, x_2 ... x_(p-2)} = T$
- $\set{a_2, x_3 ... a_(p-2)} = T$
- $T$ can be evenly divided into two partitions

... we know that:

- $\set{a_1, a_2 ... a_k} \bigcup \set{x_{q_1}, x_{q_2} ... x_{q_k}} = T$
- $\set{a_1, a_2 ... a_k} \bigcap \set{x_{q_1}, x_{q_2} ... x_{q_k}} = \phi$

---

Hence, we get that using the multiplicative property of congruence:

$a_1 x_{q_1} a_2 x_{q_2}... a_k x_{q_k} \equiv 1 \pmod p$

$\implies 2 \cdot 3...(p-2) \equiv 1 \pmod p$

$\implies 2 \cdot 3...(p-2)(p-1) \equiv (p-1) \pmod p$

$\implies (p-1)! \equiv (p-1) \pmod p$

$\implies (p-1)! \equiv -1 \pmod p$