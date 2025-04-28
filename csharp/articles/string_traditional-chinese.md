<!--
Meta Description: # C# 字串 (String) - 使用與特性詳解 ## 概述 在 C# 中，字串 (String) 是一種用於儲存文字資料的資料型別。字串是不可變的（immutable），這意味著一旦創建後，其內容無法更改。開發者經常使用字串來處理文本，包括用於顯示、輸入和存儲資料的各種情境。 ## 文檔 字串...
Meta Keywords: string, csharp, greeting, 其內容無法更改, firstname
-->

# C# 字串 (String) - 使用與特性詳解

## 概述
在 C# 中，字串 (String) 是一種用於儲存文字資料的資料型別。字串是不可變的（immutable），這意味著一旦創建後，其內容無法更改。開發者經常使用字串來處理文本，包括用於顯示、輸入和存儲資料的各種情境。

## 文檔
字串在 C# 中是一個非常重要的資料型別，屬於 System.String 類。字串可以用雙引號來定義，並且支持多種操作，如串接、搜尋、替換等。字串支持 Unicode 字元集，這使得它能夠處理多種語言的文本。

### 目的
C# 的字串用於儲存和操作文本資料，提供了豐富的 API 來支持各種字串相關的操作，讓開發者能夠輕鬆地處理和顯示文字。

### 使用
要使用字串，只需用雙引號包圍文本。例如：
```csharp
string greeting = "你好，世界！";
```
這行程式碼會建立一個名為 `greeting` 的字串變數，並將其初始化為 "你好，世界！"。

### 主要特性：
- **不可變性**：字串一旦創建，其內容無法更改。
- **串接**：可以使用 `+` 或 `String.Concat()` 方法來串接字串。
- **插值字串**：C# 6.0 引入了插值字串語法，方便在字串中嵌入變數。

## 範例
以下是一些基本的字串使用範例：

1. 字串串接：
```csharp
string firstName = "John";
string lastName = "Doe";
string fullName = firstName + " " + lastName; // "John Doe"
```

2. 字串插值：
```csharp
string name = "Alice";
string greeting = $"你好，{name}！"; // "你好，Alice！"
```

3. 使用 String.Format 方法：
```csharp
string formatString = "今天是 {0} 月 {1} 日";
string formattedDate = String.Format(formatString, 10, 1); // "今天是 10 月 1 日"
```

## 解釋
在使用字串時，開發者需要注意以下幾點：

- **性能問題**：字串的不可變性可能導致性能問題，特別是在大量字串操作時。這時可以考慮使用 `StringBuilder` 類來提高性能。
- **空字串與 null**：空字串 (`""`) 與 `null` 是兩個不同的概念，使用時需要小心，避免 NullReferenceException。
- **文化信息**：在處理多語言字串時，需考慮文化信息對字串的影響，例如排序和比較。

## 一句話總結
C# 的字串是一種不可變的資料型別，用於儲存和操作文本資料，並提供多種便利的功能來處理字串。