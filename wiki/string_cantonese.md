<!--
Meta Description: # CSharp 字串資料型別 (String) 詳細介紹 ## 簡介 在 CSharp 中，字串（String）是用來表示文字的資料型別，支援各種文字操作與處理功能，廣泛應用於程式設計中。 ## 文件 字串是一個不可變的資料型別，這意味著一旦創建，字串的內容就無法更改。字串在 CSharp 中是用...
Meta Keywords: string, csharp, greeting, length, substring
-->

# CSharp 字串資料型別 (String) 詳細介紹

## 簡介
在 CSharp 中，字串（String）是用來表示文字的資料型別，支援各種文字操作與處理功能，廣泛應用於程式設計中。

## 文件
字串是一個不可變的資料型別，這意味著一旦創建，字串的內容就無法更改。字串在 CSharp 中是用雙引號包圍的字符序列。這個資料型別的主要用途是儲存文本資料，如用戶輸入、文件內容或任何需要處理的文字。

### 主要功能
1. **創建字串**：可透過直接賦值或使用字串建構子創建。
2. **字串拼接**：使用 `+` 運算子或 `String.Concat` 方法來合併字串。
3. **字串格式化**：使用 `String.Format` 或插值字串來格式化字串內容。
4. **查詢與操作**：提供多種方法如 `Length`、`Substring`、`IndexOf`、`Replace` 等，進行字串查詢與操作。
5. **字串比較**：使用 `Equals` 方法或 `Compare` 方法來比較字串的內容。

## 示例
以下是一些基本用法的示例：

```csharp
// 創建字串
string greeting = "你好，世界！";

// 字串拼接
string name = "小明";
string welcomeMessage = greeting + " " + name;

// 字串格式化
int age = 20;
string formattedString = string.Format("{0} 年齡是 {1} 歲", name, age);

// 查詢字串長度
int length = greeting.Length;

// 取得子字串
string subString = greeting.Substring(0, 5); // 取得 "你好，"
```

## 解釋
在使用字串時，有一些常見的陷阱需要注意：
- **不可變性**：字串一旦被創建，不能被修改。任何操作都會返回一個新的字串，這可能導致性能問題，特別是在大量字串操作時。為了提高性能，可以考慮使用 `StringBuilder`。
- **字串比較**：使用 `==` 來比較字串時，會比較引用而非內容，建議使用 `String.Equals` 或 `String.Compare` 進行內容比較。
- **文化影響**：某些字串操作可能會受到文化的影響，例如在進行字串排序和比較時，應考慮使用 `StringComparison` 參數來指定文化。

## 總結
字串（String）在 CSharp 中是一個不可變的資料型別，用於處理和操作文本資料，具有多種功能與應用。