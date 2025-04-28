<!--
Meta Description: # Understanding the "fixed" Statement in C#: A Comprehensive Guide ## Synopsis The `fixed` statement in C# is a keyword used to pin a variable in memo...
Meta Keywords: fixed, statement, unsafe, code, pointer
-->

# Understanding the "fixed" Statement in C#: A Comprehensive Guide

## Synopsis
The `fixed` statement in C# is a keyword used to pin a variable in memory, preventing the garbage collector from relocating it, which is essential when working with pointers and unmanaged code.

## Documentation
The `fixed` statement is primarily used in unsafe contexts to create a pointer to a managed object, allowing direct memory manipulation. When a managed object is pinned, the Garbage Collector (GC) cannot move it during a collection, ensuring that the pointer remains valid.

### Purpose
The primary purpose of the `fixed` statement is to enable interoperability with unmanaged code, allowing developers to handle memory directly while ensuring that the managed environment remains stable.

### Usage
To use the `fixed` statement, you must declare an unsafe context in your code. This allows you to work with pointers safely. Here's the syntax:

```csharp
fixed (type* pointer = &variable)
{
    // Code that uses the pointer
}
```

### Details
- The `fixed` statement can only be used with reference types (e.g., arrays, strings).
- It is necessary to declare the surrounding code block as unsafe, which can be done by adding the `unsafe` keyword to the method or main program.
- The scope of the pinning is limited to the block of code within the `fixed` statement.

## Examples

### Example 1: Pinning an Array
Here’s a simple example of how to use the `fixed` statement to pin an array:

```csharp
unsafe
{
    int[] numbers = { 1, 2, 3, 4, 5 };
    fixed (int* p = numbers)
    {
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine(*(p + i)); // Outputs: 1 2 3 4 5
        }
    }
}
```

### Example 2: Using `fixed` with a String
While strings are immutable, you can still use `fixed` to work with their underlying character data:

```csharp
unsafe
{
    string str = "hello";
    fixed (char* p = str)
    {
        for (int i = 0; i < str.Length; i++)
        {
            Console.WriteLine(*(p + i)); // Outputs: h e l l o
        }
    }
}
```

## Explanation
Common pitfalls when using the `fixed` statement include:

- **Unsafe Context**: The `unsafe` keyword must be declared at the method level or for the entire project. Ensure that your project settings allow unsafe code.
- **Scope Limitation**: The pointer is only valid within the `fixed` block. Attempting to use the pointer outside this block will lead to compilation errors.
- **Garbage Collection**: If the object is garbage collected during the `fixed` statement, it can lead to undefined behavior. Always ensure the object remains in scope.

Using `fixed` can lead to performance increases when manipulating large arrays or structures, but it can also introduce complexity and potential instability into your applications if not used carefully.

## One Line Summary
The `fixed` statement in C# is used to pin managed objects in memory, allowing for safe pointer manipulation in an unsafe context.