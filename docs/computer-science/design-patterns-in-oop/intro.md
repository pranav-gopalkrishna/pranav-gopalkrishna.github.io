[<< Back to **Design Patterns in Object-Oriented Programming**](https://pranigopu.github.io/computer-science/design-patterns-in-oop)

**INTRODUCTION**

---

**Contents**:

- [Definition and purpose of patterns](#definition-and-purpose-of-patterns)
- [Levels of abstraction: What is a "design pattern" here?](#levels-of-abstraction-what-is-a-design-pattern-here)
- [Essential elements of a design pattern](#essential-elements-of-a-design-pattern)
- [Template for describing a design pattern](#template-for-describing-a-design-pattern)
- [Pattern classification criteria](#pattern-classification-criteria)

---

> **Key reference**: DPG4

---

The purpose of this document is to understand:

- The goal of design patterns
- The essentials of a design pattern
    - Clarifies how design patterns achieve their goal
    - Clarifies what to note when learning them
- The template of design pattern description
    - Creates a pattern for learning design patterns
    - Facilitates their retention, comparison and use
- Pattern classification criteria
    - Creates a basis for logically organising patterns
    - Makes it easier to relate patterns to their application

# Definition and purpose of patterns
A pattern is an abstraction that describes a class of similar arrangements. An arrangement is a set of relationships (causal, logical, spatial or temporal) within which exist a set of elements of some kind. A _design pattern_ is a pattern that addresses a class of similar purposes.

"Each pattern _describes a problem_ which occurs over and over again in our environment, and then _describes the core of the solution_ to that problem, in such a way that _you can use this solution a million times over, without ever doing it the same way twice._" — Christopher Alexander (emphases added).

# Levels of abstraction: What is a "design pattern" here?
What is or is not dealt with as a pattern depends on the chosen level of abstraction. At a higher level of abstraction, less abstract patterns may be dealt with as elements that are used in more abstract patterns. Hence, when talking about patterns, it is key to also talk about the level of abstraction in which they would be dealt as patterns and not elements.

<details><summary>Click here for an example.</summary><p>For example, in software design, an array is a pattern, but being less abstract than normal level of abstraction in software design (i.e. writing modules, packages and applications), an array is dealt with more as an element than an arrangement of elements.</p></details>

Hence, to be clear about our level of abstraction, here is an except from the book: "Design patterns are not about designs such as linked lists and hash tables that can be encoded in classes and reused as is. Nor are they complex, domain-specific designs for an entire application or subsystem. _The design patterns in this book are descriptions of communicating objects and classes that are customized to solve a general design problem in a particular context._ **_A design pattern names, abstracts, and identifies the key aspects of a common design structure that make it useful for creating a reusable object-oriented design._**" (emphases added).

# Essential elements of a design pattern
1. Pattern name
    - Naming is the final step of mental integration
    - Lets us deal with the pattern at higher levels of abstraction
2. Problem
    - Context and conditions leading to design challenges
    - It shows what and how a pattern addresses these challenges
3. Solution
    - Conceptual solution to the above-mentioned problem
    - Lays the abstract basis of the pattern and its application
4. Consequences
    - Costs and benefits of the pattern's application
    - Tradeoffs and limitations of the pattern
    - Helps evaluate a pattern's applicability in a use-case

# Template for describing a design pattern
Why a template?

- Lends a uniform structure to the information
- Thus, makes design patterns easier to learn, compare, and use

---

The template is as follows:

- Pattern name and classification
    - Encapsulates the essence of the pattern
    - A good name makes your vocabulary clearer
- Intent
    - Purpose of the pattern
    - The kind of problems it is meant to address
- Also known as
    - Other well-known names of the pattern
    - Helps understand references using these different names
- Motivation
    - Illustrates the design problem
    - Gives the pattern's broad approach with rationale
- Applicability
    - Use-cases
    - Poor design that can be fixed by this pattern
    - Identifying potential use-cases
- Structure
    - Organises classes, objects and their interactions
    - Relates elements to each other
    - Shows request and collaboration sequences between objects
    - Often presented using graphical notation
- Participants
    - Classes and/or objects involved in the pattern
    - Reponsibilities of the above
- Collaboration
    - How participants purposefully interact
- Consequences
    - How the pattern fulfils its intent
    - Results (including tradeoffs) of using the pattern
    - Its role in the system structure
- Implementation
    - Details relevant to pattern implementation
    - This includes pitfalls, tips and techniques
- Sample code
    - Example implementation(s)
- Known uses
    - Example use-cases
- Related patterns
    - Relationship with similar patterns
    - Distinction from similar patterns
    - Good combined uses with other patterns

# Pattern classification criteria
1. **Purpose**
    - **_Creational_** <br> _Deal with object creation_
    - **_Structural_** <br> _Deal with class/object composition_
    - **_Behavioural_** <br> _Deal with class/object interation and responsibility distribution_
2. **Scope**
    - **_Class_**
        - Deal with class relationships
        - Established by inheritance
        - Static, i.e. fixed during compilation
    - **_Object_**
        - Deal with object relationships
        - Modifyable during runtime, hence more dynamic

---

The above two aspects combine as follows:

|  | ? | **Class** | **Object** |
| --- | --- | --- | --- |
| **Creational** | _Create_ | .. via subclasses | ... via other objects |
| **Structural** | _Compose_ | ... via inheritance | ... via elements |
| **Behavioural** | _Organise_ | ... control-flow | ... cooperation |

**NOTE**:

- Create ⇒ Create objects
- Compose ⇒ Compose class/object (based on scope)
- Organise ⇒ Organise control-flow (_class_) and actions (_objects_)

---

Things to note as you study further:

- There are other ways to organise patterns <br> **Example**: _Based on how they reference each other_
- Some patterns are complementary to each other
- Some patterns are alternatives to each other
- Patterns may have similar designs despite different intents