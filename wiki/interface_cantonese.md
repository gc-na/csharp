<!--
Meta Description: # CSharp 接口（Interface）詳細介紹：定義與應用 ## 概述 在 CSharp 中，接口（Interface）是一種合約，定義了類別必須實現的成員（方法、屬性、事件等）。接口可以促進多型性和解耦，讓程式碼更具可維護性和可擴展性。 ## 文檔 ### 目的 接口的主要目的是提供一種方式...
Meta Keywords: csharp, public, ianimal, speak, interface
-->

# CSharp 接口（Interface）詳細介紹：定義與應用

## 概述
在 CSharp 中，接口（Interface）是一種合約，定義了類別必須實現的成員（方法、屬性、事件等）。接口可以促進多型性和解耦，讓程式碼更具可維護性和可擴展性。

## 文檔
### 目的
接口的主要目的是提供一種方式，使不同的類別可以實現相同的功能，這樣可以在不改變使用者程式碼的情況下更改底層實現。使用接口可以使程式碼更具彈性，促進模組化設計。

### 使用
在 CSharp 中，接口使用 `interface` 關鍵字來定義，並且類別必須使用 `:` 符號來實現接口。接口中的成員不能有任何的實作，只有聲明。

### 詳細說明
- **定義接口**：接口可以包含方法、屬性、事件等，但不能包含字段或實作。
- **實現接口**：類別必須實現接口中所有的成員，否則會導致編譯錯誤。
- **多重實現**：CSharp 允許一個類別同時實現多個接口，這為類別提供了更多的靈活性。

## 範例
以下是如何在 CSharp 中定義和實現接口的簡單範例：

```csharp
// 定義接口
public interface IAnimal
{
    void Speak();
}

// 實現接口
public class Dog : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Woof!");
    }
}

public class Cat : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Meow!");
    }
}

// 使用接口
public class Program
{
    public static void Main(string[] args)
    {
        IAnimal myDog = new Dog();
        myDog.Speak(); // 輸出: Woof!

        IAnimal myCat = new Cat();
        myCat.Speak(); // 輸出: Meow!
    }
}
```

## 解釋
### 常見陷阱
- **未實現所有成員**：如果類別未實現接口的所有成員，則會導致編譯錯誤。
- **接口與抽象類別的區別**：接口不能包含任何實作，而抽象類別可以。選擇使用哪一種取決於需求。
- **命名衝突**：如果不同的接口有相同的方法名稱，實現類別需要明確指定使用哪個接口的方法。

### 額外說明
- 接口可以繼承其他接口，這使得接口之間的關係更加靈活和強大。
- 在大型應用程式中，使用接口有助於實現依賴注入，從而提高測試性。

## 單行摘要
CSharp 的接口是一種合約，允許類別實現相同的功能，促進多型性和模組化設計。