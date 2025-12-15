# Software Design

## Anti-Patterns

 - Postel's Law - also known as the *Robustness Principle*, was used when first developing Internet protocols, but should be avoided now in favour of stronger standards:
   - https://devopedia.org/postel-s-law
   - http://trevorjim.com/postels-law-is-not-for-you/

## Principles

 - Separation of Concerns
   (This explanation needs more work) An area of code should not concern itself with another area of code (eg: concepts, domain, etc.) if it isn't relevant. For example, the repository layer should not know about nor return HTTP status codes, this is the responsibility/concern of the API layer.
 
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

- [Hyrum's Law](https://www.hyrumslaw.com/)
  > With a sufficient number of users of an API, \
    it does not matter what you promise in the contract: \
    all observable behaviors of your system \
    will be depended on by somebody.


## Inheritance and Polymorphism

https://www.infoworld.com/article/3024718/application-development/how-to-implement-polymorphism-in-c.html
