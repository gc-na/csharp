<!--
Meta Description: # C# 中的 "new" 关键字详解 ## 概述 在 C# 中，"new" 关键字用于创建对象实例以及隐藏基类成员。 ## 文档 "new" 关键字的主要目的是用于实例化类或结构体，分配内存并调用相应的构造函数。此外，"new" 还可以用于隐藏基类中的成员，以便在派生类中定义同名的成员。 ### ...
Meta Keywords: new, public, dog, person, class
-->

# C# 中的 "new" 关键字详解

## 概述
在 C# 中，"new" 关键字用于创建对象实例以及隐藏基类成员。

## 文档
"new" 关键字的主要目的是用于实例化类或结构体，分配内存并调用相应的构造函数。此外，"new" 还可以用于隐藏基类中的成员，以便在派生类中定义同名的成员。

### 用法
1. **实例化对象**:
   ```csharp
   MyClass obj = new MyClass();
   ```
   这里，`MyClass` 是一个类，`obj` 是该类的一个实例。使用 "new" 关键字后，内存将被分配以存储该对象，并调用 `MyClass` 的构造函数。

2. **隐藏成员**:
   ```csharp
   class BaseClass
   {
       public void Display() 
       {
           Console.WriteLine("BaseClass Display");
       }
   }

   class DerivedClass : BaseClass
   {
       new public void Display() 
       {
           Console.WriteLine("DerivedClass Display");
       }
   }
   ```
   在此示例中，`DerivedClass` 中的 `Display` 方法使用 "new" 关键字来隐藏 `BaseClass` 中的同名方法。

## 示例
### 基本用法
```csharp
// 定义一个简单的类
public class Person
{
    public string Name { get; set; }

    public Person(string name)
    {
        Name = name;
    }
}

// 使用 new 关键字创建对象实例
Person person = new Person("张三");
Console.WriteLine(person.Name); // 输出：张三
```

### 隐藏基类成员
```csharp
class Animal
{
    public void Speak()
    {
        Console.WriteLine("动物叫");
    }
}

class Dog : Animal
{
    new public void Speak()
    {
        Console.WriteLine("汪汪");
    }
}

// 创建 Dog 对象并调用 Speak 方法
Dog dog = new Dog();
dog.Speak(); // 输出：汪汪

Animal animal = dog;
animal.Speak(); // 输出：动物叫
```

## 说明
- **常见陷阱**: 使用 "new" 关键字隐藏成员时，派生类的对象可以通过基类引用访问基类的方法。如果你希望使用派生类的方法，需要使用派生类的类型来引用对象。
- **额外注意**: 在使用 "new" 关键字时，确保你了解何时需要隐藏而不是覆盖。如果希望在派生类中覆盖基类的成员，应使用 `override` 关键字。

## 一句话总结
在 C# 中，"new" 关键字用于创建对象实例和隐藏基类成员。