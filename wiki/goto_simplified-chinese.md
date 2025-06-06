<!--
Meta Description: # C# 中的 goto 语句详解 ## 概述 `goto` 是 C# 编程语言中的一种控制流语句，允许程序在代码中跳转到指定标签的位置。尽管它在某些情况下可以简化代码逻辑，但过度使用可能导致代码可读性降低。 ## 文档 ### 目的 `goto` 语句主要用于在程序执行过程中跳转到代码中的特定标签...
Meta Keywords: goto, console, writeline, csharp, 当前值
-->

# C# 中的 goto 语句详解

## 概述
`goto` 是 C# 编程语言中的一种控制流语句，允许程序在代码中跳转到指定标签的位置。尽管它在某些情况下可以简化代码逻辑，但过度使用可能导致代码可读性降低。

## 文档
### 目的
`goto` 语句主要用于在程序执行过程中跳转到代码中的特定标签。这种跳转可以用于实现循环、条件跳转等功能。

### 用法
在 C# 中，`goto` 语句的基本语法如下：

```csharp
goto label;
```

标签是一个用户定义的标识符，后面紧跟着一个冒号。可以在程序的任意位置定义标签。使用 `goto` 跳转时，程序将立即转移到标签的位置继续执行。

### 注意事项
- `goto` 语句只能跳转到同一方法内的标签。
- 不允许跳转到变量声明、循环结构或异常处理结构的内部。
- 在使用 `goto` 时，务必确保逻辑清晰，以避免造成代码混乱和难以维护的问题。

## 示例
以下是一些基本的 `goto` 使用示例：

### 示例 1：基本使用
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("开始程序");

        goto Skip;

        Console.WriteLine("这行代码不会被执行");

    Skip:
        Console.WriteLine("跳过到这里");
    }
}
```
输出：
```
开始程序
跳过到这里
```

### 示例 2：在循环中的使用
```csharp
using System;

class Program
{
    static void Main()
    {
        for (int i = 0; i < 5; i++)
        {
            if (i == 2)
            {
                goto EndLoop;
            }
            Console.WriteLine($"当前值: {i}");
        }

    EndLoop:
        Console.WriteLine("循环结束");
    }
}
```
输出：
```
当前值: 0
当前值: 1
循环结束
```

## 解释
- **常见陷阱**：使用 `goto` 可能导致程序流变得复杂，特别是当多个 `goto` 语句交错使用时，程序逻辑可能会变得难以追踪。
- **可读性与维护性**：虽然 `goto` 可以在某些情况下简化代码，但过度依赖它会使代码变得难以理解和维护。建议优先使用结构化控制流语句，如 `if`、`for` 和 `while`。

## 一句话总结
`goto` 语句在 C# 中用于跳转到指定标签，尽管有其用途，但应谨慎使用以保持代码的可读性和维护性。