# Types

## Primitive
Primitive data types are value types that are built into the C# language.

A type can be checked to see if it is primitive by calling its `IsPrimitive` property. For example `typeof(double).IsPrimitive` will return true, while .

In C# the primitive types are:
 - `bool`
 - `byte`
 - `sbyte`
 - `char`
 - `short`
 - `ushort`
 - `int`
 - `uint`
 - `long`
 - `ulong`
 - `float`
 - `double`


https://docs.microsoft.com/en-us/dotnet/api/system.type.isprimitiveimpl?redirectedfrom=MSDN&view=netframework-4.7.2#System_Type_IsPrimitiveImpl
https://docs.microsoft.com/en-us/dotnet/api/system.type.isprimitive?view=netframework-4.7.2

https://medium.com/omarelgabrys-blog/primitive-data-types-in-c-vs-java-5b8a597eef05
https://www.programiz.com/csharp-programming/variables-primitive-data-types


### Value
A value type is a type that holds values rather than being a reference type. They are either stack-allocated or allocated inline in a structure.

In C# a value type is a type that derives from `System.ValueType`. Note: `ValueType` can not be directly inherited, rather,
the C# language provides the `struct` keyword to support the creation of value types.
`enum` is a special case that inherits ValueType, but is a reference type until ).
However, `ValueType` can be used in code for parameter restrictions or checking parameter types, etc.

e.g.: `typeof(double).IsValueType`

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/value-types

#### Double

#### Float

#### Int

#### Byte

### String

## Reference
Reference types are heap-allocated.
