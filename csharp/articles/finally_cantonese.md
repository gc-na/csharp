<!--
Meta Description: # CSharp 的「finally」關鍵字：確保資源釋放的最佳實踐 ## 概述 在 CSharp 中，「finally」是一個重要的關鍵字，用於確保在異常處理時，無論是否發生異常，都能執行清理代碼。它通常與 try-catch 塊一起使用，幫助開發者在確保資源釋放方面達到最佳實踐。 ## 文檔 #...
Meta Keywords: finally, try, catch, filestream, csharp
-->

# CSharp 的「finally」關鍵字：確保資源釋放的最佳實踐

## 概述
在 CSharp 中，「finally」是一個重要的關鍵字，用於確保在異常處理時，無論是否發生異常，都能執行清理代碼。它通常與 try-catch 塊一起使用，幫助開發者在確保資源釋放方面達到最佳實踐。

## 文檔
### 目的
「finally」塊的主要目的是無論 try 塊中發生的任何異常如何，都能確保特定的代碼執行。這對於釋放資源（如文件、網絡連接或數據庫連接）至關重要。

### 使用方法
在 CSharp 中，「finally」通常用於以下結構：

```csharp
try
{
    // 嘗試執行的代碼
}
catch (Exception ex)
{
    // 處理異常的代碼
}
finally
{
    // 總是執行的代碼
}
```

在 try 塊中執行的代碼如果發生異常，catch 塊將處理該異常，而 finally 塊將始終執行，無論是否發生異常。

### 詳細說明
- **語法**：在 try-catch 結構中添加 finally 塊。
- **執行順序**：若 try 塊中無異常發生，finally 塊仍然會執行；即使 catch 塊已經處理了異常，finally 塊也會執行。
- **不會被跳過**：即使在 try 或 catch 塊中使用了 return 語句，finally 塊依然會被執行。

## 示例
### 基本用法示例
```csharp
using System;

class Program
{
    static void Main()
    {
        FileStream fileStream = null;

        try
        {
            fileStream = new FileStream("example.txt", FileMode.Open);
            // 其他操作
        }
        catch (FileNotFoundException e)
        {
            Console.WriteLine("文件未找到: " + e.Message);
        }
        finally
        {
            if (fileStream != null)
            {
                fileStream.Close();
                Console.WriteLine("文件流已關閉。");
            }
        }
    }
}
```

在這個示例中，無論是否發生 FileNotFoundException，finally 塊都會確保 fileStream 被正確關閉。

## 解釋
### 常見陷阱
- **資源未釋放**：如果開發者不小心在 try 塊中發生異常，且未在 finally 塊中進行資源釋放，可能會導致資源洩漏。
- **多重返回**：在 try 或 catch 塊中使用 return 語句，可能會讓開發者誤以為 finally 塊不會執行，但事實上它會執行。
- **例外處理**：在 finally 塊中拋出異常會遮蓋之前的異常，這可能會導致難以追踪的錯誤。

## 一句總結
「finally」關鍵字用於 CSharp 中的異常處理，確保清理代碼無論異常是否發生都能執行。