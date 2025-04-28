<!--
Meta Description: # C# 中的 bool 型別：完全指南 ## 簡介 在 C# 程式語言中，`bool` 型別是用來表示布林值，這些值僅限於 `true` 和 `false`。這一型別在控制程式流程（如條件判斷）上扮演著關鍵角色。 ## 文檔 `bool` 是 C# 的基本數據類型之一，主要用於儲存邏輯值。它的主要...
Meta Keywords: bool, console, writeline, true, false
-->

# C# 中的 bool 型別：完全指南

## 簡介
在 C# 程式語言中，`bool` 型別是用來表示布林值，這些值僅限於 `true` 和 `false`。這一型別在控制程式流程（如條件判斷）上扮演著關鍵角色。

## 文檔
`bool` 是 C# 的基本數據類型之一，主要用於儲存邏輯值。它的主要用途是在條件語句中，如 `if` 語句、`while` 循環和邏輯運算符，來決定程式的執行路徑。`bool` 型別的變數只能被賦值為 `true` 或 `false`，這使得它在邏輯運算中非常重要。

### 用法
在 C# 中，您可以這樣宣告一個 `bool` 型別的變數：

```csharp
bool isActive = true;
bool isCompleted = false;
```

在條件判斷中，您可以使用 `bool` 變數來控制程式的執行：

```csharp
if (isActive)
{
    Console.WriteLine("活動是啟用的。");
}
else
{
    Console.WriteLine("活動是停用的。");
}
```

## 示例
以下是一些基本的 `bool` 型別使用範例：

### 範例 1：基本變數設定

```csharp
bool isRaining = false;
bool isSunny = true;

Console.WriteLine($"正在下雨: {isRaining}");
Console.WriteLine($"陽光明媚: {isSunny}");
```

### 範例 2：條件語句

```csharp
bool hasPermission = true;

if (hasPermission)
{
    Console.WriteLine("您有訪問權限。");
}
else
{
    Console.WriteLine("您沒有訪問權限。");
}
```

### 範例 3：邏輯運算

```csharp
bool hasKey = true;
bool isDoorLocked = false;

if (hasKey && !isDoorLocked)
{
    Console.WriteLine("您可以進入。");
}
else
{
    Console.WriteLine("您無法進入。");
}
```

## 解釋
在使用 `bool` 型別時，有幾個常見的陷阱需要注意：

1. **布林值的初始值**：未初始化的 `bool` 變數會導致編譯錯誤，因此必須在使用前進行賦值。
2. **邏輯運算符**：在進行邏輯運算時，確保您正確使用 `&&`（與）和 `||`（或）運算符，以避免邏輯錯誤。
3. **強制轉換**：在某些情況下，布林值可能需要與其他類型進行比較，請注意這可能會導致編譯錯誤或不正確的結果。

## 總結
在 C# 中，`bool` 型別是處理邏輯值的基礎，僅能為 `true` 或 `false`，並在控制程式流程中發揮著重要作用。