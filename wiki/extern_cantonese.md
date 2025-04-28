<!--
Meta Description: # CSharp 中的 "extern" 關鍵字：用法與範例 ## 概要 在 CSharp 中，`extern` 關鍵字用於聲明外部方法，這些方法通常是由其他語言編寫的，如 C 或 C++。這使得 CSharp 程式能夠調用非托管代碼。 ## 文件說明 `extern` 關鍵字的主要目的是允許 CS...
Meta Keywords: extern, csharp, dll, dllimport, static
-->

# CSharp 中的 "extern" 關鍵字：用法與範例

## 概要
在 CSharp 中，`extern` 關鍵字用於聲明外部方法，這些方法通常是由其他語言編寫的，如 C 或 C++。這使得 CSharp 程式能夠調用非托管代碼。

## 文件說明
`extern` 關鍵字的主要目的是允許 CSharp 程式與外部函數進行互動。這類函數通常是透過 P/Invoke 技術從 DLL 文件中調用的。使用 `extern` 關鍵字時，必須搭配 `DllImport` 屬性，這樣 CSharp 就能識別並正確調用外部函數。

### 用法
在 CSharp 中，使用 `extern` 關鍵字的基本格式如下：

```csharp
[DllImport("library.dll")]
public static extern int FunctionName(parameters);
```

- `DllImport` 屬性指定了所需的 DLL 檔案。
- `public static extern` 標記方法為靜態外部函數。
- `FunctionName` 是你希望調用的外部函數名。

## 範例
以下是使用 `extern` 的基本範例：

```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("user32.dll")]
    public static extern int MessageBox(int hWnd, string text, string caption, int type);

    static void Main()
    {
        MessageBox(0, "Hello, World!", "Greeting", 0);
    }
}
```

在這個例子中，`MessageBox` 函數來自 Windows 的 `user32.dll`，用於顯示一個消息框。

## 解釋
使用 `extern` 時需要注意以下幾點：

1. **引入的 DLL 必須存在**：確保指定的 DLL 文件在可訪問的路徑中，否則會導致運行時錯誤。
2. **數據類型匹配**：確保 CSharp 中使用的數據類型與 DLL 中的數據類型相匹配，否則可能會導致未定義的行為。
3. **安全性考量**：調用外部函數可能會引入安全風險，特別是當這些函數來自不受信任的來源時。

## 總結
`extern` 關鍵字在 CSharp 中用於聲明外部方法，允許開發者調用來自其他語言的函數，這對於需要使用現有的 DLL 或非托管代碼的應用程式來說非常重要。