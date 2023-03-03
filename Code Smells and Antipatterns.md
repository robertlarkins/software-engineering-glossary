# Code smells and Antipatterns

- Feature Envy
  - https://refactoring.guru/smells/feature-envy


## Linguistic Smells

Methods that do:
- more than their name says. Eg: `isValid(Guid userId)` that does something more than check if the userId is valid.
- less than their name says.
- the reverse of what their name says.
