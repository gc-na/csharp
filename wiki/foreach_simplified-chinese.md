<!--
Meta Description: # C# 中的 foreach 循环：用法与示例 ## 概述 `foreach` 是 C# 中用于遍历集合（如数组、列表和其他实现了 `IEnumerable` 接口的集合）的控制结构。它使得读取集合中的每个元素变得简单而直观。 ## 文档 `foreach` 循环的主要目的是简化对集合中元素的迭代...
Meta Keywords: foreach, csharp, var, item, int
-->

# C# 中的 foreach 循环：用法与示例

## 概述
`foreach` 是 C# 中用于遍历集合（如数组、列表和其他实现了 `IEnumerable` 接口的集合）的控制结构。它使得读取集合中的每个元素变得简单而直观。

## 文档
`foreach` 循环的主要目的是简化对集合中元素的迭代。与传统的 `for` 循环不同，`foreach` 不需要手动管理索引或迭代器，降低了出错的可能性。

### 用法
`foreach` 的基本语法如下：

```csharp
foreach (var item in collection)
{
    // 对 item 的操作
}
```

- **item**: 当前循环中访问的集合元素。
- **collection**: 需要遍历的集合。

### 细节
1. `foreach` 语句会自动处理集合的边界，避免越界错误。
2. 适用于所有实现了 `IEnumerable` 接口的集合。
3. 在 `foreach` 循环中，集合不能被修改（例如，添加或删除元素），否则会抛出 `InvalidOperationException` 异常。

## 示例
以下是 `foreach` 的一些基本用法示例：

### 示例 1：遍历数组
```csharp
string[] fruits = { "苹果", "香蕉", "橙子" };
foreach (var fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

### 示例 2：遍历列表
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
foreach (var number in numbers)
{
    Console.WriteLine(number);
}
```

### 示例 3：遍历字典
```csharp
Dictionary<string, int> ages = new Dictionary<string, int>
{
    { "张三", 25 },
    { "李四", 30 }
};

foreach (var entry in ages)
{
    Console.WriteLine($"{entry.Key}: {entry.Value}");
}
```

## 解释
在使用 `foreach` 时，有几个常见的注意事项：

1. **只读访问**: `foreach` 循环中的 `item` 是只读的，不能直接修改。如果需要对集合元素进行修改，应该使用 `for` 循环。
2. **集合修改问题**: 如果在 `foreach` 循环中修改集合，可能导致运行时异常。建议在迭代前创建集合的副本或使用其他方法处理。
3. **性能**: 对于大型集合，使用 `foreach` 可能会比普通的 `for` 循环稍慢，特别是当集合不支持高效的迭代时。

## 一句话总结
`foreach` 是 C# 中用于简化集合遍历的控制结构，提供了简单直观的语法。