# Software Design

Domain Driven Design
The code classes should reflect real world objects for that domain. That is, each class should have a real world counterpart.

## Anti-Patterns

 - Postel's Law - also known as the *Robustness Principle*, was used when first developing Internet protocols, but should be avoided now in favour of stronger standards:
   - https://devopedia.org/postel-s-law
   - http://trevorjim.com/postels-law-is-not-for-you/

## Principles

 - Separation of Concerns
 
 - You aren't gonna need it (YAGNI)

 - Law of Demeter (Principle of least knowledge)
 
 - Don't repeat yourself (DRY) - One source of truth within the code.
 
 - Conway's Law
 
 - Levels of Abstraction
 
 - Consistency
 
### SOLID

 - Single Responsibility Principle
 
   https://softwareengineering.stackexchange.com/questions/150760/single-responsibility-principle-how-can-i-avoid-code-fragmentation
   
   There is a second question, as important as "does every class have only one reason to change?" and that is "does every change only affect one class?"
 
 - Open / Closed Principle
 
 - Liskov Substitution Principle
 
 - Interface Segregation Principle
 
 - Dependency Inversion Principle

## Patterns

 - Special Case Pattern
 https://martinfowler.com/eaaCatalog/specialCase.html


## Inheritance and Polymorphism

https://www.infoworld.com/article/3024718/application-development/how-to-implement-polymorphism-in-c.html
