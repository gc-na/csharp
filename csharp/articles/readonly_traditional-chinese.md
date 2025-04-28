<!--
Meta Description: # C# 中的 readonly 關鍵字：使用與注意事項 ## 簡介 `readonly` 是 C# 中的一個關鍵字，用於定義只讀字段。這些字段一旦被賦值後，便無法再被修改，提供了對數據不可變性的保護。 ## 文檔 `readonly` 關鍵字的主要目的是保護字段的值不被意外更改。當一個字段被標記為...
Meta Keywords: readonly, example, readonlynumber, public, csharp
-->

# C# 中的 readonly 關鍵字：使用與注意事項

## 簡介
`readonly` 是 C# 中的一個關鍵字，用於定義只讀字段。這些字段一旦被賦值後，便無法再被修改，提供了對數據不可變性的保護。

## 文檔
`readonly` 關鍵字的主要目的是保護字段的值不被意外更改。當一個字段被標記為 `readonly` 時，它可以在聲明時或在構造函數中被初始化，但在對象的整個生命週期中都不能被修改。這對於需要保證數據完整性和穩定性的情況非常有用。

### 目的
- 增強數據完整性。
- 限制字段的可變性，確保其在對象創建後不會改變。

### 使用
在 C# 中，`readonly` 可以用於類的字段聲明。以下是其基本語法：

```csharp
readonly <data_type> <field_name>;
```

在類的構造函數中，您可以賦值給 `readonly` 字段，但在構造函數之外則無法進行賦值。

## 範例
以下是 `readonly` 的基本使用範例：

```csharp
public class Example
{
    public readonly int ReadOnlyNumber;

    public Example(int number)
    {
        ReadOnlyNumber = number; // 在構造函數中賦值
    }
}

class Program
{
    static void Main(string[] args)
    {
        Example ex = new Example(10);
        Console.WriteLine(ex.ReadOnlyNumber); // 輸出: 10
        // ex.ReadOnlyNumber = 20; // 這行會導致編譯錯誤
    }
}
```

在這個範例中，`ReadOnlyNumber` 字段只能在 `Example` 的構造函數中被賦值，之後將無法改變。

## 解釋
使用 `readonly` 時需要注意以下幾點：
- `readonly` 字段可以在靜態構造函數中初始化，但在其他地方不能被賦值。
- 如果 `readonly` 字段是一個引用類型的對象，則該對象的內容仍然可以被修改，但引用本身不能被更改。
- 在多執行緒環境中，使用 `readonly` 可以幫助避免數據競爭，因為字段在初始化後不會改變。

## 一句總結
`readonly` 關鍵字在 C# 中用於定義不可變的字段，確保數據在對象生命週期內保持一致性。