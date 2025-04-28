<!--
Meta Description: # Understanding the "protected" Access Modifier in C# ## Synopsis The `protected` keyword in C# is an access modifier that restricts access to class m...
Meta Keywords: protected, class, access, classes, derived
-->

# Understanding the "protected" Access Modifier in C#

## Synopsis
The `protected` keyword in C# is an access modifier that restricts access to class members, allowing them to be accessed only within their own class and by derived classes. This feature is essential for implementing encapsulation and inheritance in object-oriented programming.

## Documentation
In C#, access modifiers determine the visibility and accessibility of class members (fields, properties, methods, and events) to other classes. The `protected` access modifier is one of the four main access modifiers in C#—the others being `public`, `private`, and `internal`.

### Purpose
The primary purpose of the `protected` modifier is to allow derived classes to access members of their base class while preventing access from unrelated classes. This enables a controlled inheritance mechanism where base class implementations can be extended or modified safely.

### Usage
To declare a member as `protected`, you simply prefix the member declaration with the `protected` keyword. Below is the syntax:

```csharp
protected type memberName;
```

### Details
- **Class Members**: Members declared as `protected` can be accessed within the class they are declared in and in any class that derives from it, regardless of whether they are in the same assembly.
- **No Access from Non-Derived Classes**: If a class does not inherit from a base class, it cannot access its `protected` members.
- **Combination with Other Modifiers**: You can combine `protected` with other access modifiers. For instance, `protected internal` allows access from derived classes and classes within the same assembly.

## Examples
### Example 1: Basic Usage of `protected`
```csharp
public class BaseClass
{
    protected int protectedField;

    protected void ProtectedMethod()
    {
        Console.WriteLine("Protected Method Accessed");
    }
}

public class DerivedClass : BaseClass
{
    public void AccessProtectedMembers()
    {
        protectedField = 10; // Accessing protected field
        ProtectedMethod();    // Calling protected method
    }
}
```

### Example 2: `protected` with Inheritance
```csharp
public class Animal
{
    protected string species;

    protected void DisplaySpecies()
    {
        Console.WriteLine($"Species: {species}");
    }
}

public class Dog : Animal
{
    public Dog()
    {
        species = "Canine"; // Accessing protected member
    }

    public void ShowSpecies()
    {
        DisplaySpecies(); // Accessing protected method
    }
}
```

## Explanation
### Common Pitfalls
- **Accessing from Non-Derived Classes**: A frequent mistake is attempting to access a `protected` member from a non-derived class, which will lead to a compilation error.
- **Misunderstanding Protected Internal**: Developers may confuse `protected internal` with `protected`. Remember that `protected internal` allows both derived and same-assembly access, while `protected` restricts access solely to derived classes.

### Gotchas
- **Sealed Classes**: If a class is marked as `sealed`, it cannot be inherited, which may lead to confusion about the usage of `protected` members that cannot be accessed by any other class.
- **Nested Classes**: A nested class can access the `protected` members of its containing class, even if it is not a derived class.

## One Line Summary
The `protected` access modifier in C# allows class members to be accessed only within their own class and by derived classes, promoting encapsulation and controlled inheritance.