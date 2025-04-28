<!--
Meta Description: # CSharp中的“checked”关键字详解 ## 概述 “checked”是CSharp中的一个关键字，用于捕获整数运算中的溢出异常。它确保在执行可能导致溢出的算术操作时，抛出一个溢出异常，而不是默认情况下的截断行为。 ## 文档 ### 目的 在CSharp中，整数算术运算的结果在超出其数据...
Meta Keywords: checked, int, overflowexception, csharp, result
-->

# CSharp中的“checked”关键字详解

## 概述
“checked”是CSharp中的一个关键字，用于捕获整数运算中的溢出异常。它确保在执行可能导致溢出的算术操作时，抛出一个溢出异常，而不是默认情况下的截断行为。

## 文档
### 目的
在CSharp中，整数算术运算的结果在超出其数据类型的范围时，默认会发生截断，可能导致意外的逻辑错误。“checked”关键字的引入旨在提供一种机制，以增强代码的安全性，确保开发者能够及时发现并处理溢出问题。

### 用法
“checked”关键字可以用于单个表达式或整个代码块。使用“checked”时，如果运算结果超出范围，将抛出`OverflowException`异常。

#### 语法
```csharp
checked
{
    // 代码块
}
// 或者
int result = checked(a + b);
```

## 示例
### 示例 1: 使用“checked”关键字
```csharp
int a = 2147483647; // int的最大值
int b = 1;

try
{
    int result = checked(a + b); // 这里将抛出OverflowException
}
catch (OverflowException ex)
{
    Console.WriteLine("发生溢出: " + ex.Message);
}
```

### 示例 2: 在代码块中使用“checked”
```csharp
try
{
    checked
    {
        int c = 2147483647;
        int d = 1;
        int result = c + d; // 这里也将抛出OverflowException
    }
}
catch (OverflowException ex)
{
    Console.WriteLine("发生溢出: " + ex.Message);
}
```

## 说明
- **常见问题**：在使用“checked”时，如果未捕获异常，程序将终止。确保在需要的地方使用try-catch块来处理可能的溢出。
- **性能考虑**：使用“checked”会稍微降低性能，因为每次运算都需要检查溢出。但是在需要安全性和准确性的场景中，这种开销是可以接受的。
- **不同于unchecked**：CSharp中还有“unchecked”关键字，用于显示禁用溢出检查，允许运算结果截断。使用“unchecked”时，如果溢出发生，不会抛出异常。

## 一句话总结
“checked”关键字在CSharp中用于确保整数运算中溢出的安全性，通过抛出异常来提醒开发者。