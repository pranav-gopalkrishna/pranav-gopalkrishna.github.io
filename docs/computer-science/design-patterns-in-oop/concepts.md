[<< Back to **Design Patterns in Object-Oriented Programming**](https://pranigopu.github.io/computer-science/design-patterns-in-oop)

**CONCEPTS**

---

**Contents**:

- [Binding](#binding)
  - [Static binding](#static-binding)
  - [Dynamic binding](#dynamic-binding)
  - [Key time periods relevant to binding](#key-time-periods-relevant-to-binding)
  - [Performance implications](#performance-implications)
  - [The importance of dynamic binding in OOP](#the-importance-of-dynamic-binding-in-oop)
- [Class](#class)
- [Encapsulation](#encapsulation)
- [Framework](#framework)
- [Inheritance and polymorphism](#inheritance-and-polymorphism)
  - [Inheritance](#inheritance)
    - [Class vs. interface inheritance](#class-vs-interface-inheritance)
  - [Polymorphism](#polymorphism)
- [Interface](#interface)
- [Method](#method)
- [Object](#object)
  - [Design-level definition](#design-level-definition)
  - [Implementation-level definition](#implementation-level-definition)
  - [Linking design-level and implementation-level](#linking-design-level-and-implementation-level)
  - [Conceptual links](#conceptual-links)
- [Toolkit](#toolkit)
- [Type](#type)
- [Additional conceptual topics](#additional-conceptual-topics)
  - [Relating class and interface](#relating-class-and-interface)

---

# Binding
Binding in programming refers to relating (i.e. "binding" or "resolving") identifiers to either their implementations (i.e. stored instructions) or memory locations (i.e. stored data or allocated space for storing data). Note that (1) these identifiers may be identify either data (e.g. variables), data references (e.g. pointers) or functions, and (2) for the machine, "relating" identifiers to their implementations or memory locations means replacing source text with machine-executable instructions or data.

**SIDE NOTE**: _Objects are a kind of data structure, and object methods are a kind of function. Hence, whatever has been given for binding in programming also applies to object-oriented programming._

## Static binding
Example:

```cpp
void my_function(int x, int y) { ... }  // Resolved at compile-time
```

- Resolution occurs at compile-time
- Function calls are linked to _particular_ implementations
- Enables compile-time type and syntax checking
- Implementation typically uses function pointers

## Dynamic binding
_Also called "late" binding, as it is done during runtime._

Example:

```python
def process(obj):
    obj.method()  # Resolved at runtime based on obj's type
```

- Resolution occurs at runtime
- [Method](#method) calls are resolved based on actual object type
- Enables polymorphism and duck typing\*
- Implementation typically uses method virtual tables (vTables)

\* _Duck typing is an approach to resolving an object's type based not on its declared type but on its [interface](#interface) and valid behaviour (i.e. valid object methods). For reference, the name "duck typing" is a reference to the "[duck test](https://en.wikipedia.org/wiki/Duck_test)", a widely cited example of abductive reasoning._

> **Reference**: [_Duck Typing in Python: Writing Flexible and Decoupled Code_ from **RealPython.com**](https://realpython.com/duck-typing-python/)

## Key time periods relevant to binding
1. **Compile-time**: Type checking, overload resolution
2. **Link-time**: Symbol resolution across compilation units
3. **Load-time**: Dynamic library resolution
4. **Runtime**: Virtual method [dispatch](https://www.javatpoint.com/data-structure-tutorial), dynamic typing

## Performance implications
Static binding enables compiler optimisations but reduces flexibility. Dynamic binding offers greater flexibility at performance cost.

## The importance of dynamic binding in OOP
The run-time association of a request to an object and one of its operations is known as **dynamic binding**. Dynamic binding means that issuing a request does not commit you to a particular implementation until run-time. Consequently, you can write programs that expect an object with a particular interface, knowing that any object that has the correct interface will accept the request. Moreover, dynamic binding lets you substitute objects that have identical interfaces for each other at run-time. This substitutability is known as [polymorphism](#polymorphism), and it is a key concept in object-oriented systems.

> **Reference**: DPG4 (p. 45)

# Class
A class is the definition of an [object](#object), i.e. it is a set of stored instructions that specifies (1) the object's identity (i.e. its attributes and methods), and (2) how an object must be created during runtime. Note that an object is called an "instance" of its class, analogous to a concept and its referents; just as one concept (encapsulated by a definition) can have multiple referents, one class can have multiple instances. Hence:

- An object is a class' instance
- A class is an object's implementation

**NOTE**: _Not all classes are meant to be instantiated; e.g. abstract classes._

For further clarity, see how [class is related to interface](#relating-class-and-interface).

# Encapsulation
Encapsulation refers to restricting direct access to an [object](#object)'s attributes and methods. Hence, it "encapsulates", i.e. packages data and procedures, and protects access to them via objects. Hence, it is the key aspect of an object.

---

For more clarity, here are some key points about objects:

- Executes a method when it receives a request from a client
- Requests are the only way to make an object execute a method
- Methods are the only way to change an object's state

Due to these restrictions, an object's attributes and methods are encapsulated, i.e. (1) its attributes and methods _cannot be accessed directly_, i.e. without referring them through the object, and (2) the implementation of an object's state and behaviour is invisible from outside the object.

> **Reference**: DPG4 (p. 42)

# Framework
A framework is a set of cooperating classes that make up a reusable design for a specific class of software. Note that you customise a framework by creating application-specific subclasses of abstract classes from the framework. As examples of frameworks, a framework can be made for _building_:

- Graphical editors for different domains <br> _Such as artistic drawing, music composition and industrial design_
- Compilers for various languages and target machines
- Financial modeling applications

Hence, frameworks:

- Dictate the architecture of your application
- Emphasise design reuse over code reuse <br> _This is in constrast to_ [_toolkits_](#toolkit)

Design patterns vs. frameworks:

- Design patterns are more abstract
    - Only pattern examples (not patterns) can be embodied in code
    - But frameworks can be executed and reused directly
- Design patterns are smaller architectural elements
    - A typical framework contains several design patterns
    - A design pattern never contains several frameworks <br> _It often does not even contain one_
- Design patterns are less specialised
    - Frameworks always have a particular application domain
    - Design patterns are domain-agnostic

> **Reference**: DPG4 (p. 65-68)

# Inheritance and polymorphism
Objects with identical interfaces may have different implementations of the methods that fulfill these requests, often made possible by inheritance and polymorphism. **Inheritance** allows subclasses to implement or override methods from a parent class, while **polymorphism** ensures that objects of different implementations can be treated uniformly when they share the same interface.

## Inheritance
Inheritance is the concept of containing one object's implementation and/or interface as a part of another object's implementation and/or interface. In effect, the latter object "inherits" the attributes and methods of the former object, allowing the latter to reuse and extend the functionality of the former.

### Class vs. interface inheritance
An object's class defines how the object is implemented. The class defines the object's internal state and the implementation of its operations. In contrast, an object's type only refers to its interface, i.e. the set of requests to which it can respond. An object can have many types, and objects of different classes can have the same type.

> **Reference**: DPG4 (p. 49) 

## Polymorphism
Polymorphism is the concept of enabling different objects or functions to behave differently while sharing the same [type](#type) (for objects) or name (for functions). In other words, it enables (1) a single function/method identifier to handle different requests, i.e. different parameters (here, the identifier and the request together identify the function), or (2) different objects to respond differently to the same request made from a shared interface.

---

_Polymorphism simplifies the definitions of clients, decouples objects from each other, and lets them vary their relationships to each other at run-time._ (direct quote from the book)

---

Check [here](#the-importance-of-dynamic-binding-in-oop) for more clarity of polymorphism.

> **Reference**: DPG4 (p. 44-45)

# Interface
A method's name, parameters, and return value are together called the method's **signature**. The set of the signatures of the methods declared by an object is called the object's **interface**. An object's interface characterizes the complete set of requests that can be sent to the object. Any request that matches a signature in the object's interface may be sent to the object.

**NOTE**: _Interfaces can contain other interfaces as subsets._

_Interfaces are fundamental in object-oriented systems, since objects are known only through their interfaces._ There is no way to know anything about an object or make any requests to it without dealing with its interface. An object's interface is not tied to its implementation, i.e., its class. Two objects having different implementations (e.g., derived from different classes or subclasses) can have identical interfaces. For example, both `Dog` and `Cat` classes can implement an `Animal` interface with the method signature `make_sound()`, but have different implementations:

```python
class Animal:
    def make_sound(self):
        pass  # method signature in the interface

class Dog(Animal):
    def make_sound(self):
        print("Bark!")

class Cat(Animal):
    def make_sound(self):
        print("Meow!")
```

Further reading for clarity

- [Inheritance and polymorphism](#inheritance-and-polymorphism) further clarify interfaces
- [Type](#type) a name used to denote a particular interface
- [Relating class and interface](#relating-class-and-interface)

> **Reference**: DPG4 (p. 44-45)

# Method
Also called "operation"\*.

A method is a functions whose access is managed by an object. Hence, a method is always _of an object_. [Encapsulation](#encapsulation) further clarifies the role of a method.

---

\* _This term is less common and has other meanings outside OOP._

# Object
## Design-level definition
**_An object is a well-defined representation_**\* **_of a functional unit_** (i.e. a unit that can act and interact as a well-defined whole, e.g. an entity, a phenomenon, a functionality, etc.). To this end, an object represents both the state and the behaviour of the functional unit.

\* _A representation of X is a mapping between X and some other entity or system Y, done such that, within a specific context, changes to Y exactly map to changes to X and vice versa._

---

In essence, an object models a functional unit with both:

- Properties (its state/data)
- Capabilities (its behavior/operations)

For encapsulating usage, an object presents an interface that:

- Hides internal implementation details
- Exposes only the operations other code needs
- Makes clear what the object can do and how to interact with it

For abstracting implementation details, it manages:

- The integrity of its internal state
- The rules and logic for operating on that state
- Its interactions with other objects

---

_Hence, an object is not just a way to organise code, but a design tool for breaking down complex systems into manageable components that map to real concepts in the problem domain._

## Implementation-level definition
_Given how it is implemented with our existing technology._

**_An object is a data structure that stores and gives access to (1) data or references to data and (2) the procedures designed to operate on these data_**. These data and references to data are called "attributes", and procedures are called "[methods](#method)". The values of its attributes are together the object's state, and the execution of the object's methods (i.e. the object's "actions") is the object's behaviour. An object is implemented through a [class](#class).

**NOTE**. _The purpose of an object is to organise and manage access to data and procedures with respect to a unifying idea or purpose (e.g. an entity, a phenomenon, a functionality, etc.); typically, this is an idea or purpose that ties into the broader purpose of a module or application._

## Linking design-level and implementation-level
The technical implementation of an object (at least the way it has been done so far) uses data structures, but in a conceptual design/architecture context, an object is about [encapsulation](#encapsulation) and abstraction rather than data organisation. As analogy, describing a car as "a collection of metal parts" gives the truth but does not give the essence of what a car is and does. That said, to be precise about its implementation, an object is realised as a data structure that contains:

- Memory locations for instance variables
- References to methods (typically via a virtual table (vTable))
- Metadata about the object's [type](#type) (i.e. the name of its [interface](#interface))

## Conceptual links
For greater clarity, see:

- [>>](#encapsulation) Encapsulation
- [>>](#method) Method
- [>>](#class) Class
- [>>](#interface) Interface

# Toolkit
A toolkit is a library, i.e. a set of related and reusable classes designed to provide useful, general-purpose functionality. They let you as an implementer avoid recoding common functionality. Examples of toolkits: a set of collection classes for (1) lists, associative tables, stacks, (2) visualisation (e.g. Matplotlib in Python).

**NOTE**: _Toolkits do not impose a particular design on your application and just provide functionality that can help your application do its job; toolkits are design-agnostic_ **_Toolkits emphasise code reuse_**.

> **Reference**: DPG4 (p. 65)

# Type
A **type** is a name used to denote a particular [interface](#interface). E.g. an object has the type "Rectangle" if it accepts all requests for the methods defined in the interface named "Rectangle". This name may just be the name of the object's class or some ancestor class of its class, but not necessarily, since one object may have more than one type (i.e. it can be interacted with via more than one interface), and different objects with very different identities (possibly even unrelated class hierarchies) can share a type. A type is a **subtype** of another type (its **supertype**) if the interface it refers to contains the interface of its supertype. Often, a subtype is said to "inherit" the interface of its supertype.

---

---

# Additional conceptual topics
## Relating class and interface
There is a close relationship between class and interface. Because a class defines the operations an object can perform, it also defines the object's type. When we say that an object is an instance of a class, we imply that the object supports the interface defined by the class.

> **Reference**: DPG4 (p. 49) 