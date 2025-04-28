<!--
Meta Description: # C# 類別 (Class) 介紹：深入理解 C# 的物件導向程式設計 ## 摘要 在 C# 中，類別 (Class) 是一種用於定義物件的藍圖，透過類別可以封裝數據與行為，支援物件導向程式設計的核心概念。 ## 文件說明 類別是 C# 中的一個基本概念，允許開發者創建自定義數據類型，以包含屬性 ...
Meta Keywords: public, class, string, make, model
-->

# C# 類別 (Class) 介紹：深入理解 C# 的物件導向程式設計

## 摘要
在 C# 中，類別 (Class) 是一種用於定義物件的藍圖，透過類別可以封裝數據與行為，支援物件導向程式設計的核心概念。

## 文件說明
類別是 C# 中的一個基本概念，允許開發者創建自定義數據類型，以包含屬性 (Attributes) 和方法 (Methods)。類別可以被視為一個模板，用來產生物件 (Object)。每個物件都是類別的實例，並能夠擁有屬性和行為。

### 目的
類別的主要目的是將數據和方法封裝在一起，促進程式碼的重用、可讀性和維護性。

### 使用方式
在 C# 中，類別的定義通常採用以下語法：

```csharp
public class ClassName
{
    // 屬性
    public int PropertyName { get; set; }

    // 建構子
    public ClassName(int propertyName)
    {
        PropertyName = propertyName;
    }

    // 方法
    public void MethodName()
    {
        // 方法實作
    }
}
```

## 範例
以下是使用 C# 類別的基本範例：

```csharp
// 定義一個簡單的類別
public class Car
{
    public string Make { get; set; }
    public string Model { get; set; }

    public Car(string make, string model)
    {
        Make = make;
        Model = model;
    }

    public void DisplayInfo()
    {
        Console.WriteLine($"汽車品牌: {Make}, 型號: {Model}");
    }
}

// 使用類別
class Program
{
    static void Main(string[] args)
    {
        Car myCar = new Car("Toyota", "Corolla");
        myCar.DisplayInfo(); // 輸出: 汽車品牌: Toyota, 型號: Corolla
    }
}
```

## 解釋
在使用類別時，有幾個常見的陷阱和注意事項：

1. **命名衝突**：確保類別名稱具有唯一性，以避免與系統類別或其他自定義類別發生衝突。
2. **封裝性**：使用適當的存取修飾符（如 public、private）來控制類別成員的可見性，保護內部狀態。
3. **建構子**：若未定義建構子，編譯器會自動提供一個預設建構子，但如果已定義其他建構子，則需顯式定義預設建構子。

## 一句話總結
C# 類別是定義物件的藍圖，透過封裝數據和行為實現物件導向程式設計。