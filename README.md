# software-engineering-glossary
A glossary of terms used in software engineering

https://stackoverflow.com/questions/32290879/meanings-of-declaring-instantiating-initializing-and-assigning-an-object
 - Declare
 
   Introduce a new variable with a type and a name:
   
   ```C#
   int x;
   ```
   
   Note: in C# with will cause a compile time error if `x` is used without being assigned. Or it could be that it can be declared but will only error if it is used without being assigned.
 
 - Assign (or Set?)
 
   Provide a variable with a value.
   
   ```C#
   int x; // Declare x
   x = 5; // Assign 5 to x
   ```
   
 - Instantiate
 
   Create a new instance of a class
   
   ```C#
   var myObject = new MyObject();
   ```
   
   is this also instantiation?:
   
   ```C#
   MyObject myObject; // Declare myObject
   myObject = new MyObject(); // Instantiate myObject with a new MyObject instance
   ```
 
 - Initialise
 
   Declare a variable and assign a value to it
   
   ```C#
   int x = 5
   ```


Minimal Working Example:
https://en.wikipedia.org/wiki/Minimal_Working_Example

## Code structure C#

### Inheritance

Inheritance Hierachy - The total chain of inheritance between the most base class and the most derived class. The root (or base) of the hierarchy is the Object class.
https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance

Subclass (the child class)
Superclass (the parent class)

 - Extends, Derives, Inherits - Terms for how a child class relates to a parent class (concrete or abstract), or a child interface relates to a parent interface.
 - Implements - Term for how a concrete or abstract class relates to an interface. These classes provide an implementation for members defined in the interface.
 - Overrides - Provides a new implementation for an existing method implementation (using `new`) or virtual method.


inheritance is transitive

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/virtual

#### Covariances and Contravariance

Been wrapping my head around covariance and contravariance. These are simplest version I can come up with:

```
interface ICovariance<out T>
{
    T CanOut();
    void CantIn(T value);
}
```

This will have a compile time error on the `T` parameter in `CantIn` as the `out` on the generic type specifies that this type can only be returned, not passed in as a parameter; an example would be `IEnumerable`.

```
interface IContravariance<in T>
{
    T CantOut();
    void CanIn(T value);
}
```

This will have a compile time error on the `T` return from `CantOut` as the `in` on the generic type specified that this type can only be used as a method parameter; an example would be `IComparer`.
Incidentally, a property of type T could not be used in either interfaces, as it both gets and sets T.

Building on this, with covariance, a derived class can be used instead of the base class (a child can be used where a parent is specified; think liskov substitution in SOLID). Where as, with contravariance, a base class can be used instead of the derived class; so in the case of a Comparer, the base class's comparer is used to compare instances of the derived class. This is possible because the derived class has all the members of the base class to allow the base class comparer to work.

### Composition

Prefer composition over inheritance.

 - https://scottlilly.com/c-design-patterns-composition-over-inheritance/
 - https://medium.com/humans-create-software/composition-over-inheritance-cb6f88070205
 - https://stackoverflow.com/questions/49002/prefer-composition-over-inheritance
 - https://www.thoughtworks.com/insights/blog/composition-vs-inheritance-how-choose


### Methods
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods
https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html

Signature

- access modifier
- return type
- name
- parameters (arguments)
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments

Body

# General Terms to Add

 - The term for a line of code, is it Operation, Statement, Expression?
 - Side Effect
   - https://en.wikipedia.org/wiki/Side_effect_(computer_science)
   - https://weblogs.asp.net/dixin/functional-csharp-pure-function
   - https://davesquared.net/2013/04/side-effect-free-csharp.html
   - https://docs.microsoft.com/en-us/cpp/c-language/side-effects?view=vs-2017

# Terms to Add
 - Parsing
 - Santising
 - Interning
   - https://blogs.msdn.microsoft.com/ericlippert/2009/09/28/string-interning-and-string-empty/
   - https://www.c-sharpcorner.com/UploadFile/d551d3/what-is-string-interning/
 - Class Members - https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/members
   - Fields
   - Properties
   - Event handlers
   - Methods
   - anything else?
 - Encapsulation
 - Debugging
   - Replicate or reproduce issue
   - Intermittant issue
   

### Strings

Verbatim string
String Literal
Interpolated String

### Code Presentation

 - Prettify - Split the code across multiple lines to make it more human readable.
 - Minify
 - 

### Code Metrics

 - https://docs.microsoft.com/en-us/visualstudio/code-quality/code-metrics-values?view=vs-2017
