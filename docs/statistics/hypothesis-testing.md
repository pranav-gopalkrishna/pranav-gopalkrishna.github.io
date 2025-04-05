<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Statistics**](https://pranav-gopalkrishna.github.io/statistics)

**HYPOTHESIS TESTING**

---

**Contents**:

- [0. Definitions](#0-definitions)
- [1. Introduction](#1-introduction)
  - [1.1. Test statistic](#11-test-statistic)
  - [1.2. Formulating a hypothesis and a test](#12-formulating-a-hypothesis-and-a-test)
    - [1.2.1. Null hypothesis](#121-null-hypothesis)
    - [1.2.2. Distribution of test statistic with respect to $H\_0$](#122-distribution-of-test-statistic-with-respect-to-h_0)
    - [1.2.3. Conditions to reject $H\_0$](#123-conditions-to-reject-h_0)
      - [1.2.3.1. Defining "sufficiently unlikely"](#1231-defining-sufficiently-unlikely)
      - [1.2.3.2. Critical region](#1232-critical-region)
      - [1.2.3.3. $p$-value](#1233-p-value)
      - [1.2.3.4. "One-sided" vs. "two-sided" tests](#1234-one-sided-vs-two-sided-tests)
- [2. Goodness of fit tests](#2-goodness-of-fit-tests)

---

# 0. Definitions
The following are defined and explained in [_Quantifying Probability_](https://pranav-gopalkrishna.github.io/statistics/quantifying-probability.html):

- Population, random process, sample and sample space
- Generalising a population's distribution with a random process
- Generalising random sampling as sampling from a random process
- "Drawing from a distribution"

The idea of maintaining the distribution of a random process across samples is discussed in the file on approximating distributions.

_Henceforth, "distribution" = "probability distribution" unless specified._

# 1. Introduction
Let $\mathbb{P}$ denote a theoretical distribution which models a given random process. Now, consider that we want to either (1) study this distribution through its samples or (2) study the samples of the random process with respect to $\mathbb{P}$ (for example, to try to find out whether these samples are in fact drawn from $\mathbb{P}$). Furthermore, case (1) could be a case wherein we want to either try to (1.1) judge the plausibility of an estimate of a parameter of $\mathbb{P}$, given that the parameter is unknown, or (1.2) judge the plausbility of a possible $\mathbb{P}$ among a family of distributions (considering we know or assume that the random process is distributed by a distribution from this family). In all these cases, we have:

- Theoretical distribution $\mathbb{P}$, which may be:
    - Known
    - Assumed
    - Unknown (with only its family known or assumed)
- Samples from a random process (may or may not be modelled by $\mathbb{P}$), which may be:
    - Known to be drawn from $\mathbb{P}$
    - Assumed to be drawn from $\mathbb{P}$
    - Not certain to be drawn from $\mathbb{P}$

In the case where everything is known, no further work is needed. But in the case where one or more aspects are assumed or unknown or both, we have a reason to test our assumptions and try to discover a relationship between the samples and the theoretical distribution, if one exists. The use of statistical methods to test assumptions about a theoretical distribution with respect to samples or about samples with respect to a theoretical distribution is hypothesis testing. Alternatively, instead of referring to samples we can refer to an "observed random process" from which the samples are drawn; hypothesis testing, then, is the use of statistical methods to test assumptions about the relation between the distribution of an observed random process and a theoretical distribution modelling some random process (which may or may not be the observed random process).

## 1.1. Test statistic
Consider a theoretical distribution $\mathbb{P}$ which models a given random process whose sample space is $X$. A test statistic is an estimator of some parameter of $\mathbb{P}$ or a function of an estimator of some parameter of $\mathbb{P}$, i.e. it is a collection of maps (collection, because there is a map for each value of $n \in \mathbb{N}$) $T^n:X^n \rightarrow \mathbb{R}$ which implements some operation on any tuple of $X^n$. [As with estimators](https://pranav-gopalkrishna.github.io/statistics/approximating-distributions.html#1-estimators), the distribution of the test statistic is a pushforward measure on $\mathbb{P}^n$ through $T^n$, i.e. $T^n_*\mathbb{P}^n$. This can be understood as the distribution of the results of applying a function $T^n$ to $n$ samples each drawn from $\mathbb{P}$.

To test how plausible the observed value of the test statistic is, we need to have some idea about the probability distribution of the test statistic itself. The essence of hypothesis testing is figuring out the test statistic's probability distribution (through exact derivations or approximations), then using this distribution to judge the plausibility of an observed value. We ask, in effect, "Given a set of samples as well as the knowledge and assumptions about the samples, the distribution and their relation, is the observed value of the test statistic too extreme (i.e. too unlikely or implausible)?"

## 1.2. Formulating a hypothesis and a test
### 1.2.1. Null hypothesis
To test some aspect of the relation between the observed samples and a theoretical distribution, we form a hypothesis with respect to the relevant test statistic. The simplest way to form a test hypothesis is to form an assumption of no difference, i.e. to hypothesise that there is no difference (i.e. no distance) between the observed random process' distribution and a given theoretical distribution (known or assumed); this is the null hypothesis ("null" refers to "no difference" or "no distance"), notated as $H_0$. We may formulate $H_0$ more precisely, to, for example, make a statement of no difference or distance between:

- An estimate or assumption and the true value of a parameter
- A random process' distribution and a theoretical distribution

In every case, $H_0$ is the hypothesis, either implicitly or explicitly, that the distance between the true distribution of the observed random process and a given theoretical distribution (known or assumed) is zero. For example, explicitly, $H_0$ may be about the equivalence of an estimate of population mean and the true population mean, but implicitly, $H_0$ holds that the population is distributed by the assumed or estimated distribution whose mean is the given estimated mean.

### 1.2.2. Distribution of test statistic with respect to $H_0$
A test statistic is an estimator or a function of an estimator of a hypothesised theoretical distribution, hence, its assumed or approximated distribution is derived from the hypothesised one. Hence, to be able to judge the plausibility of a test statistic's value with respect to a hypothesised theoretical distribution, we have to assume that the test statistic's distribution is derived from the hypothesised one. Hence, when we test the plausibility of a test statistic's value, it is always under the assumption that the null hypothesis $H_0$ is true, i.e. under the assumption that the hypothesised theoretical distribution accurately models the distribution of the observed random process (from which samples are obtained, through which the test statistic is obtained).

### 1.2.3. Conditions to reject $H_0$
In essence, we reject $H_0$ if our observation is _deemed_ to be _sufficiently unlikely_.

#### 1.2.3.1. Defining "sufficiently unlikely"
We pick a parameter $\alpha \in (0, 1)$, the **confidence level**. This is a proportion of the most likely (i.e. highest probability) values of the test statistic's distribution. Since the proportion is that of a probability distribution, $\alpha$ is also the probability mass (i.e. combined probability) of the $(100 \times \alpha)$% most likely values of the test statistic. For example, if $\alpha = 0.95$, then it refers to the probability mass of the $95$% most likely values of the test statistic.

The smallest interval containing these values is called the **confidence interval**. Using the confidence interval, we can define what we mean by "sufficiently unlikely"; if an observed value of the test statistic lies outside the confidence interval, i.e. outside the range of the $(100 \times \alpha)$% most likely values of the test statistic, the observed value is deemed "sufficiently unlikely". Usually, $\alpha$ is chosen as $0.95, 0.99, 0.999,$ etc.

#### 1.2.3.2. Critical region
This concept is directly derived from the confidence interval. The critical region is the part of the test statistic's distribution apart from the confidence interval, i.e. the part of the test statistic's distribution containing the $(100 \times (1 - \alpha))$% least likely values of the test statistic. The probability mass of these values, i.e. $1 - \alpha$, is called the **significance level**. Hence, if an observed value of the test statistic lies within the critical region, it is deemed "sufficiently unlikely".

#### 1.2.3.3. $p$-value
This is an alternative to the critical region to test the plausibility of an observation, and is a concept that is logically and practically equivalent to using the critical region. The $p$-value is the probability mass of all the values of the test statistic that are at least as extreme (i.e. at least as unlikely) as the observed value. If this probability mass is less than the significance level $1 - \alpha$, then we know that the observed value lies in the critical region and is hence deemed "sufficiently unlikely".

#### 1.2.3.4. "One-sided" vs. "two-sided" tests
_Also called "one-tailed" and "two-tailed"_

**NOTE: Meaning of "side of a distribution"**:<br>Given a suitable point $t \in \mathbb{R}$ on the real line:

- "Left side" is the part of the distribution in $(-\infty, t]$
- "Right side" is the part of the distribution in $[t, \infty)$

Depending on the type of distribution, the critical region, i.e. $(100 \times (1-\alpha))$% of the least likely (i.e. most extreme) values may lie on either only one side of the distribution, or on both sides of the distribution. The parts of the distribution that make up the critical region depend on (1) the shape of the distribution (extent of skewness, concentration of values, etc.) and (2) the confidence level considered. For example, for any symmetric distribution, equally extreme values lie on both sides, leading to the critical region being equally divided on both sides of the distribution. As another example, if the confidence level is low enough, an asymmetric distribution's critical region may lie on both sides of the mean (unequally divided), though for a high enough confidence level, an asymmetric distribution's critical region always lies on only one side of the distribution.

---

**NOTE: Effect of one or two sidedness on** $p$**-value**: 

Given that $F$ is the cumulative probability distribution of the test statistic and given an observed value $x$ of the test statistc, for a one-sided test, $p = \min(1-F(x), F(x))$ (more specficially, $1-F(x)$ for right-sided test, $F(x)$ for left-sided test), whereas for a two-sided test, $p = 2\min(1-F(x), F(x))$. To see why, consider what intervals of values would be considered "at least as extreme" as the observed value.

# 2. Goodness of fit tests
The goodness of fit test of a statistical model (e.g. a theoretical distribution) is a measure of how closely it models a set of observations. In other words, it is a measure of how close the hypothesised theoretical distribution is to the distribution of the observed outcomes of a given observed random process. i.e. the empirical distribution of the observed random process. In essence, a goodness of fit test is a hypothesis test wherein the test statistic is a measure of distance between the theoretical and empirical distributions.

Hence, the focus of a goodness of fit test is in (1) obtaining the probability distribution of the measure of distance being used (which, as in all hypothesis testing, is derived or approximated from the theoretical distribution to which the empirical distribution is being compared), and (2) obtaining the plausibility of the particular measurement of distance observed between the empirical distribution of the observed samples and the theoretical distribution, under the assumption that the null hypothesis is true.