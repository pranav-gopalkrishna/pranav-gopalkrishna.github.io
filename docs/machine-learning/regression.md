<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Machine Learning**](https://pranav-gopalkrishna.github.io/machine-learning)

**REGRESSION**

---

**Contents**:

- [Introduction](#introduction)
- [Linear regression](#linear-regression)

---

# Introduction
Regression is about finding the function that maps a numerical input to a numerical output; the inputs and outputs may be scalar or vector, i.e. they may be described as values of a pre-defined variable or a pre-defined list of variables (independent variable(s) for the input, dependent variable(s) for the output). Note that here, one input maps to one output, be it one vector or one scalar. More precisely, we are dealing with a problem of the following form: the $i$-th input $x_i$ that maps to the $i$-th output $y_i$. There exists a linear function $f$ defined on $x_i$ and parameterised by $\theta$, such that $y_i \approx f(x_i, \theta)$. Lastly, there exists noise, i.e. a factor or factors that can affect the output but cannot practically be accounted for, which means $f(x_i, \theta)$ can only be expected to approximate $y_i$.

If $x_i$ is a vector, then we would have $x_i = (x_{1,i}, x_{2,i} ... x_{m,i})$, where $x_{k,i}$ is the $i$-th observed value of the $k$-th independent variable. In most cases, the output is a scalar, but it may also be a vector. Also, $\theta$ may be a simple parameter (i.e. a scalar parameter) or a composite parameter with more than one simple parameter (i.e. a vector parameter). The noise shall be accounted for using the error $\epsilon_i$, which corresponds to the $i$-th observation (i.e. the $i$-th input-output pair). Hence, we have that:

$y_i = f(x_i, \theta) + \epsilon_i$

---

The goal of regression is to estimate the best-performing value of $\theta$.

# Linear regression

Since $f$ here is defined as a linear function, we have that:

$y_i = wx_i^T + b + \epsilon = w_1 x_{1, i} + w_2 x_{2, i} + ... w_k x_{m, i} + b + \epsilon_i$, where:

- $w$ is the row vector of weights, i.e. $w = (w_1, w_2 ... w_k)$
- $x_i$ is the row vector denoting the input, i.e. $x = (x_{1, i}, x_{2, i} ... x_{m, i})$
- $y_i$ is the output, i.e. the target variable's value
- $b$ is the bias term (a single value)
- Hence, the parameter vector is given by $\theta = (w_1, w_2 ... w_k, b)$

**NOTE**: _For the algebra, it is irrelevant whether_ $y_i$ _is scalar or vector._

---

The goal of linear regression is to estimate the best-performing value of $\theta = (w_1, w_2 ... w_k, b)$.