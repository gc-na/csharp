<!--
Meta Description: # Understanding the `goto` Statement in C# ## Synopsis The `goto` statement in C# provides a way to transfer control to a labeled statement within the...
Meta Keywords: goto, statement, code, label, use
-->

# Understanding the `goto` Statement in C#

## Synopsis
The `goto` statement in C# provides a way to transfer control to a labeled statement within the same method, allowing for non-linear execution flow. While powerful, its use is generally discouraged in favor of structured control flow constructs.

## Documentation
The `goto` statement allows you to jump to a specific label in your code. It is defined as follows:

```csharp
goto label;
```

Where `label` is a user-defined identifier followed by a colon (`:`). The label must be defined within the same method and at a location that is valid for the jump.

### Purpose
The primary purpose of the `goto` statement is to provide an alternative way to control the flow of execution, especially in scenarios involving complex conditions or error handling.

### Usage
`goto` can be used in various situations, such as:
- Skipping code segments.
- Breaking out of deeply nested loops.
- Implementing finite state machines.

### Details
- **Labels**: Labels are defined by placing an identifier followed by a colon (`:`) before a statement.
- **Scope**: The scope of the label is limited to the method in which it is defined. Labels cannot span across multiple methods.
- **Control Flow**: When a `goto` statement is executed, control jumps to the specified label, skipping any intervening code.

## Examples
### Basic Usage
Here is a simple example demonstrating the use of the `goto` statement:

```csharp
using System;

class Program
{
    static void Main()
    {
        int i = 0;

        start:
        if (i < 5)
        {
            Console.WriteLine(i);
            i++;
            goto start; // Jumps back to the 'start' label
        }
    }
}
```
In this example, the program prints numbers from 0 to 4 by using the `goto` statement to loop back to the start label.

### Skipping Code
You can use `goto` to skip certain parts of code:

```csharp
using System;

class Program
{
    static void Main()
    {
        int number = 10;

        if (number > 5)
        {
            goto Skip;
        }

        Console.WriteLine("This will not be printed");

        Skip:
        Console.WriteLine("Skipped the previous line.");
    }
}
```
In this snippet, the program skips the line that prints "This will not be printed" if the condition is true.

## Explanation
### Common Pitfalls
- **Readability**: Excessive use of `goto` can make code harder to read and maintain. It can create "spaghetti code," where the flow of execution is difficult to follow.
- **Error Handling**: Relying on `goto` for error handling can lead to unpredictable behavior and bugs.
- **Limited Use Cases**: In most cases, structured programming constructs such as loops (`for`, `while`) and conditionals (`if`, `switch`) are recommended over `goto`.

### Gotchas
- **Scope Restrictions**: Labels must be defined within the same method, limiting their use in more complex structures.
- **Performance**: While `goto` itself is not inherently inefficient, using it inappropriately can lead to performance issues due to increased complexity in code execution paths.

## One Line Summary
The `goto` statement in C# enables jumping to labeled code within a method, but its use is generally discouraged in favor of more structured programming practices.