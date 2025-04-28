<!--
Meta Description: # C# 中的 ushort：無符號整數類型詳解 ## 概述 `ushort` 是 C# 中的一種無符號整數類型，代表從 0 到 65,535 的整數值。它主要用於需要處理非負數的情況，並且比 `int` 更節省內存。 ## 文檔 ### 目的 `ushort` 類型可以用來儲存無符號的整數值，適合...
Meta Keywords: ushort, number1, csharp, number2, sum
-->

# C# 中的 ushort：無符號整數類型詳解

## 概述
`ushort` 是 C# 中的一種無符號整數類型，代表從 0 到 65,535 的整數值。它主要用於需要處理非負數的情況，並且比 `int` 更節省內存。

## 文檔
### 目的
`ushort` 類型可以用來儲存無符號的整數值，適合用於表示小範圍的數據，如顏色值、計數器等。由於其範圍限制，使用 `ushort` 可以有效減少內存用量。

### 用法
在 C# 中，`ushort` 可以通過以下方式定義變數：
```csharp
ushort myNumber = 50000;
```
`ushort` 的範圍從 0 到 65,535，因此任何超出此範圍的值都會引發溢出錯誤。

### 詳細說明
- **存儲大小**：`ushort` 佔用 2 個字節的內存。
- **預設值**：`ushort` 的預設值為 0。
- **類型轉換**：可以將 `ushort` 轉換為其他整數類型，但在轉換過程中需注意可能的溢出問題。例如：
  ```csharp
  short myShort = (short)myNumber; // 可能會丟失數據
  ```
- **運算**：`ushort` 支持基本的數學運算，但運算結果仍需確保在 `ushort` 的範圍內。

## 示例
以下是 `ushort` 的基本用法示例：
```csharp
using System;

class Program
{
    static void Main()
    {
        ushort number1 = 30000;
        ushort number2 = 20000;
        
        // 加法
        ushort sum = (ushort)(number1 + number2);
        Console.WriteLine("Sum: " + sum); // 輸出 Sum: 50000
        
        // 減法
        ushort difference = (ushort)(number1 - number2);
        Console.WriteLine("Difference: " + difference); // 輸出 Difference: 10000
        
        // 乘法
        ushort product = (ushort)(number1 * 2);
        Console.WriteLine("Product: " + product); // 輸出 Product: 60000
        
        // 除法
        ushort quotient = (ushort)(number1 / 2);
        Console.WriteLine("Quotient: " + quotient); // 輸出 Quotient: 15000
    }
}
```

## 說明
- **常見陷阱**：在進行數學運算時，如果結果超過 `ushort` 的範圍，將會導致溢出，並且結果可能會變成一個負數或非預期的值。可以使用 `checked` 關鍵字來捕獲這種情況：
  ```csharp
  ushort result = checked((ushort)(number1 + number2)); // 如果溢出則會引發例外
  ```
- **初始化問題**：未初始化的 `ushort` 變數會默認為 0，因此在使用之前最好進行明確的初始化。
- **性能考量**：在需要較大數量計算的情況下，使用 `ushort` 可以節省內存，但在某些情況下，使用 `int` 進行計算可能會更快，因為 CPU 通常對 `int` 的支持更好。

## 一句總結
`ushort` 是 C# 中一種有效的無符號整數類型，適合用於處理範圍從 0 到 65,535 的數據。