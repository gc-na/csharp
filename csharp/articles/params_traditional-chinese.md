<!--
Meta Description: # C# 中的 params 關鍵字：靈活的參數傳遞 ## 概述 在 C# 中，`params` 關鍵字允許方法接收可變數量的參數，這使得方法能夠更靈活地處理不同數量的輸入。 ## 文件說明 `params` 關鍵字用於方法的參數列表中，指定該參數可以接受不定數量的數據，這些數據會被自動轉換為一個數...
Meta Keywords: params, sum, int, console, writeline
-->

# C# 中的 params 關鍵字：靈活的參數傳遞

## 概述
在 C# 中，`params` 關鍵字允許方法接收可變數量的參數，這使得方法能夠更靈活地處理不同數量的輸入。

## 文件說明
`params` 關鍵字用於方法的參數列表中，指定該參數可以接受不定數量的數據，這些數據會被自動轉換為一個數組。這對於需要接受多個參數的方法特別有用，能夠簡化方法調用的語法。

### 目的
使用 `params` 可以提高方法的靈活性，允許開發者在不必事先確定參數數量的情況下，方便地傳遞多個值。

### 使用方法
- `params` 必須是方法的最後一個參數。
- 只能有一個 `params` 參數。
- 在方法調用時，可以傳入任意數量的該類型的參數，甚至可以不傳參數。

### 詳細說明
當使用 `params` 時，C# 編譯器會自動將傳入的參數打包成一個數組。這使得可以像操作數組一樣操作這些參數。需要注意的是，`params` 參數的類型必須是一致的，且必須是可變長度的類型。

## 示例
以下是 `params` 的基本用法示例：

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine(Sum(1, 2, 3)); // 輸出 6
        Console.WriteLine(Sum(5, 10, 15, 20)); // 輸出 50
        Console.WriteLine(Sum()); // 輸出 0
    }

    static int Sum(params int[] numbers)
    {
        int total = 0;
        foreach (int number in numbers)
        {
            total += number;
        }
        return total;
    }
}
```

## 解釋
在使用 `params` 時，有一些常見的陷阱和注意事項：
- **類型一致性**：所有傳入的參數必須是相同的類型，否則將導致編譯錯誤。
- **唯一性**：一個方法中只能有一個 `params` 參數，不能與其他數組參數共存。
- **空參數**：如果不傳入任何參數，將會傳遞一個空陣列，這在某些情況下可能會導致意外的行為。

## 總結
C# 中的 `params` 關鍵字使得方法可以接受不定數量的參數，從而提高了靈活性和可讀性。