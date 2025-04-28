<!--
Meta Description: # CSharp中的“override”关键字详解 ## 概述 “override”是CSharp编程语言中的一个关键字，用于重写基类中的虚方法或抽象方法。这一特性使得派生类可以提供自定义实现，从而达到多态性的效果。 ## 文档 “override”关键字的主要目的是允许派生类重新定义其基类中的方法...
Meta Keywords: public, override, shape, radius, class
-->

# CSharp中的“override”关键字详解

## 概述
“override”是CSharp编程语言中的一个关键字，用于重写基类中的虚方法或抽象方法。这一特性使得派生类可以提供自定义实现，从而达到多态性的效果。

## 文档
“override”关键字的主要目的是允许派生类重新定义其基类中的方法。被重写的方法必须在基类中标记为“virtual”或“abstract”。使用“override”时，派生类的方法签名必须与基类中的相应方法完全匹配。

**用法**：
1. 在基类中定义一个虚方法或抽象方法。
2. 在派生类中使用“override”关键字重写该方法。

**示例**：
```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}
```
在上面的示例中，`Dog`类重写了`Animal`类中的`Speak`方法，当调用`Dog`类的`Speak`时，会输出“Dog barks”。

## 示例
以下是一个简单的示例，展示了如何使用“override”关键字：

```csharp
public class Shape
{
    public virtual double Area()
    {
        return 0;
    }
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
    public static void Main(string[] args)
    {
        Shape shape = new Circle(5);
        Console.WriteLine($"Area of Circle: {shape.Area()}");
    }
}
```
在这个示例中，`Circle`类重写了`Shape`类中的`Area`方法，计算圆的面积。

## 解释
使用“override”时需要注意以下几点：
- 被重写的方法必须在基类中声明为“virtual”或“abstract”。
- 方法的返回类型和参数列表必须与基类中的方法完全一致。
- 如果试图重写非虚方法，编译器将会报错。
- 使用“override”可以让你在派生类中实现不同的行为，这是实现多态的重要手段。

### 常见陷阱
- 确保方法签名匹配：派生类中的方法必须与基类中的虚方法完全匹配，任何细微的差别（如参数类型或数量）都会导致编译错误。
- 对于方法的访问修饰符，重写的方法可以是基类方法的访问修饰符相同或更开放（例如，基类为`protected`，则派生类可以是`protected`或`public`）。

## 一句话总结
“override”关键字在CSharp中用于重写基类的虚方法或抽象方法，以实现多态性。