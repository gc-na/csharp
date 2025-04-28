<!--
Meta Description: # C# 中的 Decimal 數據類型：精確的浮點數處理 ## 簡介 在 C# 中，`decimal` 是一種高精度的數據類型，特別適用於需要精確計算的場景，例如財務計算和貨幣運算。它可提供比 `float` 和 `double` 更高的精度，並能有效避免浮點數計算中的誤差。 ## 文檔 ### ...
Meta Keywords: decimal, csharp, double, float, 228
-->

# C# 中的 Decimal 數據類型：精確的浮點數處理

## 簡介
在 C# 中，`decimal` 是一種高精度的數據類型，特別適用於需要精確計算的場景，例如財務計算和貨幣運算。它可提供比 `float` 和 `double` 更高的精度，並能有效避免浮點數計算中的誤差。

## 文檔
### 目的
`decimal` 數據類型設計用來解決浮點數計算中的精度問題，特別是在金融應用中，確保運算結果的準確性和可預測性。

### 用法
在 C# 中，`decimal` 的定義如下：

```csharp
decimal variableName;
```

`decimal` 的取值範圍是從 -79,228,162,514,264,337,593,543,950,335 到 79,228,162,514,264,337,593,543,950,335，精度為 28-29 位數字。通常用於表示金額或高精度計算。

### 詳細資訊
- **存儲大小**：`decimal` 佔用 128 位元（16 字節）的內存。
- **數學運算**：支持基本的數學運算，如加、減、乘、除。
- **格式化**：可以使用 `ToString()` 方法和格式化字符串來輸出指定格式的數字。
- **初始化**：可以直接賦值，也可以通過 `decimal` 的構造函數來初始化。

## 範例
以下是一些 `decimal` 的基本用法範例：

### 範例 1：基本初始化
```csharp
decimal price = 19.99m; // 使用 m 或 M 後綴來表示 decimal 類型
```

### 範例 2：簡單計算
```csharp
decimal a = 10.5m;
decimal b = 3.2m;
decimal sum = a + b;  // sum 的值為 13.7
```

### 範例 3：格式化輸出
```csharp
decimal amount = 123456.789m;
Console.WriteLine(amount.ToString("C")); // 輸出金額格式
```

### 範例 4：高精度計算
```csharp
decimal interestRate = 0.05m; // 5% 利率
decimal principal = 1000.00m;
decimal interest = principal * interestRate; // interest 的值為 50.00
```

## 解釋
在使用 `decimal` 時，需要注意以下幾點：
- **後綴**：在數字後加上 `m` 或 `M`，以明確表示這是一個 `decimal` 類型，否則 C# 會認為這是 `double` 類型。
- **性能考量**：雖然 `decimal` 提供了更高的精度，但相較於 `float` 和 `double`，其性能會稍遜，因此在對性能要求極高的場景中，應謹慎使用。
- **四捨五入**：在進行計算時，可能需要使用 `Math.Round()` 方法來控制小數位數的四捨五入。

## 總結
`decimal` 是 C# 中一種高精度的數據類型，適合於財務計算和需要精確處理的場景，能有效避免浮點數的計算誤差。