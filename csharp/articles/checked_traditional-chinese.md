<!--
Meta Description: # C# 的 `checked` 關鍵字：用於整數溢出檢查 ## 簡介 在 C# 中，`checked` 關鍵字用於確保在進行整數運算時進行溢出檢查。當數值運算結果超出該類型所能表示的範圍時，`checked` 块會引發 `OverflowException`，從而幫助開發者捕捉潛在的錯誤。 ## ...
Meta Keywords: checked, int, overflowexception, csharp, result
-->

# C# 的 `checked` 關鍵字：用於整數溢出檢查

## 簡介
在 C# 中，`checked` 關鍵字用於確保在進行整數運算時進行溢出檢查。當數值運算結果超出該類型所能表示的範圍時，`checked` 块會引發 `OverflowException`，從而幫助開發者捕捉潛在的錯誤。

## 文件說明
`checked` 關鍵字主要用於數值運算，如加法、減法和乘法。當使用 `checked` 包裝運算時，C# 確保運算的結果不會溢出。如果溢出發生，則會引發異常，這對於需要精確計算的應用程序來說非常重要。

### 用法
`checked` 可以用在語句或表達式中。以下是其基本語法：

```csharp
checked
{
    // 進行數值運算
}
```

或者用於單個表達式：

```csharp
int result = checked(a + b);
```

這種方式可提高代碼的可讀性，並明確指出哪些運算需要溢出檢查。

## 示例
以下是幾個使用 `checked` 的基本範例：

### 範例 1：基本運算
```csharp
int a = int.MaxValue;
int b = 1;

try
{
    int result = checked(a + b); // 將引發 OverflowException
}
catch (OverflowException ex)
{
    Console.WriteLine("溢出發生: " + ex.Message);
}
```

### 範例 2：多行運算
```csharp
int x = 2000000000;
int y = 2000000000;

try
{
    checked
    {
        int sum = x + y; // 將引發 OverflowException
    }
}
catch (OverflowException ex)
{
    Console.WriteLine("溢出發生: " + ex.Message);
}
```

### 範例 3：使用在方法中
```csharp
public int Add(int a, int b)
{
    return checked(a + b); // 溢出檢查
}
```

## 解釋
使用 `checked` 時，有幾個常見的注意事項：

1. **性能影響**：使用 `checked` 會在運算中加入額外的檢查，這可能會影響性能，因此在性能敏感的區域應謹慎使用。
   
2. **全局設定**：可以在項目層級設定全局溢出檢查。這可以通過編譯器選項進行配置，但會影響整個應用程序的行為。

3. **與 `unchecked` 的區別**：`unchecked` 關鍵字則明確指出在進行運算時不進行溢出檢查，這在某些情況下可能是需要的，以提高性能或避免不必要的異常。

## 一句總結
C# 中的 `checked` 關鍵字用於確保整數運算的溢出檢查，從而提高代碼的安全性和可靠性。