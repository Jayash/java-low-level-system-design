# Low level system design implemented in Java

Catalog of popular low level system design principle in Java
 
 ## The SOLID principles of Object Oriented Design include these five principles
 
 https://www.oodesign.com/design-principles.html
 
 - S – Single Responsibility Principle. A Class should have a single responsibility.
    - There should be only one reason for the class to change, reasons can be following
       - Protocol changes
       - Message format changes
       - Communication Security changes etc...
    - For example: suppose we have a user update API which validate user values to be updated, does some business logic and store it in DB 
       - if we write it in one class it will be a violation of this principle
       - we should have controller class to land the request, validator class to pre validate, manager class for business logic and DB(DAO) class to store it in DB
 - O – Open/Closed Principle. Software entities should be open for extension but closed for modification.
    - For example: suppose we have a **abstract** base class and multiple drive class implementing the abstract method of the base class
       - so in here base class is closed for modification and open for extension
       - derived class is open for modification
 - L – Liskov Substitution Principle. Objects in a program should be replaceable by subclasses of same type without any adverse impact.
    - We should be able to substitute base class object with child class object without altering behavioral/characteristics of the program
    - For example: if you have a base class as Rectangle (length, width, calculateArea()) and a derived class as Square
       - if we substitute object of the rectangle class with the object of square class with we are changing the height of the rectangle class
       - and change the height of the rectangle make sense but changing the height of square requires changing width as well
       - above example break this principle instead of square inherits rectangle class a new interface shape(getArea()) should be created
       - both rectangle and square class should inherit shape class and we sustitute and reference of shape class with any object of rectangle and square
 - I – Interface Segregation Principle. Multiple client-specific interfaces are preferable over single generic interface.
    - Client should not be forced to depend upon interfaces that they don't use
    - For example: if there is an interface (Persistance) in which methods findByID, findByName
       - there are 2 derived classes user and order
       - it makes sence for user to have method findByName but doesn't make sense to have findByName for Order
       - this will violates this principle, in designing interfaces we should make sure that only related method should be present
 - D – Dependency Inversion Principle. Program should depend on abstract entities. It should not depend on concrete implementation of an interface.
    - For example: suppose there is a method that is writing to disk and it need some formatter and writter
       - instead of creating the formatter and writter object in the method we should get both from the caller
 
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
