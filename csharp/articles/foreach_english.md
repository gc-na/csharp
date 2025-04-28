<!--
Meta Description: # Understanding the `foreach` Loop in C#: A Comprehensive Guide ## Synopsis The `foreach` loop in C# is a powerful construct that simplifies iteration...
Meta Keywords: foreach, loop, collection, over, types
-->

# Understanding the `foreach` Loop in C#: A Comprehensive Guide

## Synopsis
The `foreach` loop in C# is a powerful construct that simplifies iteration over collections, arrays, and other enumerable objects, allowing developers to access each element without needing to manage the index manually.

## Documentation
The `foreach` statement in C# is designed to iterate through elements in a collection or an array. It provides a clean and efficient way to access elements without the complexities of traditional loop constructs. The syntax is straightforward and enhances code readability.

### Purpose
The primary purpose of the `foreach` loop is to enable iteration over a sequence of elements, such as arrays, lists, and other collections that implement the `IEnumerable` or `IEnumerable<T>` interface.

### Usage
The syntax for a `foreach` loop is as follows:

```csharp
foreach (var element in collection)
{
    // Code to execute for each element
}
```

- **`element`**: A variable that represents the current item in the collection during each iteration.
- **`collection`**: The collection or array being iterated over.

### Details
- The `foreach` loop can be used with various data types, including arrays, lists, dictionaries, and any custom collections that implement `IEnumerable`.
- The loop automatically handles the iteration internally, eliminating the need for an index counter.
- It is important to note that the collection being iterated over should not be modified during the iteration, as this can lead to runtime exceptions.

## Examples
### Basic Usage with an Array
```csharp
string[] fruits = { "Apple", "Banana", "Cherry" };

foreach (var fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

### Basic Usage with a List
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };

foreach (var number in numbers)
{
    Console.WriteLine(number);
}
```

### Iterating Over a Dictionary
```csharp
Dictionary<string, int> ages = new Dictionary<string, int>
{
    { "Alice", 30 },
    { "Bob", 25 },
    { "Charlie", 35 }
};

foreach (var kvp in ages)
{
    Console.WriteLine($"{kvp.Key} is {kvp.Value} years old.");
}
```

## Explanation
While the `foreach` loop is generally very straightforward, there are a few common pitfalls and considerations to keep in mind:

1. **Modification of Collection**: Attempting to modify the collection being iterated over (e.g., adding or removing elements) will throw an `InvalidOperationException`. It is best practice to create a copy of the collection or collect items to modify in a separate list if changes are necessary.
   
2. **Non-Enumerable Types**: The `foreach` loop can only be used with types that implement the `IEnumerable` or `IEnumerable<T>` interfaces. Attempting to use it with non-iterable types will result in a compile-time error.

3. **Value Types vs. Reference Types**: When iterating over value types, be aware that each iteration creates a copy of the current element. If you need to modify the elements, consider using a traditional `for` loop instead.

## One Line Summary
The `foreach` loop in C# provides an efficient and readable way to iterate over collections and arrays, simplifying access to each element without manual index management.