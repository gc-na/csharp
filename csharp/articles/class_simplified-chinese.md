<!--
Meta Description: # C# 类（Class）详解：面向对象编程的核心 ## 概述 在C#中，类是面向对象编程的基本构建块。它定义了一组属性和方法，用于创建对象，并通过封装、继承和多态等特性支持复杂的数据结构和行为。 ## 文档 ### 目的 类是C#中一种用户自定义的数据类型，它可以包含字段、属性、方法和事件等。通过...
Meta Keywords: public, person, car, model, name
-->

# C# 类（Class）详解：面向对象编程的核心

## 概述
在C#中，类是面向对象编程的基本构建块。它定义了一组属性和方法，用于创建对象，并通过封装、继承和多态等特性支持复杂的数据结构和行为。

## 文档
### 目的
类是C#中一种用户自定义的数据类型，它可以包含字段、属性、方法和事件等。通过类，开发者可以创建具有特定功能的对象，从而实现代码的重用和组织。

### 用法
在C#中，类的定义通常包括以下几个部分：
- **字段**：存储对象的状态或数据。
- **构造函数**：用于初始化对象。
- **方法**：定义对象的行为。
- **属性**：提供对字段的访问。

以下是类的基本语法：
```csharp
public class ClassName
{
    // 字段
    private int field;

    // 构造函数
    public ClassName(int value)
    {
        field = value;
    }

    // 方法
    public void MethodName()
    {
        // 方法实现
    }

    // 属性
    public int PropertyName
    {
        get { return field; }
        set { field = value; }
    }
}
```

## 示例
### 示例 1：简单类的定义
```csharp
public class Person
{
    private string name;

    public Person(string name)
    {
        this.name = name;
    }

    public void Introduce()
    {
        Console.WriteLine($"你好，我是{name}。");
    }
}

// 使用示例
Person person = new Person("张三");
person.Introduce(); // 输出：你好，我是张三。
```

### 示例 2：使用属性
```csharp
public class Car
{
    private string model;

    public string Model
    {
        get { return model; }
        set { model = value; }
    }
}

// 使用示例
Car car = new Car();
car.Model = "特斯拉";
Console.WriteLine(car.Model); // 输出：特斯拉
```

## 解释
### 常见问题和注意事项
1. **类的访问修饰符**：C#支持多种访问修饰符（如`public`、`private`、`protected`等），要根据需求合理设置，以控制类的可见性。
2. **构造函数重载**：可以创建多个构造函数以支持不同的初始化方式，但需注意参数的区分。
3. **静态类**：如果一个类只包含静态成员，可以将其定义为静态类，无法实例化。
4. **继承**：C#支持单继承，子类可以继承父类的属性和方法，但需要注意构造函数的调用。

## 单行总结
C#中的类是面向对象编程的核心，允许开发者定义对象的属性和行为，实现代码的重用和组织。