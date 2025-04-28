<!--
Meta Description: # CSharp 中的隱式類型 (Implicit Types) ## 摘要 隱式類型是 C# 中的一個特性，允許開發者使用 `var` 關鍵字自動推斷變量的類型，從而使代碼更加簡潔。 ## 文檔 隱式類型在 C# 中是通過 `var` 關鍵字來實現的。當你聲明一個變量時，如果使用 `var`，編譯...
Meta Keywords: var, csharp, list, int, number
-->

# CSharp 中的隱式類型 (Implicit Types)

## 摘要
隱式類型是 C# 中的一個特性，允許開發者使用 `var` 關鍵字自動推斷變量的類型，從而使代碼更加簡潔。

## 文檔
隱式類型在 C# 中是通過 `var` 關鍵字來實現的。當你聲明一個變量時，如果使用 `var`，編譯器會根據右側的表達式自動推斷出變量的具體類型。這個特性不僅提高了代碼的可讀性，還減少了冗長的類型聲明。

### 目的
隱式類型的主要目的是簡化變量聲明，特別是在處理複雜類型（如 LINQ 查詢、集合等）時。

### 使用方法
使用隱式類型時，只需在變量前加上 `var` 關鍵字：

```csharp
var number = 10; // 整數類型
var text = "Hello, World!"; // 字符串類型
var list = new List<int> { 1, 2, 3 }; // 列表類型
```

## 示例
### 基本用法

```csharp
// 使用隱式類型來聲明變量
var score = 90; // score 的類型為 int
var name = "Alice"; // name 的類型為 string
var numbers = new List<int> { 1, 2, 3, 4, 5 }; // numbers 的類型為 List<int>

// 使用隱式類型在 LINQ 查詢中
var query = from n in numbers
            where n > 2
            select n;

// 遍歷結果
foreach (var item in query)
{
    Console.WriteLine(item); // 輸出 3, 4, 5
}
```

## 解釋
雖然隱式類型使用起來非常方便，但仍需注意以下幾點：

1. **不可重複賦值**：一旦使用 `var` 聲明變量，其類型將無法更改。例如：
   ```csharp
   var number = 10;
   number = "Hello"; // 這將導致編譯錯誤
   ```

2. **必須初始化**：使用 `var` 聲明的變量必須在聲明時進行初始化。否則，編譯器將無法推斷其類型。

3. **可讀性問題**：雖然 `var` 可以使代碼更簡潔，但過度使用可能會降低代碼的可讀性，特別是當類型不明確時。

## 一行總結
隱式類型 (`var`) 允許在 C# 中自動推斷變量的類型，從而簡化代碼的寫法。