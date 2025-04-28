<!--
Meta Description: # Understanding Struct in C#: A Comprehensive Guide to C# Structures ## Synopsis In C#, a `struct` is a value type that allows developers to create li...
Meta Keywords: struct, structs, public, int, width
-->

# Understanding Struct in C#: A Comprehensive Guide to C# Structures

## Synopsis
In C#, a `struct` is a value type that allows developers to create lightweight objects that encapsulate data and related functionality, offering an efficient alternative to classes for certain use cases.

## Documentation
### Purpose
In C#, `struct` is used to define a structure, which is a composite data type that can contain data members (fields) and function members (methods). Structs are particularly useful when you want to group related variables together without the overhead of a class.

### Usage
A `struct` is defined using the `struct` keyword followed by its name and a body that contains its members. Structs are value types, meaning they are stored on the stack, which can lead to performance benefits in scenarios where small, immutable data objects are needed.

#### Basic Syntax
```csharp
struct StructName
{
    public int Field1;
    public string Field2;

    public void Method1()
    {
        // Method implementation
    }
}
```

### Key Features
- **Value Type**: Structs are stored in stack memory, making them efficient for small data structures.
- **Immutability**: While structs can be mutable, they are often used as immutable types for better performance and predictability.
- **No Inheritance**: Structs do not support inheritance, but they can implement interfaces.
- **Default Constructor**: Structs do not allow explicit declaration of a default constructor (parameterless constructor); they have an implicit one that initializes all fields to their default values.

## Examples
### Basic Struct Definition and Usage
```csharp
struct Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Display()
    {
        Console.WriteLine($"Point coordinates: ({X}, {Y})");
    }
}

class Program
{
    static void Main()
    {
        Point p1 = new Point(10, 20);
        p1.Display(); // Output: Point coordinates: (10, 20)
    }
}
```

### Using Struct with Value Semantics
```csharp
struct Rectangle
{
    public int Width;
    public int Height;

    public int Area => Width * Height;

    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;
    }
}

class Program
{
    static void Main()
    {
        Rectangle rect1 = new Rectangle(5, 10);
        Rectangle rect2 = rect1; // Copying value

        rect2.Width = 20; // Changing rect2 does not affect rect1

        Console.WriteLine($"rect1 Width: {rect1.Width}"); // Output: 5
        Console.WriteLine($"rect2 Width: {rect2.Width}"); // Output: 20
    }
}
```

## Explanation
### Common Pitfalls
- **Mutability**: When using structs, be cautious about mutability. Since structs are value types, passing them to methods or assigning them to new variables creates a copy. Changes made to the copy do not affect the original struct.
- **Large Structs**: Avoid creating large structs. Since they are copied by value, large data structures can lead to performance issues.
- **Default Constructor**: Attempting to define a default constructor will result in a compilation error. Always ensure you use the implicit constructor provided by C#.

### Additional Notes
- Structs can implement interfaces, allowing them to be used polymorphically.
- They are often used as data carriers in scenarios like 2D graphics (e.g., `Point`, `Rectangle`).
- Be mindful of boxing and unboxing when working with structs and collections, as it can introduce performance overhead.

## One Line Summary
A struct in C# is a value type that encapsulates related data and functionality, providing an efficient way to model lightweight objects.