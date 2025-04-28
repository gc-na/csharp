<!--
Meta Description: # CSharp 中的「throw」關鍵字：異常處理的基石 ## 簡介 在 CSharp 中，「throw」關鍵字用於引發異常，幫助開發者在程式執行期間處理錯誤和異常情況。這一功能是異常處理機制的核心，允許開發者在程序中捕捉和應對潛在的錯誤。 ## 文檔 ### 目的 「throw」關鍵字的主要目的...
Meta Keywords: throw, csharp, new, argumentnullexception, message
-->

# CSharp 中的「throw」關鍵字：異常處理的基石

## 簡介
在 CSharp 中，「throw」關鍵字用於引發異常，幫助開發者在程式執行期間處理錯誤和異常情況。這一功能是異常處理機制的核心，允許開發者在程序中捕捉和應對潛在的錯誤。

## 文檔
### 目的
「throw」關鍵字的主要目的是在程式中引發異常（Exception），使得異常處理機制能夠捕捉並妥善處理這些異常。當發生不符合預期的情況時，開發者可以使用「throw」來中斷正常的流程並傳遞錯誤信息。

### 使用方法
語法格式如下：
```csharp
throw new ExceptionType("Error message");
```
- **ExceptionType**：可為任何從 `System.Exception` 繼承的異常類型，例如 `ArgumentNullException`、`InvalidOperationException` 等。
- **Error message**：為異常提供的描述信息，幫助調試和錯誤追蹤。

### 詳細說明
在 CSharp 中，異常是一種對象，當程序遇到錯誤情況時，這些對象會被生成並傳遞到異常處理代碼中。使用「throw」關鍵字可以創建並引發這些異常；通常與 `try-catch` 語句結合使用，以便能夠捕捉和處理異常。

```csharp
try
{
    // 可能會引發異常的代碼
    throw new ArgumentNullException("param", "參數不能為空");
}
catch (ArgumentNullException ex)
{
    Console.WriteLine(ex.Message);
}
```

## 範例
以下是「throw」的基本使用範例：

### 範例 1：引發自定義異常
```csharp
public void ValidateAge(int age)
{
    if (age < 0)
    {
        throw new ArgumentOutOfRangeException("年齡不能為負數");
    }
}
```

### 範例 2：在方法中引發異常
```csharp
public void ProcessOrder(string orderId)
{
    if (string.IsNullOrEmpty(orderId))
    {
        throw new ArgumentNullException(nameof(orderId), "訂單ID不能為空");
    }
    // 處理訂單的邏輯
}
```

## 解釋
### 常見陷阱
1. **未捕捉的異常**：如果異常未被適當捕捉，將導致應用程序崩潰。開發者應使用 `try-catch` 語句來捕捉異常。
2. **過度使用 throw**：不應該隨意引發異常，這會影響性能並降低程式可讀性。應只在真正需要的情況下使用。
3. **不清晰的錯誤信息**：引發異常時，應提供清晰且具體的錯誤信息，以方便後續的調試。

## 總結
「throw」是 CSharp 中異常處理的重要工具，允許開發者在遇到錯誤時中斷程序流程並傳遞錯誤信息，以便能夠進行適當的處理和響應。