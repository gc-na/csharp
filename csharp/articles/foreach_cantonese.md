<!--
Meta Description: # CSharp 中的 foreach：用於遍歷集合的強大工具 ## 概述 `foreach` 是 CSharp 中的一個控制結構，專門用於遍歷集合（如陣列、列表和字典）中的每個元素。這個關鍵字提供了一種簡單且直觀的方式來訪問集合的項目，無需使用傳統的索引或計數器。 ## 文件說明 ### 目的 `...
Meta Keywords: foreach, csharp, var, string, item
-->

# CSharp 中的 foreach：用於遍歷集合的強大工具

## 概述
`foreach` 是 CSharp 中的一個控制結構，專門用於遍歷集合（如陣列、列表和字典）中的每個元素。這個關鍵字提供了一種簡單且直觀的方式來訪問集合的項目，無需使用傳統的索引或計數器。

## 文件說明
### 目的
`foreach` 旨在簡化集合元素的迭代過程。開發人員可以用它輕鬆地讀取集合中的每個項目，而不必擔心邊界檢查或索引越界的問題。

### 用法
`foreach` 的基本語法如下：
```csharp
foreach (var item in collection)
{
    // 操作 item
}
```
- `item` 是在每次迭代中代表當前集合項目的變量。
- `collection` 是要遍歷的集合，可以是陣列、列表或其他實現了 `IEnumerable` 接口的對象。

### 詳細說明
`foreach` 循環會自動處理集合的邊界，並且在迭代過程中不會修改集合的結構，這樣可以避免許多常見錯誤。這種語法不僅提高了代碼的可讀性，還減少了出錯的機會。

## 範例
以下是幾個基本的 `foreach` 使用範例：

### 範例 1：遍歷整數陣列
```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
foreach (var number in numbers)
{
    Console.WriteLine(number);
}
```

### 範例 2：遍歷字典
```csharp
Dictionary<string, int> ages = new Dictionary<string, int>()
{
    { "Alice", 30 },
    { "Bob", 25 }
};

foreach (var kvp in ages)
{
    Console.WriteLine($"{kvp.Key} 的年齡是 {kvp.Value}");
}
```

### 範例 3：遍歷列表
```csharp
List<string> fruits = new List<string> { "蘋果", "香蕉", "橙" };
foreach (var fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

## 解釋
### 常見陷阱
- **集合修改**：在使用 `foreach` 遍歷集合的同時修改集合（如添加或刪除元素）會導致 `InvalidOperationException`。這是因為 `foreach` 依賴於集合的穩定狀態。
- **非泛型集合**：對於非泛型集合，`foreach` 需要使用 `object` 類型來進行遍歷，這可能會導致性能問題以及需要進行類型轉換。

### 附加備註
- `foreach` 無法用於字符串，因為字符串不是一個集合。
- 在使用 `foreach` 時，請確保集合的類型實現了 `IEnumerable` 接口。

## 一行總結
`foreach` 是 CSharp 中用於簡潔地遍歷集合元素的控制結構，有助於提高代碼的可讀性和安全性。