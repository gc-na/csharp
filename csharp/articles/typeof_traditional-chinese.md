<!--
Meta Description: # C# 中的 `typeof` 關鍵字：用於類型獲取的完整指南 ## 概述 `typeof` 是 C# 中的一個關鍵字，用於獲取指定類型的 `System.Type` 對象。這個功能在反射、類型檢查和其他與類型相關的操作中非常有用。 ## 文檔 ### 目的 `typeof` 讓開發者能夠在編譯時...
Meta Keywords: typeof, type, system, csharp, int
-->

# C# 中的 `typeof` 關鍵字：用於類型獲取的完整指南

## 概述
`typeof` 是 C# 中的一個關鍵字，用於獲取指定類型的 `System.Type` 對象。這個功能在反射、類型檢查和其他與類型相關的操作中非常有用。

## 文檔
### 目的
`typeof` 讓開發者能夠在編譯時期獲取類型資訊，而不需要實例化對象。這對於反射、類型安全和泛型編程等場合尤其重要。

### 用法
`typeof` 的基本語法如下：

```csharp
Type type = typeof(YourType);
```

其中 `YourType` 可以是任何有效的類型，包括自定義類型、內建類型或介面。此語句將返回該類型的 `Type` 對象，通過該對象可以訪問類型的詳細資訊，如方法、屬性和事件等。

### 詳細說明
- **靜態類型**： `typeof` 在編譯時確定類型，因此它不會影響性能。
- **泛型**：可用於獲取泛型類型的具體類型信息。
- **組合**：可以與其他反射功能結合使用，以獲取更詳細的類型信息。

## 範例
以下是一些使用 `typeof` 的基本範例：

### 獲取基本類型
```csharp
Type intType = typeof(int);
Console.WriteLine(intType); // 輸出：System.Int32
```

### 獲取自定義類型
```csharp
class Person { }

Type personType = typeof(Person);
Console.WriteLine(personType); // 輸出：Namespace.Person
```

### 獲取泛型類型
```csharp
List<int> numbers = new List<int>();
Type listType = typeof(List<int>);
Console.WriteLine(listType); // 輸出：System.Collections.Generic.List`1[System.Int32]
```

## 解釋
- **常見陷阱**：`typeof` 只能用於已知類型，無法用於變量。例如，不能寫 `typeof(variable)`，這會導致編譯錯誤。
- **與 `GetType` 的區別**：`typeof` 用於獲取靜態類型信息，而 `GetType()` 用於獲取運行時的實例類型信息。
- **泛型的使用**：當使用 `typeof` 與泛型結合時，必須指定完整的類型參數，否則會引發編譯錯誤。

## 一句總結
`typeof` 是 C# 中用於在編譯時獲取類型信息的關鍵字，對於反射和類型安全編程至關重要。