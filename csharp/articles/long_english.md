<!--
Meta Description: # Understanding the 'long' Data Type in C#: A Comprehensive Guide ## Synopsis In C#, the `long` data type is a 64-bit signed integer that is used to s...
Meta Keywords: long, type, data, can, csharp
-->

# Understanding the 'long' Data Type in C#: A Comprehensive Guide

## Synopsis
In C#, the `long` data type is a 64-bit signed integer that is used to store large numeric values. It is essential for applications that require high-performance arithmetic operations on large numbers.

## Documentation
The `long` keyword in C# is used to declare a variable that can hold a 64-bit signed integer. This data type is particularly useful when dealing with numbers that exceed the range of the standard `int` data type, which is limited to 32 bits.

### Purpose
The primary purpose of the `long` data type is to provide a means of representing large integer values that can be utilized in various arithmetic computations, storage, and manipulation within applications.

### Usage
To declare a variable of type `long`, you can use the following syntax:

```csharp
long myLongVariable;
```

You can also initialize it at the time of declaration:

```csharp
long myLongVariable = 12345678901234;
```

### Range
The `long` data type can hold values from `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807`. This makes it suitable for applications that need to handle very large numbers.

### Type Conversion
You can convert other numeric types to `long` using explicit casting or the `Convert` class:

```csharp
int myInt = 123456;
long myLongFromInt = (long)myInt; // Explicit casting
long myLongFromDouble = Convert.ToInt64(12345.67); // Using Convert class
```

## Examples

### Basic Declaration and Initialization
```csharp
long distanceToMoon = 384400000; // Distance from Earth to Moon in meters
Console.WriteLine(distanceToMoon); // Outputs: 384400000
```

### Arithmetic Operations
```csharp
long a = 1000000000;
long b = 2000000000;
long sum = a + b;
Console.WriteLine(sum); // Outputs: 3000000000
```

### Type Conversion
```csharp
double myDouble = 12345.6789;
long myConvertedLong = Convert.ToInt64(myDouble);
Console.WriteLine(myConvertedLong); // Outputs: 12346 (rounded)
```

## Explanation
When using the `long` data type, it's important to be aware of the following:

- **Overflow**: If you exceed the range of `long`, it will cause an overflow exception if checked, or wrap around to the negative end of the range if unchecked. You can use the `checked` keyword to enable overflow checking:
  
  ```csharp
  long result = checked(a + b); // Throws an exception if overflow occurs
  ```

- **Performance**: While `long` is capable of handling larger values, it may have a performance overhead compared to smaller data types like `int`. Always choose the data type that best fits your needs based on the expected range of values.

- **Default Value**: The default value of a `long` variable is `0`.

## One Line Summary
The `long` data type in C# is a powerful tool for handling large signed integers, offering a range from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.