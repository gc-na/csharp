<!--
Meta Description: # Understanding stackalloc in C#: Efficient Memory Allocation on the Stack ## Synopsis `stackalloc` is a C# keyword used for allocating memory on the ...
Meta Keywords: stackalloc, memory, stack, point, can
-->

# Understanding stackalloc in C#: Efficient Memory Allocation on the Stack

## Synopsis
`stackalloc` is a C# keyword used for allocating memory on the stack for a fixed-size array. It provides a way to create arrays with a limited lifetime that can enhance performance by avoiding heap allocations.

## Documentation
### Purpose
The `stackalloc` keyword is primarily used to allocate memory for arrays directly on the stack rather than the heap. This can lead to more efficient memory usage and faster allocations, especially in scenarios where the size of the array is known at compile time and the array does not need to persist beyond the scope in which it was created.

### Usage
`stackalloc` is typically used within a method to allocate memory for an array. The syntax is straightforward:

```csharp
Span<T> span = stackalloc T[length];
```

Where `T` is the type of the elements in the array and `length` is the number of elements to allocate.

### Details
- **Lifetime**: Memory allocated using `stackalloc` is automatically deallocated when the method completes, making it ideal for temporary data storage.
- **Performance**: Since stack memory allocation is generally faster than heap allocation, using `stackalloc` can lead to performance improvements in high-frequency or performance-critical methods.
- **Limitations**: The size of memory allocated with `stackalloc` is limited by the stack size. Allocating too much memory can lead to a `StackOverflowException`.
- **Value Types**: `stackalloc` can only be used with value types, such as structs or primitive types. It cannot be used with reference types.
- **Span<T>**: The allocated memory can be wrapped in a `Span<T>`, providing a safer and more flexible way to handle the memory.

## Examples
### Basic Usage Example
Here’s a simple example of using `stackalloc` to create an array of integers:

```csharp
public void ExampleMethod()
{
    Span<int> numbers = stackalloc int[10];

    for (int i = 0; i < numbers.Length; i++)
    {
        numbers[i] = i * 2;
    }

    foreach (var number in numbers)
    {
        Console.WriteLine(number);
    }
}
```

### Example with Structs
```csharp
public struct Point
{
    public int X;
    public int Y;
}

public void CreatePoints()
{
    Span<Point> points = stackalloc Point[3];

    points[0] = new Point { X = 1, Y = 2 };
    points[1] = new Point { X = 3, Y = 4 };
    points[2] = new Point { X = 5, Y = 6 };

    foreach (var point in points)
    {
        Console.WriteLine($"Point: ({point.X}, {point.Y})");
    }
}
```

## Explanation
### Common Pitfalls
- **Stack Overflow**: Be cautious about the amount of memory you allocate. Exceeding the stack size can lead to a `StackOverflowException`. The stack size varies by platform but is generally much smaller than the heap.
- **Lifetime Issues**: Since stack-allocated memory is deallocated when the method exits, trying to access this memory outside the method will result in undefined behavior.
- **Only Value Types**: Remember that `stackalloc` can only be used with value types. Attempting to allocate a reference type will lead to a compilation error.

## One Line Summary
`stackalloc` in C# allows for efficient allocation of fixed-size arrays on the stack, improving performance for temporary data storage.