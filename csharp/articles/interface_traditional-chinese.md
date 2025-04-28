<!--
Meta Description: # CSharp 接口（Interface）：基礎與應用 ## 概述 在 CSharp 中，接口（Interface）是一種特殊的類型，定義了一組方法、屬性、事件或索引器的簽名，但不提供具體的實現。接口允許不同類型之間實現多態性，促進代碼的靈活性和可維護性，是面向對象編程的重要組成部分。 ## 文檔...
Meta Keywords: public, csharp, void, robot, interface
-->

# CSharp 接口（Interface）：基礎與應用

## 概述
在 CSharp 中，接口（Interface）是一種特殊的類型，定義了一組方法、屬性、事件或索引器的簽名，但不提供具體的實現。接口允許不同類型之間實現多態性，促進代碼的靈活性和可維護性，是面向對象編程的重要組成部分。

## 文檔
### 目的
接口的主要目的在於提供一種契約，讓實現該接口的類別必須遵循這個契約，從而保證類別之間的兼容性和可擴展性。使用接口可以實現多重繼承的效果，因為一個類別可以實現多個接口。

### 使用方式
在 CSharp 中，使用 `interface` 關鍵字來定義接口。接口可以包含方法、屬性、事件和索引器，但這些成員都沒有具體的實現。任何類別或結構都可以實現這個接口，並提供具體的行為。

#### 定義接口的語法範例：
```csharp
public interface IAnimal
{
    void Speak();
    string Name { get; }
}
```

#### 實現接口的語法範例：
```csharp
public class Dog : IAnimal
{
    public string Name => "Dog";

    public void Speak()
    {
        Console.WriteLine("Woof!");
    }
}
```

## 範例
以下是如何在 CSharp 中使用接口的示例：

### 範例 1：基本接口實現
```csharp
public interface IShape
{
    double Area();
}

public class Circle : IShape
{
    private double radius;

    public Circle(double radius)
    {
        this.radius = radius;
    }

    public double Area()
    {
        return Math.PI * radius * radius;
    }
}

class Program
{
    static void Main()
    {
        IShape circle = new Circle(5);
        Console.WriteLine($"Circle Area: {circle.Area()}");
    }
}
```

### 範例 2：多重接口實現
```csharp
public interface IMovable
{
    void Move();
}

public interface IControllable
{
    void Control();
}

public class Robot : IMovable, IControllable
{
    public void Move()
    {
        Console.WriteLine("Robot is moving.");
    }

    public void Control()
    {
        Console.WriteLine("Robot is being controlled.");
    }
}

class Program
{
    static void Main()
    {
        Robot robot = new Robot();
        robot.Move();
        robot.Control();
    }
}
```

## 解釋
在使用接口時，有幾個常見的陷阱和注意事項：
- **無法實例化接口**：接口不能被直接實例化，必須通過實現該接口的類別來使用。
- **成員無具體實現**：接口中的成員不應該包含任何實現，所有的實現必須留給實現該接口的類別。
- **多重實現**：雖然 CSharp 支持一個類別實現多個接口，但同時也會增加代碼的複雜性，需謹慎使用。

## 一句話總結
CSharp 接口是一種定義行為的契約，使得不同類別能夠實現多態性和擴展性。