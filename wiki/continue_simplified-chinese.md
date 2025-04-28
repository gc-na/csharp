<!--
Meta Description: # C# 中的 continue 语句详解 ## 摘要 `continue` 语句是 C# 编程语言中的一个控制流语句，用于跳过当前循环的剩余部分并立即开始下一次循环迭代。 ## 文档 `continue` 语句的主要目的是在循环中跳过某些条件下的代码执行。当满足特定条件时，`continue` 语...
Meta Keywords: continue, while, csharp, 循环中使用, 语句时
-->

# C# 中的 continue 语句详解

## 摘要
`continue` 语句是 C# 编程语言中的一个控制流语句，用于跳过当前循环的剩余部分并立即开始下一次循环迭代。

## 文档
`continue` 语句的主要目的是在循环中跳过某些条件下的代码执行。当满足特定条件时，`continue` 语句将使控制流转到循环的下一个迭代，从而跳过当前迭代中剩余的代码。这在处理循环时非常有用，尤其是在需要根据条件有选择性地执行代码时。

### 用法
`continue` 语句可以在 `for`、`foreach`、`while` 和 `do...while` 循环中使用。其基本语法如下：

```csharp
continue;
```

在使用 `continue` 语句时，通常会在循环体内进行条件判断，例如：

```csharp
if (某个条件)
{
    continue; // 跳过当前迭代
}
```

## 示例
以下是 `continue` 语句的基本用法示例：

### 示例 1: 在 for 循环中使用
```csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0)
    {
        continue; // 跳过偶数
    }
    Console.WriteLine(i); // 只打印奇数
}
```

### 示例 2: 在 while 循环中使用
```csharp
int j = 0;
while (j < 10)
{
    j++;
    if (j % 3 == 0)
    {
        continue; // 跳过能被3整除的数
    }
    Console.WriteLine(j); // 打印不是3的倍数的数字
}
```

## 说明
使用 `continue` 语句时，需要注意以下几点：

- `continue` 语句只影响包含它的最近一层循环。如果在嵌套循环中使用，只有内部循环会受到影响，外部循环将继续正常执行。
- 在某些情况下，过度使用 `continue` 可能会导致代码的可读性下降。因此，建议在合适的场合使用，保持代码的清晰性。
- `continue` 语句后面不需要加任何条件或表达式，直接使用 `continue;` 即可。

## 一句话总结
`continue` 语句用于在 C# 循环中跳过当前迭代的剩余部分，直接进入下一次迭代。