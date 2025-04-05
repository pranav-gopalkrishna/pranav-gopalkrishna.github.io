[<< Back to **Design Patterns in Object-Oriented Programming**](https://pranigopu.github.io/computer-science/design-patterns-in-oop)


**USING DESIGN PATTERNS**

---

**Contents**:

- [How design patterns solve design problems](#how-design-patterns-solve-design-problems)
- [How to select a design pattern](#how-to-select-a-design-pattern)

---

> **Key reference**: DPG4

---

# How design patterns solve design problems
- Identifying the appropriate [objects](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#object) for the purpose
- Determining object granularity
- Specifying [object interfaces](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#interface)
- Specifying [object implementations](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#class) <br> **NOTE**: _An object's implementation is defined by its class_
- [Using reuse mechanisms](https://pranigopu.github.io/computer-science/design-patterns-in-oop/oop-design-principles.html#favor-object-composition-over-class-inheritance)
    - Class inheritance
    - Object composition
- Relating run-time and compile-time structures
    - Object aggregation
    - Object acquaintance
- Making the design adaptible to change
    - Role of design patterns in apps, [toolkits](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#toolkit) and [frameworks](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#framework)

> **Reference**: DGP4 (p. 41-68)

# How to select a design pattern
- Consider [how design patterns solve design problems](#how-design-patterns-solve-design-problems)
- Scan the ["intent" sections](https://pranigopu.github.io/computer-science/design-patterns-in-oop/intro.html#template-for-describing-a-design-pattern)
- Study how patterns interrelate
- Study patterns of similar purposes
- Examine cause of redesign (see DPG4, p. 61)
- Consider what should be variable in your design
    - This is the opposite of examining cause of redesign
    - Consider what you want to be able to change without redesign

> **Reference**: DPG4 (p. 68-69)