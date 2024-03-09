# Low level system design implemented in Java

Catalog of popular low level system design principle in Java
 
 ## The SOLID principles of Object Oriented Design include these five principles
 
 https://www.oodesign.com/design-principles.html
 
 - S – Single Responsibility Principle. A Class should have a single responsibility.
    - There should be only one reason for the class to change, reasons can be following
       - Protocol changes
       - Message format changes
       - Communication Security changes etc...
 - O – Open/Closed Principle. Software entities should be open for extension but closed for modification.
 - L – Liskov Substitution Principle. Objects in a program should be replaceable by subclasses of same type without any adverse impact.
    - We should be able to substitute base class object with child class object without altering behavioral/characteristics of the program 
 - I – Interface Segregation Principle. Multiple client-specific interfaces are preferable over single generic interface.
    - Client should not be forced to depend upon interfaces that they don't use
 - D – Dependency Inversion Principle. Program should depend on abstract entities. It should not depend on concrete implementation of an interface.
 
 ## Encapsulate what varies
 
 - "Varies" here means "may change over time due to changing requirements". This is a core design principle: To separate and isolate pieces of code or data which may have to change separately in the future. If a single requirement changes, it should ideally only require us to change the related code in a single place. But if the code base is badly designed, i.e. highly interconnected and logic for the requirement spread out in many places, then the change will be difficult and have a high risk of causing unexpected effects.
 - Factory pattern is build upon this principle, here Object factory class can change over time due to changing requirement.
 
 ## Favor composition over inheritance
 
 - Prefer composition over inheritance as it is more malleable / easy to modify later, but do not use a compose-always approach. With composition, it's easy to change behavior on the fly with Dependency Injection / Setters. Inheritance is more rigid as most languages do not allow you to derive from more than one type.
 - Strategy pattern is build upon this principle.
 
 ## Loose coupling
 
 - Loose coupling is an approach to interconnecting the components in a system or network so that those components, also called elements, depend on each other to the least extent practicable. Coupling refers to the degree of direct knowledge that one element has of another.
 
 ## Program to interfaces
 
 - Coding to interfaces is a technique to write classes based on an interface; interface that defines what the behavior of the object should be. It involves creating an interface first, defining its methods and then creating the actual class with the implementation.
 - Template pattern is build upon this principle.
