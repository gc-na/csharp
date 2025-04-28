<!--
Meta Description: # CSharp 中的 goto 語句：功能、使用及範例 ## 概述 `goto` 語句是一個在 CSharp 中用來無條件跳轉至程序中其他位置的控制結構。雖然它提供了一種簡單的跳轉方式，但在現代編程中，使用 `goto` 語句並不常見，因為它可能導致代碼可讀性降低。 ## 文檔 ### 目的 `g...
Meta Keywords: goto, csharp, count, startloop, console
-->

# CSharp 中的 goto 語句：功能、使用及範例

## 概述
`goto` 語句是一個在 CSharp 中用來無條件跳轉至程序中其他位置的控制結構。雖然它提供了一種簡單的跳轉方式，但在現代編程中，使用 `goto` 語句並不常見，因為它可能導致代碼可讀性降低。

## 文檔
### 目的
`goto` 語句的主要目的是允許程序在代碼執行過程中跳轉到特定的標籤，這在某些情況下可以簡化代碼的邏輯結構。

### 用法
在 CSharp 中，`goto` 語句的基本語法如下：

```csharp
goto 標籤名稱;
```

標籤名稱必須以字母或下劃線開頭，並且可以包含字母、數字和下劃線。標籤必須在代碼中以冒號結尾。

### 詳細信息
- `goto` 語句可以用於跳轉到同一方法中的任意位置。
- 由於 `goto` 可能會造成難以追蹤的代碼流，建議僅在特定情況下使用，例如在錯誤處理或多重循環時。
- 使用 `goto` 會使代碼難以理解，因此在編寫可維護的代碼時應謹慎使用。

## 範例
以下是使用 `goto` 的基本範例：

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("開始計數...");
        
        int count = 0;
        
    StartLoop:
        count++;
        Console.WriteLine(count);
        
        if (count < 5)
        {
            goto StartLoop; // 跳回 StartLoop 標籤
        }

        Console.WriteLine("計數結束。");
    }
}
```

在這個範例中，程序會從 `StartLoop` 標籤開始，每次增加計數，直到計數達到 5 為止。

## 解釋
### 常見問題
1. **可讀性問題**：使用 `goto` 會使代碼的控制流變得不清晰，特別是當有多個 `goto` 語句時。
2. **錯誤處理**：雖然 `goto` 可以用於簡化錯誤處理，但使用 `try-catch` 結構通常更為合適且可讀性更強。
3. **無法跳出範圍**：`goto` 只能跳轉至在同一方法內的標籤，無法跨方法跳轉。

## 總結
`goto` 語句在 CSharp 中提供了一種無條件跳轉的方式，但應謹慎使用，以避免降低代碼的可讀性和維護性。