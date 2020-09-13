# Architecture Terms

- Composition Root  
  https://blog.ploeh.dk/2011/07/28/CompositionRoot/
  
- Inversion of Control (IoC)  
  https://martinfowler.com/articles/injection.html
  
- Anti-Corruption Layer  
  Checks that the data coming in from an endpoint is valid, such as item exists in the database, the values are within expected bounds, there is no data duplication, etc.
  This layer may also be used to convert the passed in DTOs into domain models.
  - https://softwareengineering.stackexchange.com/questions/314861/in-ddd-is-validation-application-logic-or-domain-logic
  - https://softwareengineering.stackexchange.com/questions/184464/what-is-an-anti-corruption-layer-and-how-is-it-used
  - https://docs.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer
