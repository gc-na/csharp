<!--
Meta Description: # Understanding the "explicit" Keyword in C# ## Synopsis The `explicit` keyword in C# is used to define a user-defined conversion operator that requir...
Meta Keywords: explicit, value, public, conversion, type
-->

# Understanding the "explicit" Keyword in C#

## Synopsis
The `explicit` keyword in C# is used to define a user-defined conversion operator that requires an explicit cast when converting between types, enhancing type safety and clarity in code.

## Documentation
In C#, the `explicit` keyword is primarily used in conjunction with operator overloading to create conversion operators between user-defined types. By marking a conversion operator as `explicit`, you ensure that any conversion from one type to another must be explicitly stated in the code, helping to prevent unintended data loss or type mismatches.

### Purpose
The purpose of the `explicit` keyword is to enforce stricter type conversions in your code. This is particularly useful when converting from a more complex type to a simpler type, where automatic conversions could lead to ambiguity or data truncation.

### Usage
To define an explicit conversion operator, you can use the following syntax:

```csharp
public static explicit operator TargetType(SourceType source)
{
    // Conversion logic here
}
```

Where `TargetType` is the type you want to convert to, and `SourceType` is the type you want to convert from.

### Details
- **Scope**: You can define explicit conversions for both struct and class types.
- **Error Handling**: When using explicit conversions, it’s important to handle potential conversion errors, as failing to do so can lead to runtime exceptions.
- **Performance**: While explicit conversions can be safer, they may incur a slight performance overhead compared to implicit conversions due to the necessity of casting.

## Examples
### Example 1: User-Defined Type Conversion
Here’s a simple example illustrating an explicit conversion from a class `Feet` to an `Inches` type:

```csharp
public class Feet
{
    public double Value { get; set; }

    public Feet(double value)
    {
        Value = value;
    }

    public static explicit operator Inches(Feet feet)
    {
        return new Inches(feet.Value * 12);
    }
}

public class Inches
{
    public double Value { get; set; }

    public Inches(double value)
    {
        Value = value;
    }
}

// Usage
Feet feet = new Feet(5);
Inches inches = (Inches)feet; // Explicit cast required
```

### Example 2: Converting Between Structs
```csharp
public struct Celsius
{
    public double Value { get; set; }

    public Celsius(double value)
    {
        Value = value;
    }

    public static explicit operator Fahrenheit(Celsius celsius)
    {
        return new Fahrenheit((celsius.Value * 9 / 5) + 32);
    }
}

public struct Fahrenheit
{
    public double Value { get; set; }

    public Fahrenheit(double value)
    {
        Value = value;
    }
}

// Usage
Celsius celsius = new Celsius(100);
Fahrenheit fahrenheit = (Fahrenheit)celsius; // Explicit cast required
```

## Explanation
One common pitfall with the `explicit` keyword is forgetting to perform the necessary cast when using the conversion operator, leading to compilation errors. Additionally, if the conversion logic is not carefully implemented, it may result in runtime exceptions or incorrect values.

Another important note is that `explicit` conversions can make code less readable if overused, as the need for explicit casts can clutter code and make it harder to follow. Therefore, it’s critical to use explicit conversions judiciously and only when necessary.

## One Line Summary
The `explicit` keyword in C# enforces type safety by requiring an explicit cast for user-defined conversion operators between types.