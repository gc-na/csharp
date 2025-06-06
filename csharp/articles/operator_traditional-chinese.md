<!--
Meta Description: # C# 中的運算子 (Operator) - 完整指南 ## 概述 在 C# 程式設計中，運算子是執行特定操作的符號或關鍵字。這些操作可以是數學計算、邏輯判斷、位元操作等。了解運算子的使用對於寫出高效且可讀的 C# 程式碼至關重要。 ## 文檔 運算子在 C# 中可以分為幾類，包括： 1. **算...
Meta Keywords: int, bool, csharp, 小於或等於, 算術運算子
-->

# C# 中的運算子 (Operator) - 完整指南

## 概述
在 C# 程式設計中，運算子是執行特定操作的符號或關鍵字。這些操作可以是數學計算、邏輯判斷、位元操作等。了解運算子的使用對於寫出高效且可讀的 C# 程式碼至關重要。

## 文檔
運算子在 C# 中可以分為幾類，包括：
1. **算術運算子**：用於執行數學運算，如加法（`+`）、減法（`-`）、乘法（`*`）、除法（`/`）和取餘（`%`）。
2. **關係運算子**：用於比較兩個值，如等於（`==`）、不等於（`!=`）、大於（`>`）、小於（`<`）、大於或等於（`>=`）、小於或等於（`<=`）。
3. **邏輯運算子**：用於處理布林值的運算，如邏輯與（`&&`）、邏輯或（`||`）、邏輯非（`!`）。
4. **位元運算子**：用於操作位元，如位元與（`&`）、位元或（`|`）、位元異或（`^`）、左移（`<<`）、右移（`>>`）。
5. **條件運算子**：三元運算子（`?:`），用於簡化條件語句。
6. **賦值運算子**：用於給變數賦值，如簡單賦值（`=`）及複合賦值運算子（如 `+=`, `-=` 等）。

每個運算子都有其特定的用途和運作方式，掌握這些運算子能夠提升程式的效率和可讀性。

## 範例
以下是一些常見運算子的基本用法示範：

### 算術運算子
```csharp
int a = 10;
int b = 5;
int sum = a + b;        // 加法
int difference = a - b; // 減法
int product = a * b;    // 乘法
int quotient = a / b;   // 除法
int remainder = a % b;  // 取餘
```

### 關係運算子
```csharp
bool isEqual = (a == b);     // 等於
bool isNotEqual = (a != b);  // 不等於
bool isGreater = (a > b);    // 大於
bool isLessOrEqual = (a <= b); // 小於或等於
```

### 邏輯運算子
```csharp
bool condition1 = true;
bool condition2 = false;
bool result = condition1 && condition2; // 邏輯與
```

### 三元運算子
```csharp
string result = (a > b) ? "a 大於 b" : "a 小於或等於 b";
```

## 解釋
使用運算子時要特別注意以下幾點：
- **優先順序**：運算子的優先順序可能會影響表達式的結果，應該清楚不同運算子的優先級。
- **類型轉換**：在運算中，若不同類型的變數混合使用，可能會自動進行類型轉換，這有時會導致意外的結果。
- **空值檢查**：在進行運算時，對於可能為 `null` 的變數，需特別小心，避免引發空引用異常。

## 一句總結
運算子是 C# 程式設計的基礎工具，能夠實現各種數學、邏輯和位元操作。