<!--
Meta Description: # Understanding "void" in C#: Definition, Usage, and Examples ## Synopsis In C#, the keyword `void` is used to specify that a method does not return a...
Meta Keywords: return, void, method, value, not
-->

# Understanding "void" in C#: Definition, Usage, and Examples

## Synopsis
In C#, the keyword `void` is used to specify that a method does not return a value. It is a fundamental concept in C# programming, allowing developers to create methods that perform actions without needing to return a result.

## Documentation
### Purpose
The `void` keyword is crucial in defining methods that are intended solely for their side effects rather than for producing a value. This is especially useful for methods that perform operations such as modifying data, writing to the console, or updating the user interface.

### Usage
When declaring a method in C#, you can denote it as returning no value by using the `void` keyword before the method name. For example:

```csharp
public void DisplayMessage()
{
    Console.WriteLine("Hello, World!");
}
```

In this example, `DisplayMessage` is a method that prints a message to the console but does not return any value.

### Details
- **Method Signature**: The signature of a method with `void` includes the access modifier (e.g., `public`, `private`), the return type (`void`), the method name, and any parameters.
- **No Return Statement**: While you can include a return statement in a `void` method, it should not return a value. Using `return;` without a value is valid to exit the method early.
- **Event Handlers**: `void` methods are commonly used as event handlers, where they respond to events without returning a value.

## Examples
1. **Basic Method Declaration**:
   ```csharp
   public void PrintSum(int a, int b)
   {
       int sum = a + b;
       Console.WriteLine($"The sum is: {sum}");
   }
   ```

2. **Early Exit from a Method**:
   ```csharp
   public void CheckPositive(int number)
   {
       if (number < 0)
       {
           Console.WriteLine("Number is negative.");
           return; // Exits the method early
       }
       Console.WriteLine("Number is positive.");
   }
   ```

3. **Event Handling Example**:
   ```csharp
   public void OnButtonClick(object sender, EventArgs e)
   {
       Console.WriteLine("Button was clicked!");
   }
   ```

## Explanation
### Common Pitfalls
- **Confusion with Return Types**: Beginners may mistakenly try to return a value from a `void` method, which will result in a compilation error. It is essential to remember that `void` indicates no return.
- **Misusing Return Statements**: While you can use `return;` to exit a `void` method, using it with a value will not compile and lead to confusion.

### Additional Notes
- `void` can be used in delegate declarations, allowing for the creation of callback methods that do not return values.
- In asynchronous programming, `async` methods can also return `Task` or `Task<T>`, where `Task` represents an operation that does not return a value, akin to `void`.

## One Line Summary
In C#, `void` is a keyword used to define methods that do not return a value, allowing for action-oriented functionality without a return result.