<!--
Meta Description: # C# 中的 sbyte：使用與特性詳解 ## 摘要 `sbyte` 是 C# 語言中的一種數據類型，用於表示有符號的 8 位整數，範圍從 -128 到 127，適合用於需要節省內存的場景。 ## 文檔 `sbyte` 是 C# 中的基本數據類型之一，屬於整數類型。它由 8 位組成，並且可以存儲正...
Meta Keywords: sbyte, num1, num2, sum, console
-->

# C# 中的 sbyte：使用與特性詳解

## 摘要
`sbyte` 是 C# 語言中的一種數據類型，用於表示有符號的 8 位整數，範圍從 -128 到 127，適合用於需要節省內存的場景。

## 文檔
`sbyte` 是 C# 中的基本數據類型之一，屬於整數類型。它由 8 位組成，並且可以存儲正數和負數。這種數據類型特別適合用於需要限制數值範圍的情況，例如在與二進制數據交互時，或需要控制內存佔用的應用中。

### 用法
在 C# 中，可以通過以下方式聲明和使用 `sbyte`：

```csharp
sbyte myValue = -100; // 初始化一個 sbyte 變量
```

`sbyte` 的值可以進行基本的數學運算，如加法、減法、乘法和除法。需要注意的是，進行運算時，若結果超出 `sbyte` 的範圍，將會導致溢出錯誤。

## 範例
以下是一些 `sbyte` 的基本使用範例：

```csharp
using System;

class Program
{
    static void Main()
    {
        sbyte num1 = 10;
        sbyte num2 = -20;
        
        // 加法
        sbyte sum = (sbyte)(num1 + num2);
        Console.WriteLine("Sum: " + sum); // 輸出: Sum: -10

        // 減法
        sbyte difference = (sbyte)(num1 - num2);
        Console.WriteLine("Difference: " + difference); // 輸出: Difference: 30

        // 乘法
        sbyte product = (sbyte)(num1 * num2);
        Console.WriteLine("Product: " + product); // 輸出: Product: -200

        // 除法
        sbyte quotient = (sbyte)(num1 / 2);
        Console.WriteLine("Quotient: " + quotient); // 輸出: Quotient: 5
    }
}
```

## 解釋
在使用 `sbyte` 時，有幾個常見的注意事項：

1. **範圍限制**：`sbyte` 的範圍是 -128 到 127，超出此範圍的數值會導致溢出錯誤。
2. **類型轉換**：在進行數學運算時，可能需要顯式地將結果轉換回 `sbyte` 型別，因為運算結果的類型通常會提升為 `int`。
3. **性能考量**：雖然 `sbyte` 可以節省內存，但在某些情況下，使用 `int` 可能會提高性能，因為現代處理器通常對整數運算優化以 `int` 為主。

## 一句總結
`sbyte` 是 C# 中用於表示有符號 8 位整數的數據類型，範圍從 -128 到 127，適合用於內存敏感的應用。