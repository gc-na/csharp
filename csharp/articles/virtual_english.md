<!--
Meta Description: # Understanding the "virtual" Keyword in C#: A Comprehensive Guide ## Synopsis The `virtual` keyword in C# enables polymorphism by allowing methods in...
Meta Keywords: virtual, class, public, method, keyword
-->

# Understanding the "virtual" Keyword in C#: A Comprehensive Guide

## Synopsis
The `virtual` keyword in C# enables polymorphism by allowing methods in a base class to be overridden in derived classes, facilitating dynamic method resolution at runtime.

## Documentation
The `virtual` keyword in C# is used to declare a method or property in a base class that can be overridden in a derived class. By marking a member as `virtual`, you inform the compiler that this member is intended to be overridden in derived classes. This capability is essential in object-oriented programming for achieving polymorphic behavior, which allows objects of different types to be treated as objects of a common base type.

### Purpose
The primary purpose of the `virtual` keyword is to allow for more flexible and extensible code. When you declare a method as `virtual`, you provide a base implementation that can be customized or replaced by derived classes, enhancing code reusability and maintainability.

### Usage
To use the `virtual` keyword, declare a method or property in your base class with the `virtual` modifier. In the derived class, override this member using the `override` keyword. This allows you to provide a new implementation for the method or property.

```csharp
public class BaseClass
{
    public virtual void DisplayMessage()
    {
        Console.WriteLine("Message from BaseClass");
    }
}

public class DerivedClass : BaseClass
{
    public override void DisplayMessage()
    {
        Console.WriteLine("Message from DerivedClass");
    }
}
```

## Examples

### Basic Example
Here’s a simple example illustrating the use of the `virtual` keyword:

```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak(); // Output: Dog barks
    }
}
```

In this example, the `Speak` method in the `Animal` class is declared as `virtual`, allowing the `Dog` class to provide its own implementation through the `override` keyword.

### Example with Properties
You can also use `virtual` with properties:

```csharp
public class Vehicle
{
    public virtual int Wheels { get; set; } = 4;
}

public class Motorcycle : Vehicle
{
    public override int Wheels { get; set; } = 2;
}

public class Program
{
    public static void Main()
    {
        Vehicle myMotorcycle = new Motorcycle();
        Console.WriteLine(myMotorcycle.Wheels); // Output: 2
    }
}
```

## Explanation
### Common Pitfalls
- **Forgetting to Use `override`:** After declaring a method as `virtual` in the base class, it's essential to use the `override` keyword in derived classes. Failing to do so will lead to compilation errors.
  
- **Sealed Methods:** If you declare a method in a derived class as `sealed`, it prevents further overriding in any further derived classes. This can lead to confusion if not properly documented.

- **Performance Considerations:** Virtual method calls incur a slight performance overhead compared to non-virtual calls because of the additional indirection involved in resolving the method at runtime.

### Additional Notes
- **Abstract Methods:** If you want to enforce that derived classes must provide an implementation, consider using the `abstract` keyword instead of `virtual`. An abstract method does not provide any implementation in the base class.

- **Non-virtual Methods:** If a method is not marked as `virtual`, derived classes cannot override it, which can be useful for ensuring certain behaviors remain unchanged.

## One Line Summary
The `virtual` keyword in C# allows methods and properties in a base class to be overridden in derived classes, enabling polymorphic behavior and enhancing code flexibility.