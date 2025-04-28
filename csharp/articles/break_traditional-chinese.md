<!--
Meta Description: # C# 中的 "break" 命令：用於控制流程的關鍵字 ## 簡介 在 C# 編程語言中，`break` 是一個關鍵字，用於立即終止循環或 `switch` 語句的執行。此命令使程序在滿足特定條件時能夠跳出當前的執行上下文。 ## 文件說明 ### 目的 `break` 命令的主要目的是控制程序...
Meta Keywords: break, switch, case, console, writeline
-->

# C# 中的 "break" 命令：用於控制流程的關鍵字

## 簡介
在 C# 編程語言中，`break` 是一個關鍵字，用於立即終止循環或 `switch` 語句的執行。此命令使程序在滿足特定條件時能夠跳出當前的執行上下文。

## 文件說明
### 目的
`break` 命令的主要目的是控制程序的流程，尤其是在循環（如 `for`、`while` 和 `do-while`）和 `switch` 語句中。當執行到 `break` 時，程序將跳出當前的循環或 `switch`，並繼續執行後面的代碼。

### 用法
`break` 通常用於：
- 終止循環：在滿足特定條件時，停止迭代。
- 終止 `switch` 語句：在匹配到特定 case 後，停止執行。

#### 語法範例：
```csharp
break;
```

## 示例
### 基本用法示例
#### 在循環中使用 `break`
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // 當 i 等於 5 時，跳出循環
    }
    Console.WriteLine(i);
}
```
執行結果：
```
0
1
2
3
4
```

#### 在 `switch` 語句中使用 `break`
```csharp
int day = 3;
switch (day)
{
    case 1:
        Console.WriteLine("星期一");
        break; // 結束當前 case 的執行
    case 2:
        Console.WriteLine("星期二");
        break;
    case 3:
        Console.WriteLine("星期三");
        break;
    default:
        Console.WriteLine("其他日子");
        break;
}
```
執行結果：
```
星期三
```

## 解釋
### 常見陷阱
- **遺漏 `break`**：在 `switch` 語句中，如果未在每個 case 的末尾使用 `break`，將會導致「fall-through」，即執行到下一個 case 的代碼，這可能不是預期的行為。
  
- **在不支持的上下文中使用**：`break` 只能在循環或 `switch` 內部使用，若在其他上下文中使用，編譯器將報錯。

### 附加說明
`break` 是一個非常有用的控制流程工具，但在使用時應謹慎考慮其影響，特別是在複雜的邏輯結構中。

## 一句總結
`break` 是 C# 中用於立即終止循環和 `switch` 語句的關鍵字，能有效控制程序流。