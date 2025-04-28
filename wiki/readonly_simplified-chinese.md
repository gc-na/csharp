<!--
Meta Description: # C# 中的 readonly 关键字详解 ## 概述 在 C# 编程中，`readonly` 关键字用于修饰字段，使其在对象的生命周期内只能被赋值一次。这一特性确保了数据的不可变性，增强了代码的安全性和可读性。 ## 文档 `readonly` 关键字主要用于类的字段。被修饰的字段可以在构造函数...
Meta Keywords: readonly, public, person, myclass, name
-->

# C# 中的 readonly 关键字详解

## 概述
在 C# 编程中，`readonly` 关键字用于修饰字段，使其在对象的生命周期内只能被赋值一次。这一特性确保了数据的不可变性，增强了代码的安全性和可读性。

## 文档
`readonly` 关键字主要用于类的字段。被修饰的字段可以在构造函数中被赋值，但在对象创建后，字段的值不能被修改。这使得 `readonly` 字段适合用于存储常量值或在对象创建后不希望更改的数据。

### 目的
- 确保字段在初始化后不能被更改。
- 提高代码的可维护性和安全性。
- 提供一种简单的方式来创建不可变对象。

### 用法
在定义字段时，可以使用 `readonly` 关键字。以下是基本语法：

```csharp
readonly 类型 字段名;
```

在类的构造函数中，可以对 `readonly` 字段进行赋值。例如：

```csharp
public class MyClass
{
    public readonly int MyReadonlyField;

    public MyClass(int value)
    {
        MyReadonlyField = value; // 允许在构造函数中赋值
    }
}
```

## 示例
下面是使用 `readonly` 关键字的基本示例：

```csharp
public class Person
{
    public readonly string Name;

    public Person(string name)
    {
        Name = name; // 允许在构造函数中赋值
    }
}

class Program
{
    static void Main()
    {
        Person person = new Person("Alice");
        Console.WriteLine(person.Name); // 输出: Alice
        
        // person.Name = "Bob"; // 编译错误: 无法修改只读字段
    }
}
```

## 解释
### 常见问题
- **只能在构造函数中赋值**：`readonly` 字段只能在构造函数中进行赋值，尝试在其他方法中赋值将导致编译错误。
- **与 const 的区别**：`const` 字段在编译时就已确定值，而 `readonly` 字段的值可以在运行时通过构造函数赋值。

### 附加说明
- `readonly` 关键字适用于引用类型字段。当引用类型的字段被标记为 `readonly` 时，虽然引用本身不能改变，但引用对象的内容仍然可以被修改。例如：

```csharp
public class MyClass
{
    public readonly List<int> Numbers;

    public MyClass()
    {
        Numbers = new List<int>(); // 允许在构造函数中赋值
    }
}

// 使用示例
MyClass obj = new MyClass();
obj.Numbers.Add(1); // 这是合法的，因为我们没有改变 Numbers 的引用
```

## 一句总结
`readonly` 关键字在 C# 中用于修饰字段，确保字段在对象创建后不可修改，从而提升代码的安全性与可维护性。