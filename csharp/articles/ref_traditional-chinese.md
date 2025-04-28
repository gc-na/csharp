<!--
Meta Description: # C# 中的 "ref" 參考關鍵字：用法與示例 ## 摘要 在 C# 中，`ref` 關鍵字用於傳遞參數的引用，使得方法可以直接修改傳入的變數。這種特性對於需要從方法返回多個值或需要在方法內部修改變數的情況非常有用。 ## 文檔 `ref` 關鍵字允許在方法之間傳遞變數的引用，而不是將變數的值複...
Meta Keywords: ref, int, number, csharp, console
-->

# C# 中的 "ref" 參考關鍵字：用法與示例

## 摘要
在 C# 中，`ref` 關鍵字用於傳遞參數的引用，使得方法可以直接修改傳入的變數。這種特性對於需要從方法返回多個值或需要在方法內部修改變數的情況非常有用。

## 文檔
`ref` 關鍵字允許在方法之間傳遞變數的引用，而不是將變數的值複製一份。這意味著在方法內部對該變數的任何修改都會反映回原始變數。使用 `ref` 時，傳入的方法中參數的類型必須與傳遞的變數類型相符。此外，傳遞給方法的變數必須在使用 `ref` 前先被初始化。

### 目的
`ref` 的主要目的是提高性能，特別是在處理大型數據結構時，因為它避免了不必要的數據複製。它還可以用於需要從方法返回多個值的情境，因為可以直接修改參數的值。

### 用法
要使用 `ref`，需要在方法定義和方法調用時都使用 `ref` 關鍵字。下面是使用 `ref` 的基本語法範例：

```csharp
void ModifyValue(ref int number)
{
    number += 10;
}

int myNumber = 5;
ModifyValue(ref myNumber);
Console.WriteLine(myNumber); // 輸出：15
```

## 示例
以下是幾個使用 `ref` 的實際示例：

### 示例 1：基本用法
```csharp
void UpdateValue(ref int value)
{
    value = value * 2;
}

int originalValue = 4;
UpdateValue(ref originalValue);
Console.WriteLine(originalValue); // 輸出：8
```

### 示例 2：傳遞多個值
```csharp
void CalculateValues(ref int a, ref int b)
{
    a += 1;
    b += 2;
}

int x = 1;
int y = 5;
CalculateValues(ref x, ref y);
Console.WriteLine($"x: {x}, y: {y}"); // 輸出：x: 2, y: 7
```

### 示例 3：與返回值的結合
```csharp
bool TryParseInt(string input, ref int result)
{
    return int.TryParse(input, out result);
}

int number = 0;
if (TryParseInt("123", ref number))
{
    Console.WriteLine($"轉換成功：{number}"); // 輸出：轉換成功：123
}
```

## 解釋
在使用 `ref` 時需要注意以下幾點：
- **變數初始化**：在傳遞變數之前必須先初始化，否則會引發編譯錯誤。
- **保持一致性**：方法中的參數類型必須與傳遞的變數類型一致，否則會產生錯誤。
- **性能考量**：雖然 `ref` 可以提高性能，但不當使用可能導致代碼可讀性下降，應該謹慎使用。

## 一句總結
在 C# 中，`ref` 關鍵字用於以引用的方式傳遞參數，使方法能夠直接修改原始變數的值。