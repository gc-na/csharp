<!--
Meta Description: # C# 中的 else 語句：用法與示例 ## 概述 在 C# 程式設計中，`else` 語句是一種控制流語句，用於在條件語句（如 `if`）為假時執行替代的程式碼區塊。這使得開發者能夠根據不同的條件執行不同的程式邏輯。 ## 文檔 `else` 語句的主要目的是提供一個備選方案，當 `if` 條...
Meta Keywords: else, console, writeline, csharp, condition
-->

# C# 中的 else 語句：用法與示例

## 概述
在 C# 程式設計中，`else` 語句是一種控制流語句，用於在條件語句（如 `if`）為假時執行替代的程式碼區塊。這使得開發者能夠根據不同的條件執行不同的程式邏輯。

## 文檔
`else` 語句的主要目的是提供一個備選方案，當 `if` 條件為假時，能夠執行一段特定的程式碼。它通常與 `if` 語句一起使用，以構建更複雜的邏輯判斷。

### 語法
```csharp
if (condition)
{
    // 當 condition 為 true 時執行的程式碼
}
else
{
    // 當 condition 為 false 時執行的程式碼
}
```

### 使用方法
1. **基本結構**：`else` 語句必須跟隨在 `if` 語句之後，並且必須在 `if` 語句的條件不滿足時執行。
2. **多層次條件**：可以與 `else if` 組合使用，以檢查多個條件。
3. **不需要條件**：`else` 語句本身不需要任何條件，直接執行其內部的程式碼。

## 示例
### 基本用法
```csharp
int number = 10;

if (number > 0)
{
    Console.WriteLine("數字是正數");
}
else
{
    Console.WriteLine("數字是負數或零");
}
```

### 使用 else if
```csharp
int score = 85;

if (score >= 90)
{
    Console.WriteLine("成績：A");
}
else if (score >= 80)
{
    Console.WriteLine("成績：B");
}
else
{
    Console.WriteLine("成績：C或更低");
}
```

## 解釋
- **常見陷阱**：在使用 `else` 時，需要確保 `if` 條件的邏輯正確，否則可能導致預期之外的行為。 
- **代碼可讀性**：過多的嵌套 `if-else` 結構可能使代碼變得難以閱讀和維護，因此可以考慮使用其他結構如 switch 語句或策略模式來提高代碼的清晰度。
- **邊界條件**：特別注意條件的邊界情況，如在數字比較中，確保不會漏掉某些情況（例如，零的處理）。

## 總結
`else` 語句在 C# 中是控制程式流程的重要工具，能根據不同的條件執行不同的邏輯。正確使用 `else` 可以提高代碼的靈活性與可讀性。