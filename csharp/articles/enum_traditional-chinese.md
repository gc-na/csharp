<!--
Meta Description: # C# 中的列舉 (enum) 使用指南 ## 概述 在 C# 中，列舉（enum）是一種數據類型，用於定義一組具名的整數常數。列舉提高了代碼的可讀性和可維護性，並且允許開發人員以更具語義的方式來處理數值。 ## 文檔 ### 目的 列舉的主要目的是為了將整數常數命名，使其在代碼中更具可讀性和意義...
Meta Keywords: enum, csharp, color, int, green
-->

# C# 中的列舉 (enum) 使用指南

## 概述
在 C# 中，列舉（enum）是一種數據類型，用於定義一組具名的整數常數。列舉提高了代碼的可讀性和可維護性，並且允許開發人員以更具語義的方式來處理數值。

## 文檔
### 目的
列舉的主要目的是為了將整數常數命名，使其在代碼中更具可讀性和意義。使用列舉可以避免硬編碼數字，從而減少錯誤並提升維護性。

### 使用方法
在 C# 中，列舉使用 `enum` 關鍵字來定義。以下是列舉的基本語法：

```csharp
enum EnumName
{
    Value1,
    Value2,
    Value3
}
```

列舉的每個成員都會自動獲得一個從零開始的整數值，除非顯式指定不同的值。

### 詳細說明
- 列舉成員的預設整數值從 0 開始，依次遞增。
- 可以為列舉成員指定特定的整數值，例如：

```csharp
enum Days
{
    Sunday = 1,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}
```

在這個範例中，`Sunday` 的值為 1，`Monday` 的值為 2，以此類推。

- 列舉也可以指定基礎類型，預設為 `int`，例如：

```csharp
enum StatusCode : byte
{
    OK = 1,
    NotFound = 404,
    InternalServerError = 500
}
```

## 範例
以下是如何使用列舉的基本範例：

```csharp
enum Color
{
    Red,
    Green,
    Blue
}

class Program
{
    static void Main(string[] args)
    {
        Color myColor = Color.Green;
        Console.WriteLine(myColor); // 輸出 "Green"
        Console.WriteLine((int)myColor); // 輸出 "1"
    }
}
```

## 解釋
### 常見陷阱與注意事項
- **隱式轉型**：列舉類型可以隱式轉型為整數，但反向轉型需要顯式指定，否則會導致編譯錯誤。
  
```csharp
int num = 1;
Color color = (Color)num; // 正確轉型
```

- **重複值**：列舉成員可以共享相同的整數值，但這可能會導致不明確的行為。

```csharp
enum Test
{
    A = 1,
    B = 1  // 這會導致 A 和 B 具有相同的值
}
```

- **無法添加成員**：一旦列舉定義完成，就不能再添加成員。這需要在設計階段仔細考慮。

## 總結
在 C# 中，列舉（enum）是一種強大且靈活的數據類型，能夠提升代碼的可讀性和可維護性，幫助開發者以更具語義的方式處理整數常數。