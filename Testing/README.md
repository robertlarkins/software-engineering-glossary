# Testing

https://docs.microsoft.com/en-us/visualstudio/test/unit-test-basics

 - Arrange, Act, Assert (AAA)
 
 - Mocks, Fakes, Spies
 
## Testing Layers

 - Unit testing (Micro testing)
 Unit testing (especially TDD) does three things: reduces bugs, provides living documentation, and works as a code design tool by making the developer think about code structure.
 Unit tests do not find bugs that aren't accounted for, nor will they find bugs that result from how different units interact (this is the domain of integration testing). They are good at defining how code should behave, and confirming that it does behave this way. And if the coverage is sufficient, it is also good at detecting regressions from code refactoring.
 
Does it also provide a specification of the code? http://wiki.c2.com/?TheUnitTestIsTheSpecification
 
https://dzone.com/articles/top-8-benefits-of-unit-testing
 
 - Integration testing
 https://stackoverflow.com/questions/20265369/how-to-do-integration-testing-in-net-with-real-files
 
 - System testing
 
 - Exploratory testing
 
## Testing approaches

 - Manual
 
   - Test driven development (TDD)  
     This is a work flow. https://codurance.com/2015/05/12/does-tdd-lead-to-good-design/
     
     Just some follow up on my question from the developer meeting about TDD while removing features.
   
     What I have found working for me is to:
     1. disable the methods for the features you want to remove.  normally just by commenting the out.
     2. check that it still builds.  if not then it might have a call in a place you did not expect.
     3. if the code is building then run the tests.  you should have a bunch of failing tests.
     4. check the tests that are failing.  If they are testing the feature you were removing then you can remove that test.  If they are testing a feature you are keeping then enable code again till it passes.
     5. once everything is building and passing again delete the methods that were commented out.
 
aim is it take out the feature without breaking other functionality.  if another feature is effected by the removal then refactor the code till that features tests are passing again before removing the code fully.
     
 
   - Behaviour driven development (BDD)
 
 - Automated
 
   - Code coverage
 
### Test Driven Development

An interesting article focusing on why TDD doesn't automatically provide good design. TDD doesn't tell you what good design is, or what should be used. It is an aid to make you think about the code's design (ideally at both the micro and macro levels):
https://codurance.com/2015/05/12/does-tdd-lead-to-good-design/
 
## Testing Types

https://softwareengineering.stackexchange.com/a/223994/249282
https://www.softwaretestinghelp.com/types-of-software-testing/

 - Smoke
   
   http://softwaretestingfundamentals.com/smoke-testing/
 
 - Sanity
 
 - Regression
   A regression is a type of bug where some functionality was working before is no longer working now.
   https://en.wikipedia.org/wiki/Software_regression
 
 - A/B
 
 - Acceptance
   - http://www.extremeprogramming.org/rules/functionaltests.html
   - http://wiki.c2.com/?AcceptanceTest
   - http://wiki.c2.com/?FunctionalTest
 
 - Integration
   - http://wiki.c2.com/?IntegrationTest
 
 - Stress
 
 - System
   - https://www.softwaretestingclass.com/difference-between-system-testing-vs-integration-testing/
   - https://tfortesting.wordpress.com/2013/10/26/difference-between-system-testing-and-system-integration-testing/

 - Characterisation
   - https://michaelfeathers.silvrback.com/characterization-testing
   - http://radify.io/blog/characterisation-tests/
   - http://wiki.c2.com/?CharacterizationTest
   - https://en.wikipedia.org/wiki/Characterization_test
   - https://daedtech.com/characterization-tests/

- Performance
  - Load (https://freeonlineloadtest.com/)
    - Stress testing - Attempts to find the maximum load a system can take before degrading.
    - Soak testing - Measures whether a system can handle a sustained load over a period of time.
  - Latency

- Exploratory/Manual
- Install/Uninstall
- Monkey
  - https://en.wikipedia.org/wiki/Monkey_testing
- Mutation

- Security
  - Vulnerability Assessment
    - https://www.indusface.com/blog/what-is-vulnerability-testing/
- White box
- Black box
- Component (Automated)
- Contract
- Alpha
- Beta
- Ad-hoc
- Accessibility
- Backend
- Branch
  - https://www.geeksforgeeks.org/branch-software-testing/
- Comparison
- Negative testing
- Non-functional
- Functional
- Recovery
- Volume
- End-to-end / flow (automated)
- Exhaustive
- Dependency
- Time zone
- Gorilla
- Compatibility
- Component
- End-to-end
- Equivalence Partitioning
- Example
- Functional

- UI
  - Browser compatibility
  - Automated (Selenium)
  - Usability
  - Mobile
- Happy Path
- Incremental Integration
- Risk-based
- Security
  - Penetration
- Static
- API
  - Automated
- Worflow

- Unit (of behaviour)  
  This is preferred as this testing relates to business requirements rather than being coupled to implementation details  
  (see Unit Testing - Principles, Practices, and Patterns by Vladimir Khorikov)
  - Boundary value  
    This will be determined by the business rules
  
- Property
- Random

## Approaches for Testing

### Sprout Methods
A way for adding new code to a legacy system, but making the code testable.

http://taswar.zeytinsoft.com/learn-the-sprout-method-for-adding-new-functionality/
