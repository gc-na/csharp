<!--
Meta Description: # C# 中的 finally 語句：確保資源的釋放 ## 摘要 在 C# 中，`finally` 語句用於確保無論是否發生異常，特定的代碼塊都會被執行。這通常用於釋放資源，如關閉文件流或數據庫連接。 ## 文件說明 `finally` 是一種控制結構，通常與 `try` 和 `catch` 一起使...
Meta Keywords: finally, try, catch, reader, console
-->

# C# 中的 finally 語句：確保資源的釋放

## 摘要
在 C# 中，`finally` 語句用於確保無論是否發生異常，特定的代碼塊都會被執行。這通常用於釋放資源，如關閉文件流或數據庫連接。

## 文件說明
`finally` 是一種控制結構，通常與 `try` 和 `catch` 一起使用。它的主要目的是確保在異常處理後，仍然能夠執行某些清理代碼。無論 `try` 塊中的代碼是否拋出異常，`finally` 塊中的代碼都會被執行，這使得代碼的清理過程更加可靠。

### 語法
```csharp
try
{
    // 可能會拋出異常的代碼
}
catch (ExceptionType ex)
{
    // 處理異常的代碼
}
finally
{
    // 確保執行的代碼
}
```

### 目的
`finally` 語句的主要目的是：
- 確保資源被釋放，如文件、網絡連接和數據庫連接。
- 提供清理邏輯，即使發生異常也能執行。

## 示例
### 基本用法範例
以下是一個使用 `finally` 語句的範例，展示了如何確保文件在操作完成後被正確關閉：

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        StreamReader reader = null;
        try
        {
            reader = new StreamReader("example.txt");
            string content = reader.ReadToEnd();
            Console.WriteLine(content);
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine("文件未找到: " + ex.Message);
        }
        finally
        {
            if (reader != null)
            {
                reader.Close();
                Console.WriteLine("文件已關閉。");
            }
        }
    }
}
```

## 解釋
### 常見陷阱
- **未能釋放資源**：如果在 `try` 塊中發生異常並且沒有 `finally` 語句，則可能導致資源無法釋放。
- **多重 `catch`**：在多個 `catch` 塊之後，`finally` 仍然會執行，這意味著即使捕獲了異常，清理代碼也會執行。

### 附加注意事項
- `finally` 塊中的代碼無法捕獲任何異常。
- 如果 `try` 塊中的代碼導致系統崩潰（如調用 `Environment.FailFast`），則 `finally` 塊中的代碼將不會執行。

## 一句總結
`finally` 語句在 C# 中用於確保資源的釋放，即使在異常處理後也能執行清理代碼。