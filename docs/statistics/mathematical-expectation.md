<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Statistics**](https://pranav-gopalkrishna.github.io/statistics)

**MATHEMATICAL EXPECTATION**

**_Also called simply "expectation" when in a statistical context_**

---

**Contents**:

- [Introduction](#introduction)
- [Mathematical form](#mathematical-form)
- [Properties of mathematical expectation](#properties-of-mathematical-expectation)
  - [1](#1)
  - [2](#2)
  - [3](#3)
  - [4](#4)

---

# Introduction
Mathematical expectation, i.e. expected value, is the measure of the _long-term average_ outcome of a _quantitative random process_ (i.e. a random process that generates quantitative outcomes). In other words, it is the average of outcomes we _expect_ to get in the long-term. Mathematically, it is the sum of all possible outcomes of the random process as weighted by their probabilities of being observed. Evidently, this is an abstract concept that extends from the more concrete concept of the arithmetic mean of observed outcomes of a random process, but it uses the theoretical probability distribution of outcomes instead of empirical observations. In other words, mathematical expectation asks the question: to what value does the arithmetic mean converge to as more observations are made? Note here that the random variable representing the outcomes of the random process can be: a single random variable, a set of random variables (in which case we get a joint expectation), or a function of one or more random variables (which is itself a random variable).

---

**NOTE 1**: In mathematical statistics, a random process can often represented by a random variable. A random variable is a variable that can take one of many (perhaps infinite) values, and its possible values represent the possible outcomes of a certain random process. For the sake of convenience, I shall henceforth be referring to "random variables" instead of "random processes".

**NOTE 2**: The probability distribution of a random variable is the distribution of the probabilities of observing the many (perhaps infinite) values the random variable can take, which is in turn the distribution of the probabilities of observing the many (perhaps infinite) outcomes of a certain random process.

---

**TERMINOLOGY: Random variate vs. random variable**:

A random variate is a possible value of a random variable, and hence represents a particular outcome of a certain random process (whereas a random variable represents the random process as a whole). A random variable and its variates are usually differentiated algebraically by using an uppercase letter for the random variable and the corresponding lowercase letter for its variate. To be more precise, a random variable represents the future value of a random process, whereas a random variate represents the current or past value of a random process. Mathematically, both may be unknown and thus be variables, but the distinction lies in the availability of information that can be expected in a real-life case; random variable is used to represent the case where the information is unavailable, random variate is used to represent the case where the information is/becomes available.

# Mathematical form
The expected value of a random variable $X$ is denoted by $\mathbb{E}(X)$. Let $p$ denote the [probability density function (PDF)](https://pranav-gopalkrishna.github.io/statistics/quantifying-probability.html#probability-density-function) of $X$ (thereby indirectly denoting the probability distribution of $X$). Then, $\mathbb{E}(X) = \int_{-\infty}^{\infty} x p(x) dx$, where $x$ denotes any random variate of $X$. While this formulation has the integration bounds as $(-\infty, \infty)$, in practice, these bounds may be finite on one or both ends based on the [support of the distribution](https://pranav-gopalkrishna.github.io/statistics/approximating-distributions.html#21-support-of-a-distribution).

---

**NOTE**: If $f$ is a function defined on $X$, then:

$\displaystyle \mathbb{E}(f(X)) = \int_{-\infty}^{\infty} f(x) p(x) dx$

The reason is that the probability of observing $x$ from a random process is the same as the probability of observing $f(x)$ after having transformed the outcome of the random process via $f$. Here, $f$ can be seen as a deterministic process applied to the outcomes of the random process, changing not the probability distribution but the [sample space](https://pranav-gopalkrishna.github.io/statistics/quantifying-probability.html#terminology-checkpoint). Note also that $f(X)$ is also a random variable by definition, since it is the outcome of a deterministic process applied to a random variable, thus also acting as a random variable.

# Properties of mathematical expectation
> **Reference**:
> 
> - [_Mathematical Expectation_ from **toppr.com**](https://www.toppr.com/guides/fundamentals-of-business-mathematics-and-statistics/probability/mathematical-expectation/)
> - [_Expectation of Products_](https://library.fiveable.me/key-terms/statistical-inference/expectation-of-products)

---

- Let $X$ and $Y$ be **independent** random variables
- This independence is vital to some of the results shown
- Let $p_X$ and $p_Y$ be their respective PDFs
- Let $p_{X,Y}$ be their joint PDF

**NOTE**: $p_{X,Y}(x, y) = p_X(x)p_Y(y)$ _as_ $X$ _and_ $Y$ _are independent._

## 1
$\mathbb{E}(X + Y) = \mathbb{E}(X) + \mathbb{E}(Y)$

---

**Proof**:

$\mathbb{E}(X + Y)$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} (x + y) p_{X,Y}(x, y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} (x + y) p_X(x)p_Y(y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x p_X(x)p_Y(y) + y p_X(x)p_Y(y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x p_X(x)p_Y(y) dxdy + \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} y p_X(x)p_Y(y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} x p_X(x) (\int_{-\infty}^{\infty} p_Y(y) dy)dx + \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} y p_Y(y)(\int_{-\infty}^{\infty} p_X(x) dx)dy$

$\displaystyle = \int_{-\infty}^{\infty} x p_X(x) (1)dx + \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} y p_Y(y)(1)dy$

(since any PDF integrates to 1 over an infinite range)

$\displaystyle = \int_{-\infty}^{\infty} x p_X(x)dx + \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} y p_Y(y)dy$

$= \mathbb{E}(X) + \mathbb{E}(Y)$

## 2
$\mathbb{E}(XY) = \mathbb{E}(X)\mathbb{E}(Y)$

---

**Proof**:

$\mathbb{E}(XY)$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_{X,Y}(x, y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_X(x)p_Y(y) dxdy$

$\displaystyle = \int_{-\infty}^{\infty} y p_Y(y) (\int_{-\infty}^{\infty} x p_X(x) dx)dy$

$\displaystyle = \int_{-\infty}^{\infty} y p_Y(y) \mathbb{E}(X) dy$

$\displaystyle = \mathbb{E}(X) \int_{-\infty}^{\infty} y p_Y(y) dy$

(since $\mathbb{E}(X)$ is a constant)

$= \mathbb{E}(X) \mathbb{E}(Y)$

## 3
$\mathbb{E}(a + X) = a + \mathbb{E}(X)$ ($a$ is a constant)

---

**Proof**:

$\mathbb{E}(a + X)$

$\displaystyle = \int_{-\infty}^{\infty} (a + x) p_X(x) dx$

$\displaystyle = \int_{-\infty}^{\infty} a p_X(x) + x p_X(x) dx$

$\displaystyle = \int_{-\infty}^{\infty} a p_X(x) dx + \int_{-\infty}^{\infty} x p_X(x) dx$

$\displaystyle = a \int_{-\infty}^{\infty} p_X(x) dx + \int_{-\infty}^{\infty} x p_X(x) dx$

$\displaystyle = a \cdot 1 + \int_{-\infty}^{\infty} x p_X(x) dx$

(since any PDF integrates to 1 over an infinite range)

$= a + \mathbb{E}(X)$

## 4
$\mathbb{E}(aX) = a \mathbb{E}(X)$ ($a$ is a constant)

---

**Proof**:
$\mathbb{E}(aX)$

$\displaystyle = \int_{-\infty}^{\infty} ax p_X(x) dx$

$\displaystyle = a \int_{-\infty}^{\infty} x p_X(x) dx$

$= a \mathbb{E}(X)$