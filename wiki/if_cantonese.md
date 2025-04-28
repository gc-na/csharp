<!--
Meta Description: # CSharp 的 "if" 條件語句：用法及示例 ## 概述 在 CSharp 編程語言中，"if" 條件語句是一個基礎的控制結構，用於根據特定條件執行不同的程式碼區塊。 ## 文檔 ### 目的 "if" 條件語句的主要目的是讓開發者能根據條件的真偽來決定程式的執行路徑。這使得程式能夠進行邏輯...
Meta Keywords: else, csharp, number, console, writeline
-->

# CSharp 的 "if" 條件語句：用法及示例

## 概述
在 CSharp 編程語言中，"if" 條件語句是一個基礎的控制結構，用於根據特定條件執行不同的程式碼區塊。

## 文檔
### 目的
"if" 條件語句的主要目的是讓開發者能根據條件的真偽來決定程式的執行路徑。這使得程式能夠進行邏輯判斷和決策。

### 用法
基本的 "if" 語法如下：
```csharp
if (條件)
{
    // 當條件為 true 時執行的程式碼
}
```
此外，"if" 語句還可以與 "else" 和 "else if" 結構結合使用，以處理多個條件：
```csharp
if (條件1)
{
    // 當條件1為 true 時執行的程式碼
}
else if (條件2)
{
    // 當條件2為 true 時執行的程式碼
}
else
{
    // 當所有條件都不為 true 時執行的程式碼
}
```

## 示例
以下是 "if" 條件語句的基本使用示例：

### 示例 1：基本的 if 語句
```csharp
int number = 10;
if (number > 5)
{
    Console.WriteLine("數字大於 5");
}
```

### 示例 2：使用 else 語句
```csharp
int number = 3;
if (number > 5)
{
    Console.WriteLine("數字大於 5");
}
else
{
    Console.WriteLine("數字不大於 5");
}
```

### 示例 3：使用 else if 語句
```csharp
int number = 5;
if (number > 5)
{
    Console.WriteLine("數字大於 5");
}
else if (number == 5)
{
    Console.WriteLine("數字等於 5");
}
else
{
    Console.WriteLine("數字小於 5");
}
```

## 解釋
使用 "if" 條件語句時，開發者需要注意以下幾個常見問題：
- **條件的布爾值**：條件必須返回布爾值（true 或 false）。使用其他類型（如整數或字串）時可能會導致編譯錯誤。
- **代碼塊的範圍**：即使只有一條語句，也建議使用大括號來明確代碼範圍，這樣可以避免未來的維護問題。
- **嵌套 if 語句**：雖然可以嵌套多層 "if" 語句，但這可能會使程式碼變得難以閱讀，應謹慎使用。

## 一行總結
在 CSharp 中，"if" 條件語句是用於根據特定條件來執行程式碼區塊的基本控制結構。