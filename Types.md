# Types

## Primitive or Simple
Primitive data types, also known as simple data types in C#, are value types that are built into the C# language.

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
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/built-in-types-table - gives list of simple types.

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
https://medium.com/omarelgabrys-blog/understanding-data-types-in-c-7ccf4547d639
https://github.com/dotnet/docs/issues/7792

#### Integrals
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/integral-types-table

#### Floating-Point
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/floating-point-types-table

#### Boolean

#### Char

#### Enum
https://stackoverflow.com/questions/14561338/enum-is-reference-type-or-value-type

#### Struct
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/structs

### String

## Reference
Reference types are heap-allocated.

## Constants


## Literals
A _literal_ is a source code representation of a value. That is, any text that represents a specific value, such as `true`, `10`, `'c'`, `"hello"` and `null`

See:
 - [C# Standard 7.4.5.1](https://www.ecma-international.org/publications/standards/Ecma-334.htm)
 - https://stackoverflow.com/questions/2066035/in-c-sharp-are-the-terms-primitive-and-literal-interchangeable/2135136#2135136
