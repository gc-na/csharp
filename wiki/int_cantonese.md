<!--
Meta Description: # CSharp 的整數類型「int」：概述與使用指導 ## 簡介 在 CSharp 編程語言中，「int」是一個基本數據類型，用於表示整數。它是「System.Int32」的別名，佔用 4 個字節的內存，並可表示的範圍為 -2,147,483,648 到 2,147,483,647。 ## 文檔 ...
Meta Keywords: int, csharp, mynumber, age, 147
-->

# CSharp 的整數類型「int」：概述與使用指導

## 簡介
在 CSharp 編程語言中，「int」是一個基本數據類型，用於表示整數。它是「System.Int32」的別名，佔用 4 個字節的內存，並可表示的範圍為 -2,147,483,648 到 2,147,483,647。

## 文檔
### 目的
「int」數據類型的主要目的是提供一種簡潔的方式來處理整數數據。由於其固定的大小，開發者可以預測內存使用情況，從而提高程序的性能和可靠性。

### 用法
在 CSharp 中，您可以通過以下方式聲明一個「int」變量：
```csharp
int myNumber = 10;
```
您還可以進行各種數學運算，例如加法、減法、乘法和除法：
```csharp
int sum = myNumber + 20;
int product = myNumber * 5;
```

### 詳細信息
- 「int」是值類型，這意味著當您將其賦值給另一個變量時，會複製該值而不是引用。
- 在進行運算時，超出「int」範圍的計算會導致溢出，未經處理的溢出將會環繞到最小值。
- CSharp 7.3 及更高版本引入了「int」的字面量表示法，例如：
```csharp
int hexValue = 0xA; // 十六進制表示
int binaryValue = 0b1010; // 二進制表示
```

## 示例
以下是一些「int」使用的基本示例：

```csharp
// 聲明和初始化整數變量
int age = 25;

// 數學運算
int height = 180;
int totalHeight = age + height;

// 輸出結果
Console.WriteLine("年齡：" + age);
Console.WriteLine("總高度：" + totalHeight);
```

## 解釋
在使用「int」時，開發者應注意以下幾點：
- 溢出：在進行數學運算時，必須小心溢出情況，特別是在循環或大量數據處理時。可以通過使用 `checked` 關鍵字來檢查溢出：
```csharp
int result = checked(myNumber + int.MaxValue);
```
- 性能：雖然「int」比其他數據類型（如「long」）更快，但如果計算的數字超出「int」範圍，則需要考慮使用「long」以避免溢出。

## 一句總結
「int」是 CSharp 中一種常用的整數數據類型，適用於處理範圍內的整數運算。