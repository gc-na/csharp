<!--
Meta Description: # CSharp 中的 sbyte 資料類型：用途與範例 ## 概述 `sbyte` 是 CSharp 程式語言中的一種整數資料類型，代表有符號的 8 位元整數，範圍從 -128 到 127。它適合用於需要節省記憶體且數值範圍較小的情況。 ## 文檔 在 CSharp 中，`sbyte` 是一個基本...
Meta Keywords: sbyte, csharp, maxvalue, minvalue, console
-->

# CSharp 中的 sbyte 資料類型：用途與範例

## 概述
`sbyte` 是 CSharp 程式語言中的一種整數資料類型，代表有符號的 8 位元整數，範圍從 -128 到 127。它適合用於需要節省記憶體且數值範圍較小的情況。

## 文檔
在 CSharp 中，`sbyte` 是一個基本資料類型，專門設計用來存儲小範圍的整數值。由於其佔用 1 個位元組的記憶體，`sbyte` 常用於需要高效能的應用，特別是在處理大量數據時。`sbyte` 的用途包括但不限於：

- 儲存小範圍的數值以節省記憶體。
- 在需要有符號整數的情況下進行計算。
- 與其他數據結構（如陣列）結合使用時，提升效能。

### 使用方式
`sbyte` 的宣告方式如下：
```csharp
sbyte myValue = -5;
```
在這個例子中，`myValue` 被初始化為 -5，這是有效的因為它在 `sbyte` 的範圍內。

## 範例
以下是一些 `sbyte` 的基本使用範例：

```csharp
using System;

class Program
{
    static void Main()
    {
        sbyte a = 100;
        sbyte b = -50;
        sbyte sum = (sbyte)(a + b);
        
        Console.WriteLine("a + b = " + sum); // 輸出：a + b = 50

        sbyte maxValue = sbyte.MaxValue; // 127
        sbyte minValue = sbyte.MinValue; // -128

        Console.WriteLine("最大值：" + maxValue);
        Console.WriteLine("最小值：" + minValue);
    }
}
```

## 解釋
使用 `sbyte` 時需要注意以下幾點：

- **溢出問題**：由於 `sbyte` 的範圍有限，當進行加法或其他運算時，若結果超過其範圍，將會發生溢出，這可能導致意外的結果。例如，`sbyte.MaxValue + 1` 將會導致值環繞至 `sbyte.MinValue`。
  
- **類型轉換**：進行數學運算時，`sbyte` 可能會自動轉換為 `int`，因此在賦值時需注意強制轉換，特別是在進行運算後。

- **性能考量**：在需要大量整數運算的情況下，選擇 `sbyte` 可以有效降低記憶體佔用。但若範圍要求較大，則應考慮使用其他整數類型如 `short` 或 `int`。

## 一句總結
`sbyte` 是 CSharp 中用來表示有符號 8 位元整數的資料類型，適合用於小範圍的整數計算及記憶體效率的需求。