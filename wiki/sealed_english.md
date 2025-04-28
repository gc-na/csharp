<!--
Meta Description: # Understanding the "sealed" Keyword in C# ## Synopsis The `sealed` keyword in C# is a powerful modifier that prevents a class from being inherited. T...
Meta Keywords: class, sealed, from, can, public
-->

# Understanding the "sealed" Keyword in C#

## Synopsis
The `sealed` keyword in C# is a powerful modifier that prevents a class from being inherited. This feature is crucial for enforcing design constraints and ensuring specific behaviors in class hierarchies.

## Documentation
In C#, the `sealed` keyword is used to declare a class that cannot be further inherited. When a class is marked as `sealed`, it signifies that this class is the final class in its inheritance chain. This means that no other class can derive from a sealed class, which can be beneficial for various reasons, including performance optimization and design clarity.

### Purpose
- **Prevent Inheritance**: By sealing a class, you can prevent other classes from deriving from it, making your design more robust.
- **Enhance Performance**: The runtime can optimize calls to sealed classes, as it knows the class's method layout will not change.

### Usage
To use the `sealed` keyword, simply prefix your class definition with `sealed`. For example:

```csharp
sealed class MySealedClass
{
    // Class members go here
}
```

### Details
- A `sealed` class can still implement interfaces and contain methods, properties, and events.
- You can seal a class that is already derived from another class, but it must be done at the derived class level.
- If a class is marked as `sealed`, its members can still be overridden if they are marked as `virtual` in a base class, but only within the same class.

## Examples

### Basic Example
Here's a straightforward example of a sealed class:

```csharp
public sealed class ImmutableData
{
    public int Value { get; }

    public ImmutableData(int value)
    {
        Value = value;
    }
}

// Attempting to derive from ImmutableData will result in a compilation error.
// public class DerivedData : ImmutableData {} // This line will cause an error.
```

### Sealed Class with Inheritance
You can use `sealed` in conjunction with class inheritance:

```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Base class display");
    }
}

public sealed class SealedDerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Sealed derived class display");
    }
}

// Attempting to further derive from SealedDerivedClass will result in a compilation error.
// public class FurtherDerivedClass : SealedDerivedClass {} // This line will cause an error.
```

## Explanation
When using the `sealed` keyword, developers should be aware of a few common pitfalls:

- **Inheritance Limitation**: Once a class is sealed, it cannot be extended. This could lead to rigid design if not planned properly.
- **Performance Misconceptions**: While sealing can lead to performance improvements, these gains are generally marginal. Developers should evaluate whether the design benefits outweigh the potential loss in flexibility.
- **Overriding**: If you need to override methods from a base class, be cautious about sealing. Sealing a derived class restricts any further extensions.

## One Line Summary
The `sealed` keyword in C# is used to prevent a class from being inherited, enhancing design integrity and potentially improving performance.