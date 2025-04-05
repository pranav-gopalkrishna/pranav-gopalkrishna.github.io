[<< Back to **Design Patterns in Object-Oriented Programming**](https://pranigopu.github.io/computer-science/design-patterns-in-oop)

**OOP DESIGN PRINCIPLES**

---

- [Program to an interface, not an implementation](#program-to-an-interface-not-an-implementation)
- [Favor object composition over class inheritance](#favor-object-composition-over-class-inheritance)
  - [The issue with inheritance](#the-issue-with-inheritance)
  - [The advantage of composition](#the-advantage-of-composition)
  - [Interplay between inheritance and composition](#interplay-between-inheritance-and-composition)
- [Distinguish between runtime and compile-time structures](#distinguish-between-runtime-and-compile-time-structures)

---

# Program to an interface, not an implementation
Implementation reuse is only a part of the value of inheritance; the other part is an inheritance's ability to define (i.e. implement through classes) a range of objects with identical [interfaces](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#interface), usually by inheriting from the same abstract class. This is valuable as it enables [polymorphism](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#polymorphism).

Inheritance can be used such that all classes derived from an abstract class share its interface. This implies that a subclass merely adds or overrides methods and does not hide the parent class' methods. Then, all these subclasses can respond to the requests in the interface of this abstract class, making them all [subtypes](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#type) of the abstract class. The benefits of manipulating objects only through an interface defined by abstract classes are:

1. Clients stay unaware of the specific types of objects they use <br> ... _as long as the objects adhere to the interface that clients expect_
2. Clients stay unaware of classes implementing these objects <br> ... _only knowing about the abstract class(es) defining the interface_

_This reduces implementation dependencies between subsystems._

Hence, the principle.

---

Hence, in practice, do not declare variables to be instances of particular concrete classes, but rather, deal with them only through an interface defined by an abstract class. This is a common theme of the design patterns in DPG4. In particular, relational patterns ensure that your system is written in terms of interfaces, not implementations (i.e. classes/subclasses).

---

> **Reference**: DPG4 (p. 51-52)

# Favor object composition over class inheritance
The two most used techniques for reusing functionality in object-oriented systems are (1) class inheritance (white-box reuse, since everything within the parent class is visible to subclasses) and (2) object composition (black-box reuse, since objects are [encapsulated](https://pranigopu.github.io/computer-science/design-patterns-in-oop/concepts.html#encapsulation) and thus their implementations are invisible to each other).

## The issue with inheritance
Inheritance brings implementation dependency between the parent class and its subclasses; any change to the parent class forces changes in subclasses. Hence, if any aspect of the inherited implementation is not appropriate for a new problem domain, the parent class must be rewritten or replaced by something more appropriate, which can lead to rewriting or replacing its subclasses as well, which can be problematic when you want to reuse some subclasses further. Evidently, such dependency limits flexibility and reusability.

## The advantage of composition
- Objects are interchangeable in runtime <br> _This enables dynamic adaptations in functionality_
- Fewer implementation dependencies <br> _Since functionality is reused via interfaces, not creating new subclasses_
- Classes remain encapsulated and focused
- Class hierarchies remain manageable

## Interplay between inheritance and composition
If possible, do not create new components to achieve reuse and try to get as much of the functionality you need just by assembling existing components through object composition. But this is rarely enough, since the set of existing components is never quite rich enough in practice. Reuse by inheritance makes it easier to make new components that can be composed with old ones. Thus, inheritance and object composition work best together.

---

> **Reference**: DPG4 (p. 54)

# Distinguish between runtime and compile-time structures
An object-oriented program's runtime structure often bears little-to-no resemblance to its code structure. The code structure is frozen at compile-time, consisting of classes in fixed inheritance relationships. In contrast, a program's runtime structure consists of rapidly changing networks of inter-communicating objects. _In fact, the two structures are largely independent._ Trying to understand one from the other is like trying to understand the dynamism of living ecosystems from the static taxonomy of plants and animals, and vice versa.

> **Reference**: DPG4 (p. 59)