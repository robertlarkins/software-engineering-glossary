# Testing

 - Arrange, Act, Assert (AAA)
 
 - Mocks, Fakes, Spies
 
## Testing Layers

 - Unit testing (Micro testing)
 
 - Integration testing
 
 - System testing
 
 - Exploratory testing
 
## Testing approaches

 - Manual
 
   - Test driven development (TDD)
     This is a work flow.
     
     Just some follow up on my question from the developer meeting about TDD while removing features.
What I have found working for me is to:
1) disable the methods for the features you want to remove.  normally just by commenting the out.
2) check that it still builds.  if not then it might have a call in a place you did not expect.
3) if the code is building then run the tests.  you should have a bunch of failing tests.
4) check the tests that are failing.  If they are testing the feature you were removing then you can remove that test.  If they are testing a feature you are keeping then enable code again till it passes.
5) once everything is building and passing again delete the methods that were commented out.
 
aim is it take out the feature without breaking other functionality.  if another feature is effected by the removal then refactor the code till that features tests are passing again before removing the code fully.
     
 
   - Behaviour driven development (BDD)
 
 - Automated
 
   - Code coverage
 
## Testing Types

https://softwareengineering.stackexchange.com/a/223994/249282
https://www.softwaretestinghelp.com/types-of-software-testing/

 - Smoke testing
   
   http://softwaretestingfundamentals.com/smoke-testing/
 
 - Sanity testing
 
 - Regression testing
 
 - A/B testing
 
 - Acceptance testing
 
 - Stress testing
 
 - System testing
