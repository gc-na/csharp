<!--
Meta Description: # C# 中的 double 數據類型：深度解析與使用指南 ## 簡介 在 C# 中，`double` 是一種用於表示雙精度浮點數的數據類型，適合需要高精度的小數運算，廣泛應用於科學計算、財務計算及其他需要精確數值的場合。 ## 文檔 ### 目的 `double` 類型是 .NET 框架中基本數據...
Meta Keywords: double, csharp, console, writeline, radius
-->

# C# 中的 double 數據類型：深度解析與使用指南

## 簡介
在 C# 中，`double` 是一種用於表示雙精度浮點數的數據類型，適合需要高精度的小數運算，廣泛應用於科學計算、財務計算及其他需要精確數值的場合。

## 文檔
### 目的
`double` 類型是 .NET 框架中基本數據類型之一，專門用於存儲帶有小數的數值。其使用 IEEE 754 標準來表示，能夠提供約 15-16 位數字的精度。

### 用法
在 C# 中，`double` 可以直接用於變量聲明、數學運算及各種數據處理。它的範圍約為 ±5.0 × 10^−324 到 ±1.7 × 10^308。

#### 聲明示例
```csharp
double myNumber = 3.14;
```

#### 數學運算示例
```csharp
double a = 10.5;
double b = 2.5;
double sum = a + b; // 13.0
double product = a * b; // 26.25
```

## 示例
### 基本用法
以下是一些使用 `double` 的基本示例：

#### 示例 1：基本數值賦值
```csharp
double pi = 3.14159;
Console.WriteLine(pi); // 輸出：3.14159
```

#### 示例 2：數值運算
```csharp
double radius = 2.5;
double area = Math.PI * radius * radius;
Console.WriteLine(area); // 輸出：19.634954084936208
```

#### 示例 3：類型轉換
```csharp
int intValue = 10;
double doubleValue = (double)intValue; // 類型轉換
Console.WriteLine(doubleValue); // 輸出：10.0
```

## 解釋
### 常見陷阱
- **精度問題**：由於浮點數的表示限制，某些小數無法精確表示。使用 `double` 時，可能會遇到計算結果不如預期的情況。
- **比較操作**：在比較 `double` 值時，應避免直接使用 `==`，因為可能因精度因素導致比較失敗。建議使用一個容差範圍進行比較。
  
  ```csharp
  double a = 0.1 + 0.2;
  double b = 0.3;
  bool areEqual = Math.Abs(a - b) < 0.0001; // 使用容差範圍
  ```

## 一行總結
`double` 是 C# 中用於表示雙精度浮點數的數據類型，適合高精度的小數運算。