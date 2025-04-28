<!--
Meta Description: # CSharp 中的 params 關鍵字：靈活參數傳遞的利器 ## 簡介 在 CSharp 中，`params` 關鍵字允許開發者在方法中傳遞可變數量的參數，從而讓方法的使用變得更加靈活和方便。 ## 文檔 `params` 是一個修飾符，可以放在方法的參數列表中。當使用 `params` 時，...
Meta Keywords: params, 打印數字, csharp, public, int
-->

# CSharp 中的 params 關鍵字：靈活參數傳遞的利器

## 簡介
在 CSharp 中，`params` 關鍵字允許開發者在方法中傳遞可變數量的參數，從而讓方法的使用變得更加靈活和方便。

## 文檔
`params` 是一個修飾符，可以放在方法的參數列表中。當使用 `params` 時，開發者可以將多個參數傳遞給方法，而無需明確定義每個參數的數量。這對於需要處理不確定數量的數據的情況特別有用。

### 目的
`params` 的主要目的是簡化代碼，減少過載方法的需求，並提高方法的可讀性。

### 使用方式
在方法定義中，`params` 必須是最後一個參數，並且只允許一個 `params` 參數。這樣的方法可以接受數組或多個相同類型的參數。

```csharp
public void 打印數字(params int[] 數字們)
{
    foreach (int 數字 in 數字們)
    {
        Console.WriteLine(數字);
    }
}
```

## 範例
以下是使用 `params` 的基本例子：

```csharp
public class 範例
{
    public void 打印數字(params int[] 數字們)
    {
        foreach (int 數字 in 數字們)
        {
            Console.WriteLine(數字);
        }
    }

    public void 示範()
    {
        打印數字(1, 2, 3); // 輸出：1 2 3
        打印數字(4, 5);    // 輸出：4 5
        打印數字();        // 無輸出
    }
}
```

在這個例子中，`打印數字` 方法可以接受任意數量的整數參數，並打印出來。

## 說明
在使用 `params` 時，有幾個常見的注意事項：

- `params` 參數必須是方法參數列表中的最後一個參數。
- 只允許一個 `params` 參數，且該參數類型必須為數組。
- 如果方法被調用時沒有提供任何參數，則 `params` 參數將是一個空數組，而不是 `null`。

這些特性使得 `params` 成為一個強大且靈活的工具，但也需要小心使用，以避免不必要的錯誤或混淆。

## 一句總結
在 CSharp 中，`params` 關鍵字允許方法接受可變數量的參數，使得代碼更加靈活和可讀。