<!--
Meta Description: # C# 的結構 (struct) - 資料結構的基石 ## 概要 在 C# 中，結構（struct）是一種值類型，用於封裝資料並定義新類型。結構允許開發者創建自定義資料類型，並提供更好的記憶體效能與簡化的資料管理。 ## 文件說明 ### 目的 結構用於定義小型的資料封裝，特別適合於簡單的資料組合...
Meta Keywords: public, int, struct, rectangle, width
-->

# C# 的結構 (struct) - 資料結構的基石

## 概要
在 C# 中，結構（struct）是一種值類型，用於封裝資料並定義新類型。結構允許開發者創建自定義資料類型，並提供更好的記憶體效能與簡化的資料管理。

## 文件說明
### 目的
結構用於定義小型的資料封裝，特別適合於簡單的資料組合，且具有較輕量的特性。結構的主要用途是當需要快速且有效率地管理資料時，尤其在開發性能敏感的應用程式中，結構能夠有效減少記憶體的使用。

### 使用方式
在 C# 中，結構是使用 `struct` 關鍵字來定義的。結構可以包含成員變數、屬性、方法、建構函數、和事件。以下是一個基本的結構定義範例：

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
```

### 詳細說明
- **值類型**：結構屬於值類型，這意味著當結構被賦值給另一個變數時，會創建一個該結構的副本。
- **記憶體佔用**：因為結構是值類型，所以其記憶體被佈置在棧上，這使得結構在存取速度上通常比參考類型（class）快。
- **不可繼承**：結構不能被繼承，這意味著無法從結構派生出新的結構，但可以實現介面。
- **預設構造函數**：結構有一個隱式的預設構造函數，會將所有成員初始化為其類型的預設值。

## 範例
使用結構的基本例子：

```csharp
public struct Rectangle
{
    public int Width;
    public int Height;

    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;
    }

    public int Area()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main()
    {
        Rectangle rect = new Rectangle(10, 5);
        Console.WriteLine($"Area of rectangle: {rect.Area()}");
    }
}
```

## 解釋
- **常見陷阱**：當結構作為參數傳遞時，請注意它是以值傳遞的方式進行，這可能導致意外的行為。如果希望修改結構的內容，應使用 `ref` 或 `out` 關鍵字進行傳遞。
- **記憶體管理**：由於結構在棧上配置，過大的結構可能導致棧溢出，因此應謹慎選擇結構的大小。
- **使用場景**：結構最適合用於封裝小型資料，像是二維坐標、顏色值等，而不適合用於大型資料或需要繼承的情況。

## 總結
C# 的結構（struct）是一種高效的值類型，用於封裝簡單的資料結構，並提供了良好的性能與記憶體管理。