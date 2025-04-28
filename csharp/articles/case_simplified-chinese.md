<!--
Meta Description: # C# 中的 case 语句：用法与示例 ## 概述 在 C# 中，`case` 语句是 `switch` 语句的一部分，用于根据变量的不同值执行不同的代码块。它使得多重条件判断更加简洁和易读。 ## 文档 `case` 语句的主要目的是允许程序员在处理多个条件时，能够根据特定的值执行不同的代码段...
Meta Keywords: case, break, dayname, switch, default
-->

# C# 中的 case 语句：用法与示例

## 概述
在 C# 中，`case` 语句是 `switch` 语句的一部分，用于根据变量的不同值执行不同的代码块。它使得多重条件判断更加简洁和易读。

## 文档
`case` 语句的主要目的是允许程序员在处理多个条件时，能够根据特定的值执行不同的代码段。`switch` 语句根据变量的值选择合适的 `case` 进行执行。

### 用法
`case` 语句通常与 `switch` 语句一起使用。基本语法如下：

```csharp
switch (expression)
{
    case value1:
        // 执行代码块
        break;
    case value2:
        // 执行代码块
        break;
    default:
        // 执行代码块
        break;
}
```

- `expression` 是被判断的变量或表达式。
- `value1`, `value2` 是可能的值，程序将根据 `expression` 的值匹配相应的 `case`。
- `break` 语句用于退出 `switch` 语句，防止继续执行后续的 `case`。
- `default` 是可选的，用于处理所有未被匹配的情况。

## 示例
以下是一个简单的 `case` 语句示例：

```csharp
int day = 3;
string dayName;

switch (day)
{
    case 1:
        dayName = "星期一";
        break;
    case 2:
        dayName = "星期二";
        break;
    case 3:
        dayName = "星期三";
        break;
    case 4:
        dayName = "星期四";
        break;
    case 5:
        dayName = "星期五";
        break;
    case 6:
        dayName = "星期六";
        break;
    case 7:
        dayName = "星期天";
        break;
    default:
        dayName = "无效的天数";
        break;
}

Console.WriteLine(dayName);  // 输出: 星期三
```

## 解释
在使用 `case` 语句时，开发者应该注意以下几点：

1. **匹配类型**：`case` 的值必须与 `switch` 表达式的数据类型匹配。
2. **缺少 break**：如果没有 `break` 语句，程序会继续执行下一个 `case` 的代码，可能导致意外行为。
3. **使用 default**：尽量使用 `default` 来处理所有未匹配的情况，确保程序的健壮性。
4. **常量表达式**：`case` 中的值必须是常量表达式，不能使用变量。

## 一句话总结
C# 中的 `case` 语句通过 `switch` 结构允许基于变量值的多重条件判断，使代码更清晰易读。