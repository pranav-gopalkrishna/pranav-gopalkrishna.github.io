<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Number Theory**](https://pranav-gopalkrishna.github.io/mathematics/number-theory)

**DIVISION & DIVISIBILITY**

---

**Contents**:

- [Basics](#basics)
  - [Theorem 1: Division algorithm](#theorem-1-division-algorithm)
  - [Theorem 2](#theorem-2)
- [Greatest common divisor (GCD)](#greatest-common-divisor-gcd)
  - [Theorem 1](#theorem-1)
    - [Proof approach](#proof-approach)
  - [Theorem 2](#theorem-2-1)
  - [Theorem 3](#theorem-3)
  - [Euclidean algorithm](#euclidean-algorithm)
  - [Theorem 4](#theorem-4)
  - [Result 1](#result-1)
    - [Proof approach](#proof-approach-1)
  - [Result 2](#result-2)
    - [Proof approach](#proof-approach-2)
- [Relatively prime numbers](#relatively-prime-numbers)
  - [Theorem 1](#theorem-1-1)
    - [Proof approach](#proof-approach-3)
  - [Theorem 2](#theorem-2-2)
    - [Corollary](#corollary)
  - [Theorem 3](#theorem-3-1)
    - [Proof approach](#proof-approach-4)
  - [Euclid's lemma](#euclids-lemma)
    - [Proof approach](#proof-approach-5)
  - [Result](#result)
- [Least common multiple](#least-common-multiple)
  - [Theorem](#theorem)
  - [Proof approach](#proof-approach-6)
- [Prime numbers](#prime-numbers)
  - [Definition of prime numbers](#definition-of-prime-numbers)
  - [Theorem 1](#theorem-1-2)
    - [Corollary 1](#corollary-1)
    - [Corollary 2](#corollary-2)
  - [Theorem 2: Fundamental theorem of arithmetic](#theorem-2-fundamental-theorem-of-arithmetic)
    - [Proof approach](#proof-approach-7)
      - [Iteration 1](#iteration-1)
      - [Iteration 2](#iteration-2)
  - [Theorem 3](#theorem-3-2)

---

# Basics

## Theorem 1: Division algorithm
Given integers $a$ and $b$, there exist unique integers $q$ and $r$ such that:

$a = qb + r$, where $0 \leq r < \mid b \mid $

## Theorem 2
For integers $a$, $b$ and $c$, the following hold true:

- $a \mid 0$, $1 \mid a$ and $a \mid a$
- $a \mid 1$ iff $a = ± 1$
- If $a \mid b$ and $c \mid d$, then $ac \mid bd$
- If $a \mid b$ and $b \mid c$, then $a \mid c$
- $a \mid b$ and $b \mid a$ iff $a = ± b$
- If $a \mid b$ and $b \neq 0$, then $ \mid a \mid \leq \mid b \mid $
- If $a \mid b$ and $a \mid c$, then $a \mid (bx+cy)$, for any integers $x$ and $y$

# Greatest common divisor (GCD)
## Theorem 1
Given positive integers $a$ and $b$, where at least one of them is non-zero, there exist integers $x$ and $y$ such that:

$\gcd(a, b) = ax + by$

### Proof approach

Consider the set of all positive integers that can be expressed as $ax + by$, where $x,y \in \mathbb{Z}$ i.e. consider:

$T = \set{ax + by : ax + by > 0, x,y \in \mathbb{Z}}$

By well-ordering property, T must have a minimum element. Hence,
denote d = min(T). The proof involves two parts:

- Show that $d \mid a$ and $d \mid b$
- Show that if $c \mid a$ and $c \mid b$, $c \leq d$, for any $c$

---

To show the first part, we use the following...

By division algorithm:

- $a = q_1d + r_1$, where $q_1,r_1 \in \mathbb{Z}, 0 \leq r_1 < d$
- $b = q_2d + r_2$, where $q_2,r_2 \in \mathbb{Z}, 0 \leq r_2 < d$

Hence, obtain:

- $r_1 = q_1d - a$
- $r_2 = q_2d - b$

For $r_1$, expand $d = ax_0 + by_0$, and eventually obtain:

- $r_1 = am + bn$, for some $m,n \in \mathbb{Z}$
- $r_1 = a \mid m \mid + b \mid n \mid $

Hence, if $r_1 > 0$, we have that $ \mid r_1 - r_2 \mid \in \mathbb{Z}$.

But $r_1<d \implies r_1 = 0 \implies a = q_1d \implies d \mid a$

Similarly, show $d \mid b$.

---

To show the second part, take $c \mid a$ and $c \mid b$

$\implies c \mid ax + by, \forall \text{ } x,y \in \mathbb{Z}$

$\implies c \mid ax_0 + by_0$ i.e. $c \mid d$

$\implies c \leq d$

## Theorem 2
If a and b are given non-zero integers, then the set...

$T = \set{ax + by : x,y \in \mathbb{Z}}$ (_set of all integer linear combinations of a and b_)

... is precisely the set of all multiples of $\gcd(a, b)$.

## Theorem 3
Let $a$ and $b$ be two integers, at least one of which is non-zero. A positive integer d is the GCD of $a$ and $b$ iff the following conditions are met:

- $d \mid a$ and $d \mid b$
- For any positive integer $c$, $c \mid a$ and $c \mid b$ $\implies c \mid d$

## Euclidean algorithm
This is an iterative process to obtain the GCD of two integers.
Given two integers a and b, by division algorithm repeatedly, we obtain the following:

- $a = q_1 b + r_1; q_1, r_1 \in \mathbb{Z}$ and $0 \leq r_1 \leq b$
- $b = q_2 r_1 + r_2; q_2, r_2 \in \mathbb{Z}$ and $0 \leq r_2 \leq r_1$
- $r_1 = q_3 r_2 + r_3; q_3, r_3 \in \mathbb{Z}$ and $0 \leq r_3 \leq r_2$
  
---

In simple terms, previous divisor becomes next dividend, previous remainder becomes next divisor. The process will terminate when the remainder in the current step is zero. The last non-zero remainder i.e. the current divisor is the GCD of a and $b$.

## Theorem 4
For any integer $k \neq 0$, $\gcd(ka, kb) = \mid k \mid \gcd(a, b)$.

**NOTE**: _Euclidean algorithm is used for the proof._

## Result 1
For $n > 0$, $\gcd(a, a+n) \mid n$

### Proof approach
Let $d = \gcd(a, a+n)$

$d \mid a \implies a = pd$

$d \mid a+n \implies a + n = qd \implies a = qd - n$

Hence, we get:

$pd = qd - n$


## Result 2
$\gcd(qn+r, n) = \gcd(r,n)$

### Proof approach
Let $d = \gcd(qn+r, n)$.

Hence, we must prove the following two statements

- $d \mid r$ and $d \mid n$
- For any $c \mid r$ and $c \mid n$, $d \leq c$

This will show that $d$ is also the GCD of $r$ and $n$.

# Relatively prime numbers
**_Also called coprime integers_**

## Theorem 1
Let a and b be non-zero integers. Then, $a$ and $b$ are coprime iff there exist some integers $x,y \in \mathbb{Z}$ such that $ax + by = 1$.

### Proof approach
Proof of sufficient part uses the facts that, given $d = \gcd(a, b)$, we have that $ax + by = 1$ for some integers $x$ and $y$, and that $d \mid a$ and $d \mid b \implies d \mid (ax + by)$.

## Theorem 2
If $d = \gcd(a,b)$, then $\frac{a}{d}$ and $\frac{b}{d}$ are coprime i.e. $\gcd(a/d, b/d) = 1$.

### Corollary
Let $d = \gcd(a, b)$. Then, by definition:

- $a = q_1 d, q_1 \in \mathbb{Z}$
- $b = q_2 d, q_2 \in \mathbb{Z}$

Then, $q_1$ and $q_2$ are relatively prime.

**NOTE**: _This is because_ $q_1 = \frac{a}{d}$ _and_ $q_2 = \frac{b}{d}$.

## Theorem 3
If $a \mid c$, $b \mid c$, and $\gcd(a, b) = 1$, then $ab \mid c$.

### Proof approach
Proof uses the facts that:

- $ax + by = 1$ for some integers $x$ and $y$
- $a \mid c \implies c = q_1a$
- $b \mid c \implies c = q_2b$
- $c = c \cdot 1 = c(ax + by) = cax + cby$

The idea is to substitute $c$ with its expressions with respect to $a$ and $b$ such that $ab$ becomes a common factor among the terms whose sum equals $c$.

## Euclid's lemma
If $a \mid bc$ and $\gcd(a,b) = 1$, then $a \mid c$.

### Proof approach
Assume $a$ does not divide $b$. Now, consider $a \mid bc$.

$\implies bc = qa$, for some $q \in \mathbb{Z}$

$\implies q = \frac{bc}{a} \in \mathbb{Z}$

But $a$ does not divide $b$, hence:

$\frac{b}{a} \not \in \mathbb{Z} \implies \frac{c}{a} \not \in \mathbb{Z} \implies a \mid c$

## Result

If $\gcd(a,c) = 1$ and $\gcd(b,c) = 1$, then $\gcd(ab,c) = 1$.

# Least common multiple
## Theorem
For positive integers $a$ and $b$, $gcd(a,b) lcd(a,b) = ab$.

## Proof approach
Let $d = \gcd(a, b)$. Show that $m = \frac{ab}{d}$ is a common multiple of $a$ and $b$. Then, show that for any positive common multiple $c$ of $a$ and $b$, $m \leq c$. To show that $m \leq c$, show that $m \mid c$. To show that $m \mid c$, show that $\frac{c}{m} = \frac{c}{\frac{ab}{d}} = \frac{cd}{ab}$ is an integer. To do this, use the facts that:

- $c = q_1a$ and $c = q_2b$, where $q_1,q_2 \in \mathbb{Z}$
- $d = ax + by$ for some $x,y \in \mathbb{Z}$

# Prime numbers
## Definition of prime numbers
By definition, if p is a prime number, we have the following:

- $p$ is non-negative.
- $p$ has exactly two positive factors i.e. $1$ and $p$.

## Theorem 1
If $p$ is a prime number and $p \mid ab$, then either:

- $p \mid a$
- $p \mid b$
- $p \mid a$ and $p \mid b$

**NOTE**: _This is a special case of Euclid's lemma._

### Corollary 1
If $p$ is a prime and $p \mid a_1a_2 ... a_n$, then $p \mid a_i$ for some $i \in \set{1, 2... n}$.

### Corollary 2
If $p, q_1, q_2 ... q_n$ are all prime, and $p \mid q_1q_2 ... q_n$, then $p = q_i$ for some $i \in \set{1, 2... n}$

## Theorem 2: Fundamental theorem of arithmetic
Every positive integer $n > 1$ is either a prime or can be uniquely expressed as a product of primes.

**NOTE**: _Uniqueness implies that a positive integer n can be written only with particular amounts of particular primes i.e. n can be written only using one combination of primes._

### Proof approach
Note that $p$ is positive.

#### Iteration 1
If $n$ is prime, the proof is complete. Hence, assume $n$ is not prime, which means it has non-trivial factors. Consider the largest possible non-trivial factor of $n$, say $d_1$.

$\therefore n = p_1d$, where $p_1 \in \mathbb{Z}^+$

To show must $p_1$ be prime, suppose $p$ is not prime. Then, we can have $p_1 = a_1b_1$, where:

- $a_1,b_1 \in \mathbb{Z}^+$
- $a_1 \neq 1$ and $a_1 \neq p_1$
- $b_1 \neq 1$ and $b_1 \neq p_1$

Hence, $n = a_1b_1d_1 = a_1(b_1d_1)$, where $b_1d_1 > d_1$. Note that $b_1d_1$ must be a non-trivial factor of $n$, since $b < p_1$ and $n = p_1d_1$ This violates the maximality of $d_1$. Hence, $p_1$ must be prime.

#### Iteration 2
If $d$ is prime, the proof is complete. Hence, assume $d$ is not prime, which means it has non-trivial factors. Consider the largest possible non-trivial factor of $n$, say $d_2$.

$\therefore d_1 = p_1 d$, where $p_1 \in \mathbb{Z}^+$

To show must $p_2$ be prime, suppose $p$ is not prime. Then, we can have $p_1 = a_2b_2$, where:

- $a_2,b_1 \in \mathbb{Z}^+$
- $a_2 \neq 1$ and $a_2 \neq p_2$
- $b_2 \neq 1$ and $b_2 \neq p_2$

Hence, $d_1 = a_2b_2d_2 = a_2(b_2d_2)$, where $b_2d_2 > d_2$. Note that $b_2d_2$ must be a non-trivial factor of $d_1$, since $b_2 < p_2$ and $d_1 = p_2d_2$. This violates the maximality of $d_2$. Hence, $p_2$ must be prime.

---

Hence, continue in this manner. Also note that this process must be finite, since $d_k$ will keep reducing for larger $k$ values, and $p_k$ cannot be $1$.

## Theorem 3
There are infinitely many primes.