<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Statistics**](https://pranav-gopalkrishna.github.io/statistics)

**ORDER STATISTICS**

---

**Contents**:

- [Introduction](#introduction)
- [Cumulative distribution function for each order statistic](#cumulative-distribution-function-for-each-order-statistic)

---

# Introduction
In statistics, the $k$th order statistic of a statistical sample is equal to its $k$th-smallest value. Hence, order statistics are the values obtained when a sample's values are arranged from smallest to largest. To be precise, if $S = \set{X_1, X_2 ... X_n}$ is a sample, then the order statistics $X_{(1)}, X_{(2)} ... X_{(n)}$ are the values of $S$ ordered such that $X_{(i)} \leq X_{(i+1)}$ for any $i \in \set{1, 2 ... n}$. In other terms, the order statistics are defined as follows:

$X_{(1)}$ = Smallest value in $S$

$X_{(2)}$ = 2nd smallest value in $S$

$X_{(3)}$ = 3rd smallest value in $S$

.<br>.<br>.

$X_{(n)}$ = Largest value of $S$

> **References:
> 
> - [_Order statistic_ from **Wikipedia**](https://en.wikipedia.org/wiki/Order_statistic)
> - [_What are order statistics?_ by Equitable Equations from **YouTube**](https://www.youtube.com/watch?v=gDtkGqLD1R0)

# Cumulative distribution function for each order statistic
For a given order statistic $X_{(r)}$ and a given value $x$, what is the probability that $X_{(r)} \leq x$? In other words, given a sample $S = \set{X_1, X_2 ... X_n}$, what is the probability the $r$th smallest value of $S$ is less than or equal to a given value $x$? This question is based only on our knowledge of the distribution of $X_i$'s, without any knowledge about the actual values they have taken (if we knew that, there would be no question about probability). Hence, this question is asked before a sample is drawn, with the only thing known being the distribution from which samples are drawn. Hence, note that each order statistic $X_{(r)}$ is itself a random variable.

The cumulative distribution function (CDF) of $X_{(r)}$ distributes the order statistic $X_{(r)}$ based on what is known about the distribution from which the sample is drawn. Hence, it gives the answer the question asked above; if $G_r$ is the CDF of the $r$th order statistic $X_{(r)}$, then $G_r(x)$ is the probability that the $r$th order statistic is less than or equal to $x$. The question now is: given that $F$ is the CDF of the distribution from which the sample is drawn, how can we find $G_r$?

---

Let $S = \set{X_1, X_2 ... X_n}$ be the sample.

Let $F$ be the CDF of each $X_i$.

Let $X_{(r)}$ denote the $r$th order statistic.

Let $\mathbb{P}$ be the probability measure.

---

Consider $G_n$:

$G_n(x)$

$= \mathbb{P}(X_{(n)} \leq x)$

$= \mathbb{P}(X_i \leq x \forall \text{ } i \in \set{1, 2 ... n})$

$= \mathbb{P}(X_1 \leq x) \mathbb{P}(X_2 \leq x) ... \mathbb{P}(X_n \leq x)$

$= F(x) F(x) ... F(x)$ (remember: $X_i$'s are not ordered)

$= F(x)^n$

---

Now, consider $G_{n-1}$:

$G_{n-1}(x)$

$= \mathbb{P}(X_{(n-1)} \leq x)$

$= \mathbb{P}($ at least $(n-1)$ of the $X_i$'s $\leq x)$

$= \mathbb{P}($ exactly $(n-1)$ of the $X_i$'s $\leq x$ OR exactly $n$ of the $X_i$'s $\leq x)$

$= \mathbb{P}($ exactly $(n-1)$ of the $X_i$'s $\leq x)$ + $\mathbb{P}($ exactly $n$ of the $X_i$'s $\leq x)$


$= \binom{n-1}{n} F(x)^{n-1} (1 - F(x)) + F(x)^n$

---

Continuing the same logic, we get:

$G_{r}(x)$

$= \mathbb{P}(X_{(r)} \leq x)$

$= \mathbb{P}($ at least $r$ of the $X_i$'s $\leq x)$

$= \sum_{k = r}^{n} \binom{k}{n} F(x)^{k} (1 - F(x))^{n-k}$

It is helpful to think of this as a binomial distribution, where the probability of success is $F(x)$. Then, the above summation is exactly the probability of getting $r$ successes (reference: [_What are order statistics?_ by Equitable Equations from **YouTube**](https://www.youtube.com/watch?v=gDtkGqLD1R0)).

---

**NOTE**: _The probability density function for each order statistic can be obtained by differentiating the CDF._