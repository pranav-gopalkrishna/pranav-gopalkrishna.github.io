<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Mathematical Thinking**](https://pranav-gopalkrishna.github.io/mathematics/mathematical-thinking)

**VOCABULARY**

---

**Contents**:

- [Conjunction](#conjunction)
- [Disjunction](#disjunction)
- [Negation](#negation)
- [Implication](#implication)
  - [Introduction](#introduction)
  - [Alternate formulations of implication](#alternate-formulations-of-implication)
  - [Analysing implication](#analysing-implication)
  - [The validity of an implication](#the-validity-of-an-implication)
  - [Extending from implication to conditional](#extending-from-implication-to-conditional)
- [Equivalence](#equivalence)
  - [Introduction](#introduction-1)
  - [Alternative formulations of equivalence](#alternative-formulations-of-equivalence)
  - [Extending from equivalence to biconditional](#extending-from-equivalence-to-biconditional)

---

Here, we shall see the basic language of mathematical thinking.

# Conjunction
The conjuction of two statements $\alpha, \beta$ is to join them using "and" in the sense that does not imply order. Hence, we do not use "and" here in any sense that implies order, e.g. we do not use it as used in the statement "I went to the shop and bought some food"; here, the reverse order, i.e. "I bought some food and went to the shop", does not have the same meaning. A conjunction is denoted by $\land$, i.e. $\alpha \land \beta$ means "$\alpha$ and $\beta$" (wherein the order is irrelevant). Since we order is irrelevant in a conjunction, we have that $\alpha \land \beta = \beta \land \alpha$, i.e. we have that conjunction is commutative.

---

To define conjunction more precisely:

- If $\alpha$ and $\beta$ are both true, then $\alpha \land \beta$ is true
- If $\alpha$ or $\beta$ or both are false, then $\alpha \land \beta$ is false

In other words, $\alpha \land \beta$ is true iff both $\alpha$ and \beta$ are true.

---

A variety of words can be reduced in logic to a conjunction, such as:

- **"but"**, a conjunction that points to some kind of exception
- **"despite"**, a conjunction that points to some kind of exception to an expectation

---

**Truth table of conjunction**:

| $\alpha$ | $\beta$ | $\alpha \land \beta$ |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

# Disjunction
The disjunction of two statements $\alpha, \beta$ is to join them using "or" in the inclusive sense and not the exlusive sense. A statement that uses an inclusive "or" to join $\alpha$ and $\beta$ allows for either one of $\alpha$ and $\beta$ to be true or both to be true, whereas a statement that uses an exclusive "or" to join $\alpha$ and $\beta$ allows for one of $\alpha$ and $\beta$ to be true but not both; hence an exclusive "or" is an inclusive "or" (as in "one of $\alpha$ and $\beta$) along with a conjunction (as in "but not both").

Hence, we see that the inclusive "or" is more fundamental in logic, since (1) it refers to the fundamental quantifier of "some" or "at least one" (i.e. it refers to the case wherein at some or least one of the statements are true), and since (2) an exclusive "or" can be composed using an inclusive "or" (if we also use a conjunction), whereas an inclusive "or" cannot be composed using an exclusive "or". Hence, "or" in mathematics refers only to the inclusive "or". A disjunction is denoted by $\lor$, i.e. $\alpha \lor \beta$ means $\alpha$ or $\beta$ (inclusive "or"). Since order is irrelevant in a disjunction, we have that $\alpha \lor \beta = \beta \lor \alpha$, i.e. we have that disjunction is commutative.

---

To define disjunction more precisely:

- If $\alpha$ or $\beta$ or both both are true, then $\alpha \land \beta$ is true
- If $\alpha$ and $\beta$ are both false, then $\alpha \lor \beta$ is false

In other words, $\alpha \lor \beta$ is true iff at least one of $\alpha$ and \beta$ is true.

---

**Truth table of disjunction**:

| $\alpha$ | $\beta$ | $\alpha \lor \beta$ |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

# Negation
The negation of a statement $\alpha$, denoted by $\lnot \alpha$, is a contradiction of $\alpha$ such that:

- If $\alpha$ is true, $\lnot \alpha$ is false
- If $\alpha$ is false, $\lnot \alpha$ is true

Hence, a negation as defined in logic is a special kind of contradiction; for a statement to be a negation of $\alpha$, it is not sufficient that it merely contradicts $\alpha$, but rather, it must be a statement such that if false, its falsehood is logically contained in the truth of $\alpha$, and if true, its truth is logically contained in the falsehood of $\alpha$. For example, the negation of "I am eating an apple" cannot be "I am eating a banana", since the latter, though contradicting the former, is not a statement whose truth is contained in the falsehood of the former; in other words, the fact that I am not eating an apple does not mean I am eating a banana.

---

Some examples of negation:

- $a \not = b$ means $\lnot (a = b)$

---

**Elaborating on the nature of negation for practical clarity**:

Hence, we can precisely describe negation as follows: a negation of $\alpha$ is the only statement or the only set of statements (ignoring logically [implied](#implication) or [equivalent](#equivalence) statements) that contradicts $\alpha$ or any of its necessary implications (note that contradicting any of $\alpha$'s necessary implications is the same as contradicting $\alpha$; I have given the "necessary implications" part only for practical clarity). For example, let $\alpha$ be the statement "I buy eggs and I come home". What is its negation? Consider: what statement or set of statements contradict $\alpha$ or any of its necessary implications? We have the following:

- "I do not buy eggs"; contradicts $\alpha$'s necessary implication that "I buy eggs"
- "I do not come home"; contradicts $\alpha$'s necessary implication that " I come home"
- Both of the above contradict $\alpha$ both separately and together
- Neither of the above contradictions are logically implied or equivalent to each other
- Hence, neither one by itself is the only statement that contradicts $\alpha$
- Hence, "I do not buy eggs or I do not come home or both" is the negation of $\alpha$

---

**Truth table of negation**:

| $\alpha$ | $\lnot \alpha$ |
| --- | --- |
| 0 | 1 |
| 0 | 0 |

# Implication
## Introduction
An implication from statement $\alpha$ to statement $\beta$ means:

1. If $\alpha$ is true, $\beta$ is true
2. If $\beta$ is false, $\alpha$ is false

In other words, "$\alpha$ implies $\beta$" means:

1. $\alpha$ is a sufficient condition for $\beta$
2. $\beta$ is a necessary condition for $\alpha$

In other words, "$\alpha$ implies $\beta$" means "$\beta$ is necessarily true if $\alpha$ is true".

**KEY POINT**: _A necessary condition is not necessarily a sufficient condition. For example, being able to run is a necessary condition for being able to complete a marathon, but it is by no means a sufficient condition for being able to complete a marathon. On the other hand, being able to complete a marathon is a sufficient condition for being able to run, because the ability to run is contained in the ability to complete a marathon._

## Alternate formulations of implication
"$\alpha$ implies $\beta$" can be reformulated as follows:

- If $\alpha$, then $\beta$
- Only if $\beta$, then $\alpha$
- $\alpha$ is sufficient for $\beta$
- $\beta$ is necessary for $\alpha$

## Analysing implication
We observe so far that an implication's truth depends on two parts:

1. The truth of each statement in the implication
2. One statement is necessitated by the other in the given context

To be necessitated by $\alpha$ within a given context is to be contained in the nature of $\alpha$ within the given context. Note that here, to be contained in $\alpha$ within the given context means to be a selective focus of some facts about $\alpha$ within the given context. The following kinds of things can be necessitated by $\alpha$ within the given context: a fact about $\alpha$, a relationship between facts about $\alpha$, a logical or mathematical derivation from $\alpha$, an effect of the properties of $\alpha$, etc.

For example, let $\alpha$ be "pushing the ball on a smooth surface" and let $\beta$ be "the ball rolling". Within a context involving gravity and not involving any interfering forces, $\alpha$ implies $\beta$, due to (1) causality, which states that nothing acts apart from its nature and its context, (2) the direct observation of contact and change, i.e. the direct observation of interaction, and (3) the absence of other factors within the given context.

As another example, let $\alpha$ be the statement $x > 5$ and let $\beta$ be the statement $x^2 > 20$. We see that within the context of real numbers, $\beta$ relates a well-defined function of $\alpha$ to a well-defined quantity, and within this context, the truth of this relationship is an aspect of the truth of $\alpha$, i.e. if $\alpha$ is true, $\beta$ is contained in $\alpha$ as a selective focus of some facts about $\alpha$ (specifically, some facts about the size of the square of $x$).

## The validity of an implication
_First, some definitions for convenience_...

**Antecedent**:

The causal or sufficient part of the implication.

**Consequent**:

The necessitated part of the implication.

---

Hence, in "$\alpha$ implies $\beta$", $\alpha$ is the antecedent, $\beta$ is the consequent.

---

_Back to the discussion_...

Consider the implication: $\alpha$ implies $\beta$.

If $\alpha$ is true, then the implication can only be true of $\beta$ is also true. Why? Consider: "truth" means correspondence to reality; even a hypothetical truth or truth with respect to a constructed context means correspondence to the real, i.e. logical and/or factual aspects and effects of the elements within the hypothetical or constructed context. Hence, if $\alpha$ is true, then $\alpha$ corresponds to reality, i.e. $\alpha$ exists as fact within the given context. Hence, three metaphysical principles apply to $\alpha$: $\alpha$ is what it is (the law of identity), the attributes of $\alpha$ exist and are non-contradictory (the law of non-contradiction) and the results of the properties and/or actions of $\alpha$ exist neither apart from $\alpha$ nor in contradiction to $\alpha$ (the law of causality). Hence, if $\alpha$ is true, it can only imply something that exists as fact within the given context, i.e. something that is true. Thus, we have the following rows of the truth table:

| $\alpha$ | $\beta$ | $\alpha$ implies $\beta$ |
| --- | --- | --- |
| 1 | 0 | 0 |
| 1 | 0 | 1, if the necessity of $\beta$ given $\alpha$ can be established |

If $\alpha$ is false, however, then it does not correspond to reality, and thus, its implication can only be as a temporary assumption, i.e. in the form "$\alpha$ is false, but assuming $\alpha$ were true, then $\beta$ would be true", like how we assume a statement to be true in order to disprove it in a proof by contradiction. Evidently, since $\alpha$ is false, its implications need not be true. For example, "$\sqrt{2}$ is rational" implies that "$\frac{1}{\sqrt{2}}$ is rational", but both statements are in fact false. However, the implications of a false $\alpha$ need not be false. For example, let $\alpha$ be the statement $\pi = 3$, and let $\beta$ be the statement $\pi + 1 > 3$. Evidently, while $\alpha$ is false, $\beta$ is true and would be necessarily true assuming $\alpha$ were true. Hence, here, "$\alpha$ implies $\beta$" is a true implication. Thus, we have the following rows of the truth table:

| $\alpha$ | $\beta$ | $\alpha$ implies $\beta$ |
| --- | --- | --- |
| 0 | 0 | 1, if the necessity of $\beta$ given $\alpha$ can be established |
| 0 | 1 | 1, if the necessity of $\beta$ given $\alpha$ can be established |

Thus, we see that in every case except where the antecedent is true while the consequent is false, the implication can be true, with its truth depending on whether the necessity of the consequent given the antecedent can be established. Only in the case where the antecedent is true while the consequent is false, we have that no implication is possible, which means an implication in such a case is always false.

## Extending from implication to conditional
Establishing the sufficiency or necessity between two statements is not always easy, especially when automating logic and logical decision-making (e.g. through computers). Furthermore, it is inconvenient to always have to specify that an implication is true provided the sufficiency or necessity can be established. Hence, in practice, for the sake of making the notation as precise and robust as possible, we want a relationship between two statements such that (1) its truth value is the same as the implication between the statements if the implication exists, but (2) its truth value is also defined for when there the implication does not exist. This relationship is called the conditional, denoted by $\implies$. As per the truth table we derived for implication, the truth table of the conditional is as follows:

| $\alpha$ | $\beta$ | $\alpha \implies \beta$ |
| --- | --- | --- |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Hence, in essence, the conditional $\alpha \implies \beta$ poses the following question: assuming you had no knowledge about the possibility of any relationship between $\alpha$ and $\beta$, and given the truth values of $\alpha$ and $\beta$, can $\alpha$ imply $\beta$? Hence, in defining a conditional, we abstract any knowledge we have have about the possibility of any relationship between $\alpha$ and $\beta$. Why do abstract such knowledge because in formal logic and mathematics, we want the vocabulary to be as abstracted from any given context as possible, so that we can apply the vocabulary both precisely and generally to any context.

---

**SIDE NOTE 1**: Knowledge about the possibility of any relationship between $\alpha$ and $\beta$ could change the truth value of the implication "$\alpha$ implies $\beta$", regardless of the truth value of the conditional $\alpha \implies \beta$. For example, if $\alpha$ is "some birds fly" and $\beta$ is "some humans walk", then, though both $\alpha$ and $\beta$ are true, we know there is no implication between $\alpha$ and $\beta$; thus, "$\alpha$ implies $\beta$" is false even though $\alpha \implies \beta$ is true.

**SIDE NOTE 2**: In mathematical practice, the conditional is used for implication, but formally, it is always a conditional, and the implication can be inferred by the context. For example, when we say $x + 1 < 1 \implies x < 0$, we are in fact using the conditional as an implication, and we even read it out as "implies". Hence, in practice, the formal definition is often more of a technicality than a practical consideration.

# Equivalence
## Introduction
In logic, equivalence within a given context between two statements means that, in the given context, the truth value of any one is always the same as the truth value of the other. In other words, two statements are equivalent if (1) imply each other, and thus (2) they are necessary and sufficient conditions for each other. Hence, the equivalence between two statements means that they are both fundamental aspects of the same truth or falsehood. As examples:

- The law of identity is equivalent to the law of non-contradiction
- Perceiving reality is equivalent to being conscious
- $-2 < x < 2$ is equivalent to $x^2 < 4$
- $x \geq 0 \land x \leq 0$ is equivalent to $x = 0$

## Alternative formulations of equivalence
"$\alpha$ is equivalent to $\beta$" means any and all of the following:

- "$\alpha$ implies $\beta$" $\land$ "$\beta$ implies $\alpha$"
- $\beta$ is necessary and sufficient for $\alpha$
- $\alpha$ is necessary and sufficient for $\beta$
- $\alpha$ and $\beta$ necessarily have the same truth values
- " If $\alpha$, then $\beta$" $\land$ "If $\beta$, then $\alpha$"
- $\alpha$ if and only if $\beta$

**NOTE**: "If and only if" is a common phrase for equivalence, and is commonly abbreviated as "iff".

## Extending from equivalence to biconditional
Just as we extended from implication to conditional (see: ["Extending from implication to conditional"](#extending-from-implication-to-conditional)), we extend from equivalence to biconditional, denoted by $\iff$, for the same reasons. Note that, as with a conditional, we want a biconditional since we want a relationship between two statements such that (1) its truth value is the same as the equivalence between the statements if the equivalence exists, but (2) its truth value is also defined for when there the equivalence does not exist. Now, note that just as an equivalence is a conjunction of two different implications between the same statements, a biconditional is a conjunction of two difference conditionals between the same statements. Hence, $\alpha \iff \beta$ is the same as $(\alpha \implies \beta) \land (\beta \implies \alpha)$. Hence, we can derive the truth table of the biconditional as follows:

| $\alpha$ | $\beta$ | $X = \alpha \implies \beta$ | $Y = \beta \implies \alpha$ | $X \land Y = \alpha \iff \beta$ |
| --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 1 |