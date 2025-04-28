<!--
Meta Description: # Understanding the "checked" Keyword in C#: A Comprehensive Guide ## Synopsis The `checked` keyword in C# is used to explicitly enable overflow check...
Meta Keywords: checked, overflow, arithmetic, int, checking
-->

# Understanding the "checked" Keyword in C#: A Comprehensive Guide

## Synopsis
The `checked` keyword in C# is used to explicitly enable overflow checking for arithmetic operations and conversions, ensuring that exceptions are thrown when an overflow occurs.

## Documentation
The `checked` keyword provides a mechanism to detect overflow conditions in arithmetic operations, which can occur when the result of an operation exceeds the range of the data type. By utilizing `checked`, developers can write robust applications that handle numerical calculations safely, avoiding silent failures or incorrect results.

### Purpose
The primary purpose of `checked` is to enforce overflow checking during arithmetic operations. When used, any overflow will throw an `OverflowException`, allowing developers to catch and handle such situations.

### Usage
The `checked` keyword can be applied in two contexts:
1. **Checked Blocks**: You can use `checked` to define a block of code where arithmetic overflow checking is enforced.
2. **Checked Expressions**: It can be used to check individual expressions for overflow.

### Syntax
```csharp
checked
{
    // Code block for overflow checking
}

int result = checked(a + b); // Checked expression
```

## Examples

### Example 1: Using Checked Blocks
```csharp
int a = int.MaxValue;
int b = 1;

try
{
    checked
    {
        int result = a + b; // This will throw an OverflowException
    }
}
catch (OverflowException ex)
{
    Console.WriteLine("Overflow occurred: " + ex.Message);
}
```

### Example 2: Using Checked Expressions
```csharp
int a = 100000;
int b = 200000;

try
{
    int result = checked(a * b); // This will throw an OverflowException
}
catch (OverflowException ex)
{
    Console.WriteLine("Overflow occurred: " + ex.Message);
}
```

## Explanation
While the `checked` keyword is a powerful tool for preventing silent overflows, there are some common pitfalls to be aware of:

- **Performance Impact**: Enabling overflow checking can introduce a performance overhead since the runtime must monitor arithmetic operations. Use it judiciously in performance-critical code.
- **Default Behavior**: By default, C# performs unchecked arithmetic operations in certain contexts, such as in simple arithmetic directly without `checked`. Always be explicit when you need checking.
- **Nested Checked Blocks**: It is possible to nest `checked` blocks, but keep in mind that if an inner block throws an exception, it will propagate up to the outer block unless handled.

## One Line Summary
The `checked` keyword in C# enables overflow checking for arithmetic operations, throwing exceptions on overflow to enhance numerical safety in applications.