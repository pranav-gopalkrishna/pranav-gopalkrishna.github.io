[<< Back to **Logic**](https://pranav-gopalkrishna.github.io/philosophy/epistemology/logic)

**DEDUCTIVE REASONING**

---

**Contents**:

- [Introduction](#introduction)
- [Types of logical statements](#types-of-logical-statements)
  - [Hypothetical statement](#hypothetical-statement)
    - [Form](#form)
    - [Symbolic representations](#symbolic-representations)
    - [Terminology](#terminology)
    - [Relationships](#relationships)
      - [For "if P then Q"](#for-if-p-then-q)
      - [For "only if P then Q"](#for-only-if-p-then-q)
    - [Translating from informal to formal](#translating-from-informal-to-formal)
  - [Alternative statement](#alternative-statement)
    - [Form](#form-1)
    - [Symbolic representations](#symbolic-representations-1)
    - [Terminology](#terminology-1)
  - [Categorical statement](#categorical-statement)
    - [Form](#form-2)
    - [Terminology](#terminology-2)
      - [Terms of a statement](#terms-of-a-statement)
      - [Subject](#subject)
      - [Predicate](#predicate)
      - [Quantity](#quantity)
      - [Quality](#quality)
      - [Parts of a categorical statement](#parts-of-a-categorical-statement)
      - [Types of a categorical statement/proposition](#types-of-a-categorical-statementproposition)
    - [Notes for conceptual clarity of above terms](#notes-for-conceptual-clarity-of-above-terms)
      - [Quantity](#quantity-1)
        - [Synonymous quantities](#synonymous-quantities)
        - [Always default to particular](#always-default-to-particular)
        - [True for all implies true for some](#true-for-all-implies-true-for-some)
        - ["Some" is not "only some"](#some-is-not-only-some)
      - [Quality](#quality-1)
        - [Quality as logical not semantic or grammatical](#quality-as-logical-not-semantic-or-grammatical)
      - [Subject and predicate](#subject-and-predicate)
        - [Defining subject and predicate as classes](#defining-subject-and-predicate-as-classes)
        - [Specified parts of a whole as subjects](#specified-parts-of-a-whole-as-subjects)
    - [Analysis of propositions](#analysis-of-propositions)
      - [Categorisation based on quantity and quality](#categorisation-based-on-quantity-and-quality)
      - [Distribution](#distribution)
      - [Analysing propositions by distributivity of terms](#analysing-propositions-by-distributivity-of-terms)
        - [A-proposition](#a-proposition)
        - [E-proposition](#e-proposition)
        - [I-proposition](#i-proposition)
        - [O-proposition](#o-proposition)
        - [Summary](#summary)
    - [Relationships](#relationships-1)
      - [For "only S is P"](#for-only-s-is-p)
      - [For different proposition types with identical subjects and predicates](#for-different-proposition-types-with-identical-subjects-and-predicates)
        - [Contradictory](#contradictory)
        - [Contrary](#contrary)
        - [Subcontrary](#subcontrary)
        - [Superimplication and subimplication](#superimplication-and-subimplication)
        - [Summary](#summary-1)
    - [Translating from informal to formal](#translating-from-informal-to-formal-1)
- [Types of arguments and their validations](#types-of-arguments-and-their-validations)
  - [Mixed hypothetical argument](#mixed-hypothetical-argument)
    - [Forms of such an argument](#forms-of-such-an-argument)
      - [Affirming the antecedent](#affirming-the-antecedent)
      - [Denying the antecedent](#denying-the-antecedent)
      - [Affirming the consequent](#affirming-the-consequent)
      - [Denying the consequent](#denying-the-consequent)
      - [Summary](#summary-2)
  - [Pure hypothetical argument](#pure-hypothetical-argument)
    - [Rules for a valid chain](#rules-for-a-valid-chain)
    - [Translating from informal to formal](#translating-from-informal-to-formal-2)
  - [Alternative argument](#alternative-argument)
    - [Weak alternative](#weak-alternative)
    - [Strong alternative](#strong-alternative)
  - [Categorical argument](#categorical-argument)
    - [Immediate inference](#immediate-inference)
      - [Obversion](#obversion)
      - [Conversion](#conversion)
      - [Contraposition](#contraposition)
    - [Syllogism](#syllogism)
      - [Terminology](#terminology-3)
      - [5 rules of syllogistic validity](#5-rules-of-syllogistic-validity)
        - [Rule 1: Three terms rule](#rule-1-three-termsrule)
        - [Rule 2: Distributive middle rule](#rule-2-distributive-middle-rule)
        - [Rule 3: Matching distributivity rule](#rule-3-matching-distributivity-rule)
        - [Rule 4: Two negative premises rule](#rule-4-two-negative-premises-rule)
        - [Rule 5: Negative statement rule](#rule-5-negative-statement-rule)
      - [Validating syllogisms in practice](#validating-syllogisms-in-practice)
      - [General steps for solving a syllogistic argument](#general-steps-for-solving-a-syllogistic-argument)
  - [Translating from informal to formal – general points](#translating-from-informal-to-formal--general-points)

---

# Introduction
Deductive reasoning is a form of reasoning that makes explicit a conclusion implicit, i.e. contained, in the given premises. Hence, deduction is the process of reasoning from universals to either universals or particulars. By its nature, at least one of a deduction’s premises are at least as wide in extent as the conclusion.

---

**Example of a wide conclusion**:

- All men are rational.
- All rational beings have volition.
- ∴ All men have volition.

**Example of a narrow conclusion**:

- All cats are mortal.
- Socrates is a cat.
- ∴ Socrates has mortal.

---

In other terms, a conclusion of a deduction is no wider in extent than at least one of the premises.

# Types of logical statements
## Hypothetical statement
### Form
**if P then Q**

Note that the order of terms is crucial.

### Symbolic representations
If P then Q:

- P → Q
- P ⟹ Q
- P > Q
- P ⊃ Q

### Terminology
- **Antecedent**: P (the condition)
- **Consequent**: Q (conditional conclusion)

### Relationships
#### For "if P then Q"
if P then Q, i.e. P → Q, implies:

- If P happens, Q _necessarily_ follows.
    - **∴ P is a sufficient condition for Q.**
- If Q happens, P may or may not happen.
    - _Nothing in the statement P→Q makes P necessary for Q._
    - But, as Q necessarily follows P, ¬Q _necessarily_ implies ¬P.
    - **∴ ¬Q is a sufficient condition for ¬P.**

Hence, we have that

P → Q ≡ ¬Q → ¬P

#### For "only if P then Q"
only if P then Q, implies:

- P is a necessary condition for Q.
    - **∴ if Q happens, P necessarily follows.**

Hence, we have that

only if P then Q ≡ Q → P ≡ ¬P → ¬Q

### Translating from informal to formal
The essence of any conditional or hypothetical word or phrase is captured by the form "if ... then ..." For example:

- unless P, Q = if not P then Q
- only if P then Q =
    - if Q then P
    - if not P then not Q

## Alternative statement
### Form
**A or B**

Note that this may be strong alternation (i.e. either A or B but not both) or weak alternation (i.e. either A or B or both). Also, note that unlike a hypothetical, the order of terms is irrelevant. Note:

- **Weak alternative**: Either one is true, but both can be true
- **Strong alternative**: Either one is true, but both cannot be true

### Symbolic representations
- A ∨ B (weak alternative)
- A ⊻ B (strong alternative)

### Terminology

- **Alternant**: One of the alternatives offered
- **Weak alternative**: Either one is true, but both can be true.
- **Strong alternative**: Either one is true, but both cannot be true.

## Categorical statement
### Form
q S c P

Here:

- q is the quantifier
- c is the copula
- S is the subject class
- P is the predicate class

### Terminology
A categorical statement is classified with respect to 2 measures:

- **Quantity**
- **Quality**

#### Terms of a statement
A term of a statement is any class present in the statement. Hence, "term" may refer to either the subject or the predicate.

#### Subject
The subject is the being or class of beings about which the statement gives some information. In other words, the subject is what the statement talks about.

#### Predicate
The predicate is the being or class of beings to which the subject is related. Through this relationship, the predicate conveys some information about the subject. In other words, the predicate is what the statement says about the subject.

#### Quantity
Denotes either universality or particularity for a class, i.e. refers to either all members or some members of a class. The quantifier denotes the quantity of the subject class.
#### Quality

Denotes either an affirmative ("is") or a negative ("is not")  relationship between the subject and the predicate. The copula denotes the quality of the statement.

#### Parts of a categorical statement

| Part | Name | Form | Function |
| --- | --- | --- | --- |
| 1   | Quantifier | "all" or "some" | Denotes quantity |
| 2   | Subject |     |     |
| 3   | Copula | "be" or "not to be" | Denotes quality |
| 4   | Predicate |     | Informs about the subject |

#### Types of a categorical statement/proposition

| Type | Name | Form |
| --- | --- | --- |
| A | Universal affirmative | All S is P |
| E | Universal negative | No S is P |
| I | Particular affirmative | Some S is P |
| O | Particular negative | Some S is not P |

### Notes for conceptual clarity of above terms
#### Quantity
##### Synonymous quantities
In ordinary language, there are many ways to refer to universality or particularity. For instance, universality may be unstated yet implied, or stated as "every", "any", "whichever", etc. while particularity may be unstated yet implied, or stated as "many", "most", "a number of", etc. Whatever the word or expression, universality is always translated as "all" and particularity is always translated as "some".

##### Always default to particular
When it is not clear whether a statement denotes a universal or particular quantity, default to the particular "some", since it commits you to the minimum information, thus removing the chance of making wrong assumptions.

##### True for all implies true for some
A universal statement implies a particular one. For example, we know that since all men are mortal, then some men are mortal. In other terms, if something is true for all, then it is true for some.

##### "Some" is not "only some"
Without extra knowledge (beyond the given statements), a statement with a particular quantity (i.e. an I or O-proposition) does not inform us about the rest of the subject class. For example, "some men are liars" does not mean that the rest of the men are not. The rest of the men may be honest, or they may be liars as well. However, this statement alone does not inform us about it. However, when we say "only some men are liars", then we know that the rest of the men are not liars. An "only some" statement tells us about the rest of the class, while a "some" statement by itself does not.

---

**Why "only some" is not a valid quantifier**:

"Only some" is not an essential quantifier, since an "only some" statement is reducible to two "some" statements. More precisely, an "only some" statement is reducible to one I-proposition + one O-proposition having the same predicate. Hence, "only some men are liars" is equivalent to "some men are liars" + "some men are not liars".

Note that a set of statements such as the one above is sufficient to inform us about all the rest of the men, since the law of excluded middle means something is either A or ¬A, but cannot be both. Hence, we know that some men are liars and all the rest of them are not, since there is no category between "liar" and "non-liar".

#### Quality
##### Quality as logical not semantic or grammatical
The affirmative or negative denoted copula is not in terms of the semantic or grammatical relationship but logical relationship. For example,

- "Some men are unintelligent" = Affirmative
- "Some men are not intelligent" = Negative

#### Subject and predicate
##### Defining subject and predicate as classes
In any statement, ordinary or logical, there is always a subject, i.e. what the statement talks about, and a predicate, i.e. what the statement says about the subject. In any case, the subject and predicate can always be defined as classes. This is easy to see for a subject. Now, a predicate assigns some information to the members of the subject class; this is equivalent to relating to the subject class a class of beings to whom that information applies.

##### Specified parts of a whole as subjects
**Singular subjects**:

When the subject consists of a single entity, such as "Socrates" or "Athens", we apply the universal quantifier "all". Hence, we get: "all Socrates" and "all Athens". The reason is that a single entity is a unified whole. If it is irreducible, then it consists only of itself. If not, then it consists of its components. In either case, the universal quantity is the right quantity to apply to singular subjects.

---

**Specified parts of a larger class as subjects**:

In cases where you consider a part or subset of some larger class while not considering the larger class in the argument, the part or subset is the subject class, and universal or particular quantifiers would apply to it.

---

Note that in both cases, you are considering the subject of the statement as a whole rather than a part of a whole, at least logically if not semantically. In other words, even if you describe the subject as a part of a larger class, if your focus is on the part and not the larger class, the part is the subject.

### Analysis of propositions
#### Categorisation based on quantity and quality

| Quantity/Quality | Affirmative | Negative |
| --- | --- | --- |
| Universal | A-proposition <br><br> All S is P | E-proposition <br><br> No S is P |
| Particular | I-proposition <br><br> Some S is P | O-proposition <br><br> Some S is not P |

Note that the E-proposition is not stated in the form "all S is not P," because this is an amphibolous statement that can be interpreted in one of two distinct ways: "no S is P" or "some S is not P".

#### Distribution
A term is distributive if the proposition in which it occurs gives some information about every member of the class designated by that term. A distributive statement tells you something about each and every, i.e. all members of a class. An undistributive statement tells you something about some but not all members of a class (some, not only some).

#### Analysing propositions by distributivity of terms
##### A-proposition
**All S is P**

**_Subject S is distributive._**

However, all S may overlap only with a part and not the whole of P. Hence, some P is S but all P may not be S.

**_Predicate P is undistributive._**

##### E-proposition
**No S is P**

**_Subject S is distributive._**

Also, since no S is P, S does not overlap with P. Hence, P also does not overlap with S. Hence, no P is S.

**_Predicate P is distributive._**

##### I-proposition
**Some S is P**

**_Subject S is undistributive._**

Moreover, some S may overlap only with a part and not the whole of P. Hence, some P is S but all P may not be S.

**_Predicate P is undistributive._**

##### O-proposition
**Some S is not P**

**_Subject S is undistributive._**

Now, note that if some S is not P, then at least one of S, say x, is not P. Hence, we know that x is not P, which means no P is x. Hence, we know that each member of P is at least not some member or members of S.

**_Predicate P is distributive._**

##### Summary
For ease of indication:

- d for distributive term
- u for undistributive term

| Proposition type | Subject | Predicate | Symbolically |
| --- | --- | --- | --- |
| A | d | u | All S(d) is P(u) |
| E | d | d | No S(d) is P(d) |
| I | u | u | Some S(u) is P(u) |
| O | u | d | Some S(u) is not P(d) |

### Relationships
#### For "only S is P"
Only S is P implies:

- Any x that is P can only be S.
- Hence, all P is S.
- Thus, any x that is not S cannot be P.
- Hence, all non-S is non-P.

To summarise,

**Only S is P ≡ All P is S ≡ All non-S is non-P**

#### For different proposition types with identical subjects and predicates
Let S be the common subject and P be the common predicate. Then, we have the following basic propositions:

| Proposition type | Proposition |
| --- | --- |
| A | All S is P |
| E | No S is P |
| I | Some S is P |
| O | Some S is not P |

For these propositions, we have the following relationships...

##### Contradictory
2 propositions are contradictory if:

- truth of either ⇒ falsehood of the other <br> **AND**
- falsehood of either ⇒ truth of the other

Both cannot be true **AND** both cannot be false.

##### Contrary
2 propositions are contrary if:

- truth of either ⇒ falsehood of the other <br> **BUT**
- falsehood of either cannot determine the status of the other

Both cannot be true **BUT** both can be false, i.e. at least one of them is false.

##### Subcontrary
2 propositions are subcontraries if:

- falsehood of either ⇒ truth of the other <br> **BUT**
- truth of either cannot determine the status of the other

Both can be true BUT both cannot be false, i.e. at least one of them is true.

##### Superimplication and subimplication
Proposition X is the superimplicant of proposition Y if:

- truth of X ⇒ truth of Y <br> **BUT**
- falsehood of X cannot determine the status of Y

X is sufficient but not necessary for Y.

**NOTE**: _Here, Y is the subimplicant of X._

Proposition Y is the subimplicant of proposition X if:

- falsehood of Y ⇒ falsehood of X <br> **BUT**
- truth of Y cannot determine the status of X

##### Summary

Key:

- A, E, I and O are the proposition types
- CD: Contradictory
- CN: Contrary
- SC: Subcontrary
- SP: Superimplicant
- SB: Subimplicant

|     | **A** | **E** | **I** | **O** |
| --- | --- | --- | --- | --- |
| **A** |    | CN | SP | CD |
| **E** | CN |    | CD | SP |
| **I** | SB | CD |    | SC |
| **O** | CD | SB | SC |    |

### Translating from informal to formal
Note that:

- Every statement has a subject and predicate
- Any subject or predicate can be defined as a class
- Every informal quantifier is logically either a universal or a particular, i.e. either "all" or "some"
- Every relationship between the subject and the predicate is either affirmative (positive identification) or negative (negative identification)

By these facts, we see that a formal statement can always capture the logical essence of any statement without exception, without losing any logically relevant information.

# Types of arguments and their validations
## Mixed hypothetical argument
Premises are hypothetical and categorical statements, and conclusion is a categorical statement. Its general structure is:

- Hypothetical, i.e. if P then Q
- Categorical affirming/denying the antecedent/consequent
- Conclusion

Note that affirmation or denial is in logical terms, not grammatical terms. The second statement may or may not be in the form of a grammatical negative, but this does not tell us whether or not it is a logical negative. For example:

- If a man is illogical, then he is not happy
- He is happy – denies the consequent "he is not happy"
- ∴ He is illogical

Hence, note that in the hypothetical, the antecedent and consequent terms may include negatives. However, we can validly denote any negative term ¬X as a non-negative term Y = ¬X. Hence, in the presentation of the forms, the symbols P and Q (denoting the antecedent and consequent respectively) shall abstract this detail; P may be some ¬X, and Q may be some ¬Y, but this is not relevant to us.

### Forms of such an argument
#### Affirming the antecedent
Premises:

- if P then Q
- P

Conclusion:

- ∴ Q is definitely true (P is a sufficient condition for Q)
- ∴ ¬Q is definitely false

_VALID form due to determinate conclusion._

#### Denying the antecedent
Premises:

- if P then Q
- ¬P

Conclusion:

- ∴ ¬Q is indeterminate (P is not a necessary condition for Q)
- ∴ Q is indeterminate (We have no reason to conclude this)

_INVALID form due to indeterminate conclusion._

#### Affirming the consequent
Premises:

- if P then Q
- Q

Conclusion:

- ∴ P is indeterminate (P is not a necessary condition for Q)
- ∴ ¬P is indeterminate (We have no reason to conclude this)

_INVALID form due to indeterminate conclusion._

#### Denying the consequent

Premises:

- if P then Q
- ¬Q

Conclusion:

- ∴ ¬P is definitely true (¬Q is a sufficient condition for ¬P)
- ∴ P is definitely false

_VALID form due to determinate conclusion._

#### Summary
Hence, we have that:

- P → Q ≡ ¬Q → ¬P
- X → Y means X is a sufficient condition for Y

Due to the above facts, we know that only affirming the antecedent or denying the consequent give determinate conclusions, and are hence the only valid forms of mixed hypothetical arguments.

## Pure hypothetical argument
Premises and conclusions are all hypothetical statements. This kind of argument is essentially a chain of implications, with one sufficient condition leading to a result that is itself a sufficient condition for another result and so on. Hence, the conclusion is an implication between the first antecedent and last consequent of the chain. The argument’s general structure is:

Premises:

- X1 → X2
- X2 → X3 <br> ...
- Xn-1 → Xn

Conclusion:

- X1 → Xn

### Rules for a valid chain
A valid chain is in essence an unbroken chain. Hence, we have the rules:

- Antecedent of conclusion is antecedent of 1st premise.
- Consequent of conclusion is consequent of last premise.
- Consequent of kth premise is antecedent of (k+1)the premise.

The fallacy of broken chain is when a logical chain of hypotheticals is broken. It is crucial to note the order of the terms in each premise, since the order in a hypothetical obviously determines the direction of implication.

### Translating from informal to formal
- Premises may not be presented in a straightforward manner.
- Watch out for "only if" statements.
- Watch out for statements that, when converted to some equivalent form, would reveal that the chain is in fact valid.

## Alternative argument
Contains one or more alternative premises. Note that there cannot be a pure alternative argument, because alternatives do not by themselves offer one determinate conclusion, neither hypothetically nor categorically.

### Weak alternative
Given a weak alternative A ∨ B, we have that either one is true, but both can also be true. Hence, we only have a determinate conclusion if one of the alternatives is denied. Affirming either alternative gives an indeterminate conclusion, because both alternatives can be true at once.

### Strong alternative
Given a strong alternative A ⊻ B, we have that either one is true, but both cannot be true. Hence, we have a determinate conclusion by either affirming or denying any one alternative.

## Categorical argument
Only contains categorical statements as its premises and conclusions. The two basic forms of categorical arguments:

1.  Immediate inference
2.  Syllogism

### Immediate inference
An immediate inference is an argument wherein the conclusion is drawn from a single premise. By the nature of deduction, such a conclusion is either equivalent to the premise, or a more limited statement than the premise wherein information is lost. The elementary types of immediate inferences are given below.

#### Obversion
The process of changing a proposition into a logically equivalent one having a different quality – i.e. copula is inverted (affirmative to negative, or negative to affirmative).

| Original |     | Obversion |     |
| --- | --- | --- | --- |
| **Type** | **Form** | **Type** | **Form** |
| A | All S is P | E | No S is P |
| E | No S is P | A | All S is non-P |
| I | Some S is P | O | Some S is not non-P |
| O | Some S is not P | I | Some S is non-P |

#### Conversion
The process of changing a proposition into a logically equivalent one by changing the order of the subject and predicate. In other terms, for a categorical statement "q S c P", we obtain an equivalent statement where S becomes the predicate and P becomes the subject.

| **Original** |     | **Conversion** |     |
| --- | --- | --- | --- |
| **Type** | **Form** | **Type** | **Form** |
| A | All S is P | E | \* Some P is S |
| E | No S is P | A | No P is S |
| I | Some S is P | O | Some P is S |
| O | Some S is not P | I | NA |

\* _Converse of an A-proposition is not a true converse, because the conversion results in a more limited statement with less information. This is instead called a "converse by limitation."_

Note that an O-proposition does not have a converse, because, "Some S is not P," can either mean, "No P is S," or "Some P is S,", which are contradictory inferences, neither being even a converse by limitation. Note also that while, "Some non-P is S," is equivalent to, "Some S is not P,", it is not a converse but rather the converse of the obverse – the predicate P is replaced by the new predicate non-P.

#### Contraposition
The process of changing a proposition into a logically equivalent one by obverting the converse of the obverse of the original (i.e. first obverting, then converting the last result, then obverting the last result).

| Original |     | Contraposition |     |
| --- | --- | --- | --- |
| **Type** | **Form** | **Type** | **Form** |
| A | All S is P | E | All non-P is non-S |
| E | No S is P | A | NA |
| I | Some S is P | O | NA |
| O | Some S is not P | I | Some non-P is not non-S |

Here, only the contraposition of an A-proposition is useful to note.

### Syllogism
A deductive argument containing 2 premises and 3 terms, 2 of which are linked in the conclusion as a result of the linking of each of them with the 3rd (also called middle) term in the premises. In other terms, a syllogism is a categorical argument which connects the terms S, M and P in the manner:

- Premise 1: M – P (or P – M)
- Premise 2: S – M (or M – S)
- Conclusion: S – P

Note that the left-side terms are the subjects, while the right side terms are the predicates. A simple example of such an argument is:

- All men are mortal.
- Socrates is a man.
- ∴ Socrates is mortal

#### Terminology

**Minor term is**:

The subject of conclusion. It is called so because usually – by the nature of most such deductive arguments – the conclusion’s subject is the term denoting the least broad, i.e. narrowest class in the argument.

**Minor premise**:

The premise containing the minor term; it is the 2nd premise.

**Major term**:

The predicate of conclusion. It is called so because usually – by the nature of most such deductive arguments – the conclusion’s predicate is the term denoting the least narrow, i.e. broadest class in the argument.

**Major premise**:

The premise containing the minor term – the 1st premise.

**Middle term**:

The 3rd term of the argument, which links the minor and major terms in the premises.

---

Hence, note the order of the argument’s statements:

- Premise 1: Major premise
- Premise 2: Minor premise
- Conclusion

---

Convention dictates the following notation for the terms:

- Minor term: S (subject of the conclusion)
- Major term: P (predicate of the conclusion)
- Middle term: M

#### 5 rules of syllogistic validity
(Credits to: Aristotle)

##### Rule 1: Three terms rule
The argument must have 3 and only 3 terms.

**Justification**:

A 2-premise argument where each premise relates only 2 terms can make a logical inference from at most 3 terms. **_Any more_**, and we have a case where the premises relate 2 distinct pairs of terms, and thus, are disconnected. Hence, the only logical conclusion possible is an immediate inference from one of the premises, making the other redundant. **_Any less_**, and we have 2 premises with the same subjects and predicates. Hence, either we say everything we could about the terms from the 2 premises alone or we say the same thing about the 2 terms twice – in either case, the only logical conclusion possible is an immediate inference from one of the premises, making the other redundant.

---

**Fallacy of 4 terms**:

Having more than 3 terms in a syllogism.

**NOTE 1** Fallacy of 4 terms can also occur due to equivocation, where one term is used in 2 different senses, resulting in 2 logically different terms.

**NOTE 2**: An apparent fallacy of 4 terms may be resolved if the extra terms are merely logical negations or synonyms of some other term of the argument.

##### Rule 2: Distributive middle rule

The middle term must be distributive at least once in the argument – i.e. at least one premise must inform something about every member of the class denoted by the middle term.

**Justification**:

Only if the middle term (M) is distributive can you either

- link all of M to some/all of the minor term, S, or
- link all of M to some/all of the major term, P

Of course, if either of the above are true, then M is distributive by definition; hence any one of these points is the necessary and sufficient condition for M to be distributive. Now, since M is the only term that can relate S to P across premises, the only way to relate S and P in a syllogism is to ensure that S and P do not link to distinct, non-overlapping parts of M. The only way to ensure this within the argument is to either (1) link all of M to some/all of the minor term, S, or (2) link all of M to some/all of the major term, P. In other words, the only way to ensure this within the argument is if M is distributive. Note again that M needs to be distributive in at least one premise – maybe both, but not none.

---

**Fallacy of undistributed middle**:

Fallacy wherein the middle term is not distributed even once. For example:

- All men are mortal.
- All dogs are mortal.
- ∴ All men are dogs.

##### Rule 3: Matching distributivity rule
If a term is distributive in the conclusion, then it must be distributive in the premises.

**Justification**:

- Distributive ⇒ Some information about all members
- Undistributive ⇒ Some information about some – not all –  members

In deduction, you never go from information about some members of a class to information about all members of the class; the essence of deduction is making explicit what is implicit – i.e. contained – in the given premises.

---

**Fallacies**:

**1. Fallacy of illicit minor**:

Minor term is distributed in conclusion but not in premises.

**2. Fallacy of illicit major**:

Major term is distributed in conclusion but not in premises.

##### Rule 4: Two negative premises rule
No conclusion follows from 2 negative premises – negative means either E or O-propositions.

**Justification**:

- Negative of major premise ⇒ Some/all of the major term is outside M
- Negative of minor premise ⇒ Some/all of the minor term is outside M

Hence,

- Some/all of P is not M ⇒  Some/all of P is non-M ... (1)
- Some/all of S is not M ⇒ Some/all of S is non-M ... (2)

But notice that in both (1) and (2), the linking term – which is non-M – is not distributive. Therefore – violating the distributed middle rule – non-M is not a logical, i.e. guaranteed link between S and P, hence no conclusion can be drawn.

_To see it in another way_...

The middle term is disconnected from both terms; all you know about S and P are that they or some part of them is outside M, but there is no logical link between S and P through M.

---

**Fallacy of 2 negatives**:

Fallacy when both premises are negative statements.

##### Rule 5: Negative statement rule
If one premise is negative, then the conclusion must be negative, **AND** if the conclusion is negative, then one premise must be negative.

**Justification**:

If one premise is negative, then either of the following hold:

- Some/all P is outside M and some/all S is inside M
- Vice versa of the above, i.e. some/all S is outside M and some/all P is inside M

Since M is the only link between S and P, and since one of S and P is negatively related to M, the only relationship we can find between S and P through M is negative.

_To see it in another way_...

Since we only know that the part of M related to both S and P is non-overlapping with either some/all of S or some/all of P. Hence, through a link to this part of M, we can only know that some/all of S is non-overlapping with some/all of P. Similarly, if the conclusion shows a negative relationship between S and P, then, since M is the only link between S and P, one of the premises needs to show a negative relationship between either S and M or P and M.

_To see it in another way_...

Since we can only relate S and P through a part of M, if we know that some/all of S is non-overlapping with some/all of P, then it must be that the part of M linking S and P in the premises must be non-overlapping with either S or P.

#### Validating syllogisms in practice
If an argument with 2 premises, 3 terms and a conclusion – i.e. a syllogism –  is invalid, then it cannot be anything but invalid because it violates one of the 4 other rules, and – by the nature of the rules of syllogistic validity – such a violation necessarily means that the argument is invalid.

However, if an argument with 2 premises and a conclusion has more than 3 terms, it may be reducible to a valid syllogism only if the extra terms are logical inverses of one of 3 essential terms. To help convert such an argument to a valid syllogism, we can use one or more immediate inferences on one or more of the argument’s statements.

#### General steps for solving a syllogistic argument
1. Translate informal statements – if any – to formal statements.
2. Identify the terms involved – the subject, predicate and middle terms. <br> **NOTE**: _They are generally easiest to identify from the conclusion._
3. Identify and arrange the premises and conclusions in syllogistic order.
4. Restate the statements as a relation between two classes – the resulting copula must be some form of "to be"
5. If there are more than 3 terms, try to reduce them – if possible – by identifying the logical inverses and using immediate inferences.
6. If the argument is a syllogism – i.e. has only 3 terms – then check its validity by referring to the rules of syllogistic validity

## Translating from informal to formal – general points
Purpose of translation is to let the logical structure stand out clearly, and to make the logical relationships clearer. Doing so enables you to grasp (1) the argument’s essence, (2) the argument’s implications, and (3) the basis of the argument’s validity or invalidity. The translation can and should retain all the logical meaning. Hence, identify the implicit terms or presuppositions