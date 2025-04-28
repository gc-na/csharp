<!--
Meta Description: # C# 的 foreach 迴圈：高效遍歷集合的利器 ## 簡介 `foreach` 是 C# 中一個用於遍歷集合（如陣列、列表和字典）的迴圈結構。它提供了一種簡單、清晰的方式來訪問集合中的每一個元素，免去了使用索引的繁瑣。 ## 文檔 ### 目的 `foreach` 迴圈的主要目的是讓開發者輕...
Meta Keywords: foreach, var, item, csharp, list
-->

# C# 的 foreach 迴圈：高效遍歷集合的利器

## 簡介
`foreach` 是 C# 中一個用於遍歷集合（如陣列、列表和字典）的迴圈結構。它提供了一種簡單、清晰的方式來訪問集合中的每一個元素，免去了使用索引的繁瑣。

## 文檔
### 目的
`foreach` 迴圈的主要目的是讓開發者輕鬆地遍歷集合，而不需要擔心集合的大小或元素的索引。這使得代碼更加可讀，並減少了出錯的可能性。

### 使用方法
`foreach` 迴圈的基本語法如下：

```csharp
foreach (var item in collection)
{
    // 對每個 item 執行操作
}
```

- `var item`：代表當前迭代的集合元素，類型可以自動推斷。
- `collection`：需要遍歷的集合，必須實現 `IEnumerable` 接口。

### 詳細說明
`foreach` 迴圈自動處理迭代器的生成，開發者不需要手動管理迭代過程。這不僅提高了代碼的簡潔性，還降低了出錯的風險。在 C# 中，`foreach` 迴圈可以用於以下類型的集合：
- 陣列
- List<T>
- Dictionary<TKey, TValue>
- HashSet<T>

## 範例
以下是使用 `foreach` 迴圈遍歷陣列和列表的基本範例：

### 陣列範例
```csharp
string[] fruits = { "蘋果", "香蕉", "橘子" };

foreach (var fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

### 列表範例
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };

foreach (var number in numbers)
{
    Console.WriteLine(number * number);
}
```

## 解釋
在使用 `foreach` 時，有幾個常見的注意事項：
- **不可修改集合**：在 `foreach` 迴圈中，不能修改正在遍歷的集合（例如添加或刪除元素），這會引發 `InvalidOperationException`。
- **性能考量**：對於大型集合，使用 `foreach` 可能會比使用索引更慢，因為每次迭代都需要調用迭代器。如果性能是主要考量，考慮使用 `for` 迴圈。
- **變量作用域**：`foreach` 中的 `item` 變量在迴圈外不可用，需注意變量的作用域。

## 一句總結
`foreach` 迴圈是 C# 中一種強大且易於使用的工具，專為簡化集合遍歷而設計。