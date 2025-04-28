<!--
Meta Description: # C# 中的 stackalloc：高效内存分配的关键字 ## 概述 `stackalloc` 是 C# 中用于在堆栈上分配内存的关键字。它允许开发者在堆栈上快速分配一个固定大小的数组，通常用于性能优化和减少垃圾回收的负担。 ## 文档 ### 目的 `stackalloc` 主要用于在堆栈上分配...
Meta Keywords: stackalloc, int, span, numbers, csharp
-->

# C# 中的 stackalloc：高效内存分配的关键字

## 概述
`stackalloc` 是 C# 中用于在堆栈上分配内存的关键字。它允许开发者在堆栈上快速分配一个固定大小的数组，通常用于性能优化和减少垃圾回收的负担。

## 文档
### 目的
`stackalloc` 主要用于在堆栈上分配内存，与在堆上分配内存（如使用 `new` 关键字）相比，堆栈分配速度更快且无需垃圾回收。适用于临时数据存储，尤其是在性能敏感的代码中。

### 使用方法
`stackalloc` 只能用于分配值类型的数组。其基本语法如下：

```csharp
Span<int> span = stackalloc int[10];
```

在这个例子中，我们在堆栈上分配了一个包含10个整数的数组，并将其包装在一个 `Span<int>` 中，以便于进一步操作。

### 细节
- **内存管理**：使用 `stackalloc` 分配的内存会在方法返回时自动释放，无需手动处理。
- **类型限制**：`stackalloc` 只能用于值类型，不支持引用类型。
- **大小限制**：堆栈内存的大小通常有限制，因此不适合分配过大的数组。

## 示例
以下是使用 `stackalloc` 的基本示例：

```csharp
using System;

class Program
{
    static void Main()
    {
        Span<int> numbers = stackalloc int[5];
        
        for (int i = 0; i < numbers.Length; i++)
        {
            numbers[i] = i * 2; // 填充数据
        }

        foreach (var number in numbers)
        {
            Console.WriteLine(number); // 输出: 0, 2, 4, 6, 8
        }
    }
}
```

在这个示例中，我们在堆栈上分配了一个包含5个整数的数组，并将其填充并打印。

## 说明
- **常见陷阱**：由于 `stackalloc` 分配的内存是临时的，过度使用可能导致堆栈溢出错误。在编写代码时，应避免创建过大的数组。
- **性能考量**：虽然 `stackalloc` 提供了高效的内存分配，但使用时需谨慎，尤其是在递归方法中，当方法调用层次较深时，可能会导致堆栈溢出。
- **使用场景**：适用于需要快速创建临时数组的场景，例如在性能敏感的算法中。

## 一句话总结
`stackalloc` 是 C# 中用于在堆栈上高效地分配内存的关键字，适合临时数组的创建。