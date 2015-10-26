# RecSharp
RecSharp is an immutable record generator for .NET
Immutable records are similiar to F#'s records or Scala's case classes, but can be used from C# safely.

Here is the sample record definition (You can found it in sample.rcs)
```csharp
namespace Records {
    using System;

    record Test {
        Int32 Id;
        String Name;
		Nullable<Decimal> Amount;
    }
}
```

Generater class Test will have:

* getter-only properties
* constructor with parameters for properties initialization
* Copy() method with optional parameters
* IEquatable<Test> implementation
* overrides os Equals() and GetHashCode()
* == and != operators

Compile it with RecSharpC -i sample.rcs -o Records.dll and reference Records.dll to Your project.
That's it!
