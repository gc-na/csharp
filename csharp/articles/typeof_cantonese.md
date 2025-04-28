<!--
Meta Description: # CSharp 中的 `typeof` 關鍵字：用法與示例 ## 簡介 `typeof` 是 CSharp 中的一個運算符，用於獲取指定類型的 System.Type 對象。這個關鍵字在反射和類型檢查中非常有用，特別是在需要動態獲取類型信息的場合。 ## 文檔 ### 目的 `typeof` 用於...
Meta Keywords: typeof, csharp, type, system, class
-->

# CSharp 中的 `typeof` 關鍵字：用法與示例

## 簡介
`typeof` 是 CSharp 中的一個運算符，用於獲取指定類型的 System.Type 對象。這個關鍵字在反射和類型檢查中非常有用，特別是在需要動態獲取類型信息的場合。

## 文檔
### 目的
`typeof` 用於在編譯時獲取類型信息，這使得開發者能夠在運行時處理類型相關的操作，如反射、類型匹配、以及創建類型的實例等。

### 用法
`typeof` 的基本語法為：
```csharp
Type type = typeof(YourClassName);
```
這樣可以獲得 `YourClassName` 類的 Type 對象。

### 詳細說明
- `typeof` 運算符只能用於類型名稱，不能用於變量或表達式。
- 這個運算符在編譯時解析類型，這意味著它不會在運行時計算，從而提高性能。
- `typeof` 可用於所有 CSharp 支持的類型，包括自定義類型、結構、接口等。

## 示例
### 基本用法
```csharp
using System;

class Program
{
    static void Main()
    {
        Type intType = typeof(int);
        Console.WriteLine(intType); // 輸出: System.Int32

        Type stringType = typeof(string);
        Console.WriteLine(stringType); // 輸出: System.String
    }
}
```

### 自定義類型
```csharp
class MyClass
{
}

class Program
{
    static void Main()
    {
        Type myClassType = typeof(MyClass);
        Console.WriteLine(myClassType); // 輸出: Namespace.MyClass
    }
}
```

## 解釋
- 常見的陷阱：使用 `typeof` 時，開發者可能會嘗試用變量或對象來獲取類型，但這會導致編譯錯誤。`typeof` 僅接受類型名稱。
- 注意事項：當使用 `typeof` 獲取泛型類型時，需指定具體的類型參數。例如，`typeof(List<int>)` 和 `typeof(List<string>)` 將返回不同的類型。
  
## 總結
`typeof` 運算符是一個強大的工具，能夠在 CSharp 中獲取類型信息，並在反射和類型檢查中發揮重要作用。