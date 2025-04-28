<!--
Meta Description: # C# 中的 "using" 語句：用法與最佳實踐 ## 摘要 在 C# 中，`using` 語句是一種方便的工具，主要用於自動管理資源的釋放。它通常用於需要實現 `IDisposable` 接口的物件，確保在使用後能夠正確釋放資源，從而避免資源泄漏。 ## 文檔 `using` 語句有兩個主要用...
Meta Keywords: using, csharp, var, new, system
-->

# C# 中的 "using" 語句：用法與最佳實踐

## 摘要
在 C# 中，`using` 語句是一種方便的工具，主要用於自動管理資源的釋放。它通常用於需要實現 `IDisposable` 接口的物件，確保在使用後能夠正確釋放資源，從而避免資源泄漏。

## 文檔
`using` 語句有兩個主要用途：

1. **資源管理**：當創建並使用需要手動釋放的資源（例如文件、網路連接或資料庫連接）時，`using` 語句能確保在使用完後自動調用 `Dispose` 方法，釋放資源。
  
   ```csharp
   using (var stream = new FileStream("example.txt", FileMode.Open))
   {
       // 使用 stream
   } // 在這裡，stream 自動被釋放
   ```

2. **命名空間引入**：`using` 語句也用於引入命名空間，這樣可以在不需要使用完整命名空間的情況下訪問類和方法，從而提高代碼的可讀性。
   
   ```csharp
   using System;
   using System.Collections.Generic;

   class Program
   {
       static void Main()
       {
           Console.WriteLine("Hello, World!");
       }
   }
   ```

## 示例
以下是使用 `using` 語句的基本示例：

### 使用範例 1：資源管理
```csharp
using (var reader = new StreamReader("file.txt"))
{
    string content = reader.ReadToEnd();
    Console.WriteLine(content);
} // StreamReader 會自動被釋放
```

### 使用範例 2：命名空間引入
```csharp
using System;
using System.Linq;

class Example
{
    static void Main()
    {
        var numbers = new[] { 1, 2, 3, 4, 5 };
        var sum = numbers.Sum();
        Console.WriteLine($"Sum: {sum}");
    }
}
```

## 解釋
使用 `using` 語句時，開發者需注意以下幾點：

- **多個資源**：當需要使用多個資源時，可以使用逗號分隔。例如：
  ```csharp
  using (var resource1 = new Resource1(), resource2 = new Resource2())
  {
      // 使用資源
  }
  ```

- **嵌套使用**：在一個 `using` 語句內部，可以嵌套其他 `using` 語句，以更精確地控制資源的釋放。

- **異常處理**：即使在 `using` 代碼塊內發生異常，`Dispose` 方法仍會被調用，這是確保資源正確釋放的關鍵。

- **不適用於非 `IDisposable` 對象**：只有實現了 `IDisposable` 接口的類型才能使用 `using` 語句，否則編譯器將報錯。

## 簡單總結
`using` 語句在 C# 中用於自動管理資源的釋放，確保在使用完後能夠正確調用 `Dispose` 方法，從而避免資源泄漏。