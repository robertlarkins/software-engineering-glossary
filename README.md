# software-engineering-glossary
A glossary of terms used in software engineering

https://stackoverflow.com/questions/32290879/meanings-of-declaring-instantiating-initializing-and-assigning-an-object

Minimal Working Example:
https://en.wikipedia.org/wiki/Minimal_Working_Example

## Code structure C#

### Inheritance

Inheritance Hierachy - The total chain of inheritance between the most base class and the most derived class. The root (or base) of the hierarchy is the Object class.
https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance

Subclass
Superclass
Extends, Derives, Implements, Child of, parent, 

inheritance is transitive


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
