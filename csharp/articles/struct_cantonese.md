<!--
Meta Description: # CSharp 中的 “struct”：深入了解結構體的使用及應用 ## 簡介 在 CSharp 中，`struct` 是一種值類型，用於封裝數據和行為。它提供了一種簡單的方法來創建複合數據類型，適合用於需要表示小型數據結構的場景。 ## 文檔 ### 目的 `struct` 主要用於定義一組相關...
Meta Keywords: struct, public, csharp, point, int
-->

# CSharp 中的 “struct”：深入了解結構體的使用及應用

## 簡介
在 CSharp 中，`struct` 是一種值類型，用於封裝數據和行為。它提供了一種簡單的方法來創建複合數據類型，適合用於需要表示小型數據結構的場景。

## 文檔
### 目的
`struct` 主要用於定義一組相關的數據字段和方法，並且它是一個值類型，這意味著當 `struct` 被賦值或傳遞時，會創建其副本，而不是引用。

### 使用方法
在 CSharp 中，`struct` 的定義通常如下：

```csharp
struct StructName
{
    public int Field1;
    public string Field2;

    public void Method1()
    {
        // 方法實現
    }
}
```

1. **定義結構**：使用 `struct` 關鍵字定義結構，並可以包含字段、屬性和方法。
2. **實例化結構**：可以直接使用結構名稱來創建實例。
3. **值類型**：`struct` 是值類型，意味著每次賦值都會複製數據。

### 詳細信息
- **大小**：`struct` 適合用於表示小型數據結構，通常不超過 16 字節。
- **不支持繼承**：結構不能被繼承，雖然它們可以實現介面。
- **默認構造函數**：CSharp 不允許為 `struct` 定義自訂的無參構造函數，因為每個 `struct` 在創建時都會自動初始化為其數據類型的默認值。
- **性能**：由於 `struct` 是值類型，使用時不需要額外的堆內存分配，這使得它們在性能方面比引用類型更優。

## 範例
以下是一個簡單的 `struct` 範例，顯示如何定義和使用結構：

```csharp
public struct Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Display()
    {
        Console.WriteLine($"Point coordinates: ({X}, {Y})");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Point p1 = new Point(5, 10);
        p1.Display(); // 輸出: Point coordinates: (5, 10)
    }
}
```

## 解釋
### 常見陷阱
- **不可變性**：`struct` 不是不可變的，這意味著在使用時要小心。如果不小心改變了結構的值，可能會導致難以追蹤的錯誤。
- **使用大型結構**：避免使用大型結構，因為每次複製時會消耗更多的內存並影響性能。
- **與引用類型混淆**：由於 `struct` 是值類型，理解它們與引用類型（如 `class`）的區別非常重要。這影響到數據的傳遞和管理方式。

## 總結
`struct` 是 CSharp 中一種有效的數據封裝方式，適合表示小型數據結構，並且在性能上相較於引用類型具有優勢。