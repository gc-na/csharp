<!--
Meta Description: # C# 中的 "catch" 命令：捕獲異常的關鍵字 ## 摘要 在 C# 編程中，`catch` 是一個關鍵字，用於捕獲和處理異常。它是異常處理機制的一部分，允許開發者優雅地管理錯誤和異常情況，以確保應用程序的穩定性。 ## 文檔 `catch` 關鍵字用於從 `try` 區塊中捕獲拋出的異常。...
Meta Keywords: catch, try, console, writeline, filestream
-->

# C# 中的 "catch" 命令：捕獲異常的關鍵字

## 摘要
在 C# 編程中，`catch` 是一個關鍵字，用於捕獲和處理異常。它是異常處理機制的一部分，允許開發者優雅地管理錯誤和異常情況，以確保應用程序的穩定性。

## 文檔
`catch` 關鍵字用於從 `try` 區塊中捕獲拋出的異常。在 C# 中，異常是指在程序執行時發生的錯誤，這些錯誤可能會導致程序崩潰。通過使用 `try-catch` 結構，開發者可以將可能引發異常的代碼放入 `try` 區塊中，並在 `catch` 區塊中處理這些異常。

### 用法
```csharp
try
{
    // 可能引發異常的代碼
}
catch (ExceptionType ex)
{
    // 處理異常的代碼
}
```

在上面的語法中：
- `try` 區塊包含可能引發異常的代碼。
- `catch` 區塊捕獲指定類型的異常（如 `ExceptionType`），並執行處理代碼。

### 詳細說明
- 可以有多個 `catch` 區塊來處理不同類型的異常。
- 如果 `try` 區塊中的代碼引發異常，控制權會立即轉移到相應的 `catch` 區塊。
- 如果沒有匹配的 `catch` 區塊，異常會繼續傳遞到調用堆疊，最終可能導致應用程序崩潰。
- 可以使用 `finally` 區塊來執行無論是否發生異常都必須執行的代碼。

## 範例
以下是一些基本的使用範例：

### 範例 1：基本的異常捕獲
```csharp
try
{
    int result = 10 / int.Parse("0"); // 這裡會引發異常
}
catch (DivideByZeroException ex)
{
    Console.WriteLine("不能除以零： " + ex.Message);
}
```

### 範例 2：捕獲多種類型的異常
```csharp
try
{
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers[5]); // 這裡會引發異常
}
catch (IndexOutOfRangeException ex)
{
    Console.WriteLine("索引超出範圍： " + ex.Message);
}
catch (Exception ex)
{
    Console.WriteLine("發生了一個異常： " + ex.Message);
}
```

### 範例 3：使用 `finally`
```csharp
FileStream fileStream = null;
try
{
    fileStream = new FileStream("example.txt", FileMode.Open);
}
catch (FileNotFoundException ex)
{
    Console.WriteLine("文件未找到： " + ex.Message);
}
finally
{
    fileStream?.Close(); // 確保文件流被關閉
}
```

## 解釋
使用 `catch` 時有幾個常見的陷阱和注意事項：
- **過度捕獲**：避免捕獲所有異常，特別是使用 `catch (Exception)`，這可能會隱藏其他問題。
- **缺乏詳細信息**：在處理異常時，應提供清晰的錯誤消息，以便於調試。
- **性能問題**：異常處理在性能上可能會有影響，應謹慎使用。

## 一句總結
`catch` 是 C# 中用於捕獲和處理異常的關鍵字，能有效提高應用程序的穩定性和可維護性。