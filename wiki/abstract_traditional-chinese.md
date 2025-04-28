<!--
Meta Description: # C# 中的 "abstract" 關鍵字詳解 ## 簡介 在 C# 中，"abstract" 是一個關鍵字，用於定義抽象類別和抽象方法。抽象類別不能被實例化，主要目的是提供一個基礎類別，讓其他類別繼承並實現其抽象方法。 ## 文檔 ### 目的 "abstract" 關鍵字的主要目的是支持面向對...
Meta Keywords: public, abstract, circle, radius, class
-->

# C# 中的 "abstract" 關鍵字詳解

## 簡介
在 C# 中，"abstract" 是一個關鍵字，用於定義抽象類別和抽象方法。抽象類別不能被實例化，主要目的是提供一個基礎類別，讓其他類別繼承並實現其抽象方法。

## 文檔
### 目的
"abstract" 關鍵字的主要目的是支持面向對象的編程，允許開發者定義不完全的類別和方法，強制子類別實現這些方法，提供一種設計模式來確保一致性。

### 用法
- **抽象類別**：使用 `abstract` 關鍵字來定義一個類別。例如：
  ```csharp
  public abstract class Animal
  {
      public abstract void MakeSound();
  }
  ```
- **抽象方法**：在抽象類別中定義的方法不需要具體實現，子類別必須實現這些方法。例如：
  ```csharp
  public class Dog : Animal
  {
      public override void MakeSound()
      {
          Console.WriteLine("Woof!");
      }
  }
  ```

### 詳細說明
1. **不能實例化**：抽象類別無法被直接實例化。例如，`Animal animal = new Animal();` 會導致編譯錯誤。
2. **繼承**：任何從抽象類別繼承的類別都必須實現所有抽象方法，否則該類別也會成為抽象類別。
3. **多型性**：抽象類別和方法支持多型性，使得可以使用基類類型的變數來引用派生類物件。

## 範例
以下是使用 "abstract" 的基本範例：

```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Circle : Shape
{
    private double radius;

    public Circle(double radius)
    {
        this.radius = radius;
    }

    public override double Area()
    {
        return Math.PI * radius * radius;
    }
}

public class Program
{
    public static void Main()
    {
        Shape circle = new Circle(5);
        Console.WriteLine("Circle Area: " + circle.Area());
    }
}
```

## 解釋
### 常見問題
- **抽象類別和介面的區別**：抽象類別可以包含實作，而介面只能包含方法簽名。當需要提供部分實作時，使用抽象類別更合適。
- **訪問修飾符**：抽象方法可以使用不同的訪問修飾符（如 `public`, `protected`），而實現它的子類別必須符合這些修飾符的要求。

### 注意事項
- 確保在子類別中實現所有的抽象方法，否則會導致編譯錯誤。
- 抽象類別可以包含非抽象的方法和屬性，這有助於共享實作。

## 一句話總結
在 C# 中，"abstract" 關鍵字用於定義無法實例化的抽象類別和強制子類別實現的抽象方法。