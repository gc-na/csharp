<!--
Meta Description: # C#中的“protected”关键字详解 ## 概述 在C#编程语言中，“protected”是一个访问修饰符，用于控制类成员的可访问性。它主要用于实现封装，支持继承的类之间的访问权限。 ## 文档 “protected”关键字用于定义类的字段、属性、方法和事件的可见性。被标记为“protect...
Meta Keywords: protected, void, value, public, class
-->

# C#中的“protected”关键字详解

## 概述 
在C#编程语言中，“protected”是一个访问修饰符，用于控制类成员的可访问性。它主要用于实现封装，支持继承的类之间的访问权限。

## 文档 
“protected”关键字用于定义类的字段、属性、方法和事件的可见性。被标记为“protected”的成员可以在其自身类中以及在任何从该类派生的子类中访问。这种访问控制有助于保护类的内部实现细节，同时允许子类对这些成员进行扩展和修改。

### 用法 
使用“protected”关键字时，通常在成员声明前加上该修饰符，例如：

```csharp
protected int myProtectedField;
protected void MyProtectedMethod() { }
```

在以上示例中，`myProtectedField`和`MyProtectedMethod`只能在定义它们的类及其派生类中访问。

### 详细信息 
- **可访问性**：被标记为“protected”的成员不可以在类的外部直接访问，甚至无法在同一命名空间的非派生类中访问。
- **继承使用**：在派生类中，可以直接访问父类的“protected”成员，这使得子类可以重用和扩展父类的功能。
- **与其他修饰符的结合**：可以与其他访问修饰符（如“internal”或“private”）结合使用，形成“protected internal”，使得成员在同一程序集中的任何类或任何派生类中均可访问。

## 示例 
以下示例展示了“protected”关键字的基本用法：

```csharp
public class BaseClass
{
    protected int protectedValue = 10;

    protected void DisplayValue()
    {
        Console.WriteLine($"Protected Value: {protectedValue}");
    }
}

public class DerivedClass : BaseClass
{
    public void Show()
    {
        // 可以访问基类的protected成员
        Console.WriteLine($"Accessing Protected Value: {protectedValue}");
        DisplayValue();
    }
}

class Program
{
    static void Main(string[] args)
    {
        DerivedClass derived = new DerivedClass();
        derived.Show(); // 输出：Accessing Protected Value: 10 \n Protected Value: 10
    }
}
```

## 说明 
- **常见陷阱**：初学者常常误解“protected”成员的访问范围，认为它可以在同一命名空间中的所有类中访问。实际上，它仅限于派生类。
- **组合使用**：在使用“protected”修饰符时，要注意其与其他修饰符的组合，确保理解其影响。
- **设计考虑**：在设计类时，应合理使用“protected”以确保类的良好封装性和可扩展性，避免过度暴露内部实现。

## 一句话总结 
“protected”关键字用于在C#中定义类成员的访问权限，允许子类访问父类的相关成员。