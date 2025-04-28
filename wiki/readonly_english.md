<!--
Meta Description: # Understanding the 'readonly' Modifier in C# ## Synopsis The `readonly` modifier in C# is used to declare fields that can only be assigned during the...
Meta Keywords: readonly, field, public, can, constructor
-->

# Understanding the 'readonly' Modifier in C#

## Synopsis
The `readonly` modifier in C# is used to declare fields that can only be assigned during their declaration or within the constructor of the containing class, providing a way to create immutable data.

## Documentation
### Purpose
The `readonly` modifier is designed to ensure that once a field is initialized, its value cannot be changed. This promotes immutability, which can lead to safer and more maintainable code by preventing unintended side effects.

### Usage
To declare a field as `readonly`, simply add the `readonly` keyword before the field's type in your class definition. A `readonly` field can be assigned a value either at the time of declaration or within the constructor of the class.

```csharp
public class Example
{
    public readonly int ReadOnlyField;

    public Example(int value)
    {
        ReadOnlyField = value; // Valid assignment
    }
}
```

### Details
- **Field Declaration**: You can declare a `readonly` field without initializing it. However, it must be assigned a value in the constructor.
- **Constructor Assignment**: You can assign a value to a `readonly` field in any constructor, allowing for flexibility in how the field is initialized.
- **Immutability**: Once a `readonly` field is set, it cannot be modified or reassigned outside of its constructor, ensuring the integrity of the data.
- **Static Readonly Fields**: You can also declare static fields as `readonly`. These fields can be assigned a value either at declaration or within a static constructor.

```csharp
public class Example
{
    public static readonly int StaticReadOnlyField = 10;

    public Example(int value)
    {
        // StaticReadOnlyField = 20; // This will cause a compile-time error
    }
}
```

## Examples
Here are some basic usage examples of the `readonly` modifier:

### Example 1: Basic Readonly Field
```csharp
public class Person
{
    public readonly string Name;

    public Person(string name)
    {
        Name = name; // Valid assignment
    }
}
```

### Example 2: Readonly Field Initialization
```csharp
public class Configuration
{
    public readonly int MaxUsers = 100; // Initialized at declaration

    public Configuration()
    {
        // MaxUsers = 200; // Invalid assignment
    }
}
```

### Example 3: Static Readonly Field
```csharp
public class MathConstants
{
    public static readonly double Pi = 3.14159;

    static MathConstants()
    {
        // Pi = 3.14; // Invalid assignment
    }
}
```

## Explanation
### Common Pitfalls and Gotchas
- **Assignment Outside Constructor**: Attempting to assign a value to a `readonly` field outside of its constructor will result in a compile-time error.
- **Structs and Readonly**: Be cautious when using `readonly` with structs. Although the struct instance itself can be `readonly`, the fields inside the struct can still be modified unless they are also declared as `readonly`.
- **Immutable Collections**: While `readonly` prevents reassignment of the reference to an object, it does not make the object itself immutable. For example, a `readonly` list can still have its contents modified.

## One Line Summary
The `readonly` modifier in C# restricts field assignment to declaration and constructor, promoting immutability and data integrity.