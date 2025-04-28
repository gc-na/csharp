<!--
Meta Description: # C# Override Keyword: A Comprehensive Guide to Method Overriding in C# ## Synopsis The `override` keyword in C# is used to extend or modify the behav...
Meta Keywords: method, class, base, public, override
-->

# C# Override Keyword: A Comprehensive Guide to Method Overriding in C#

## Synopsis
The `override` keyword in C# is used to extend or modify the behavior of a base class method in a derived class, allowing for polymorphic behavior and method overriding in object-oriented programming.

## Documentation
In C#, the `override` keyword is utilized within a derived class to provide a new implementation of a method that is already defined in its base class. This feature is part of C#'s support for polymorphism, allowing methods to be called on derived class instances even when referenced by base class types.

### Purpose
The primary purpose of method overriding is to enable a derived class to tailor or enhance the functionality of a base class method while maintaining the same method signature. This is essential for achieving dynamic method resolution, where the method that gets executed is determined at runtime based on the actual object type.

### Usage
To use the `override` keyword:
1. The base class method must be declared with the `virtual` or `abstract` keyword.
2. The derived class method must use the `override` keyword in its declaration.

### Syntax
```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Display from BaseClass");
    }
}

public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Display from DerivedClass");
    }
}
```

## Examples

### Example 1: Basic Method Overriding
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

// Usage
Animal myDog = new Dog();
myDog.Speak(); // Output: Dog barks
```

### Example 2: Overriding an Abstract Method
```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Circle : Shape
{
    private double radius;

    public Circle(double r)
    {
        radius = r;
    }

    public override double Area()
    {
        return Math.PI * radius * radius;
    }
}

// Usage
Shape myCircle = new Circle(5);
Console.WriteLine(myCircle.Area()); // Output: 78.53981633974483
```

## Explanation
While using `override`, there are several important points to keep in mind:

1. **Access Modifiers**: The access level of the overriding method must be the same as or more accessible than the base method.
2. **Sealed Methods**: If a base class method is declared as `sealed`, it cannot be overridden in any derived classes.
3. **Method Signature**: The method signature (name and parameters) must exactly match the method in the base class.
4. **Base Method Invocation**: You can call the base class method within the overriding method using `base.MethodName()`.

### Common Pitfalls
- Forgetting to mark the base method as `virtual` or `abstract`, leading to a compilation error when trying to use `override`.
- Mismatching method signatures, which can cause runtime errors.
- Not considering the implications of polymorphism, where the derived method may not be called if the object is referenced as the base type.

## One Line Summary
The `override` keyword in C# allows derived classes to provide a new implementation for virtual or abstract methods defined in a base class, enabling polymorphic behavior.