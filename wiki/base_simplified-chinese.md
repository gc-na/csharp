<!--
Meta Description: # C# 中的 "base" 关键字详解 ## 简介 在 C# 编程语言中，`base` 关键字用于访问基类成员，特别是在派生类中。当你需要在派生类中调用基类的构造函数、方法或属性时，`base` 关键字是必不可少的。 ## 文档 `base` 关键字的主要目的是提供对基类的直接访问。在面向对象编程...
Meta Keywords: base, derivedclass, baseclass, class, public
-->

# C# 中的 "base" 关键字详解

## 简介
在 C# 编程语言中，`base` 关键字用于访问基类成员，特别是在派生类中。当你需要在派生类中调用基类的构造函数、方法或属性时，`base` 关键字是必不可少的。

## 文档
`base` 关键字的主要目的是提供对基类的直接访问。在面向对象编程中，类可以通过继承来扩展其他类的功能。`base` 允许派生类访问基类中定义的成员，确保可以利用基类的特性和功能。

### 用法
1. **访问基类方法**：通过 `base` 关键字，可以在派生类中调用基类的方法。
2. **调用基类构造函数**：在派生类的构造函数中，可以使用 `base` 关键字调用基类的构造函数，以初始化基类部分。
3. **访问基类属性或字段**：可以通过 `base` 关键字直接访问基类中的属性或字段。

### 细节
- `base` 关键字只能在类的上下文中使用，通常是在构造函数或方法内部。
- 当派生类覆盖基类中的成员时，`base` 可以用来调用被覆盖的基类成员。
- 在使用 `base` 关键字时，需确保基类中存在对应的成员，否则会引发编译错误。

## 示例

### 示例 1: 访问基类方法
```csharp
class BaseClass
{
    public void Display()
    {
        Console.WriteLine("Base Class Display Method");
    }
}

class DerivedClass : BaseClass
{
    public void Show()
    {
        base.Display(); // 调用基类的方法
    }
}

// 使用
DerivedClass derived = new DerivedClass();
derived.Show(); // 输出: Base Class Display Method
```

### 示例 2: 调用基类构造函数
```csharp
class BaseClass
{
    public BaseClass(string message)
    {
        Console.WriteLine(message);
    }
}

class DerivedClass : BaseClass
{
    public DerivedClass() : base("Hello from BaseClass") // 调用基类构造函数
    {
        Console.WriteLine("DerivedClass Constructor");
    }
}

// 使用
DerivedClass derived = new DerivedClass();
// 输出: Hello from BaseClass
//       DerivedClass Constructor
```

### 示例 3: 访问基类字段
```csharp
class BaseClass
{
    protected int number = 10;
}

class DerivedClass : BaseClass
{
    public void DisplayNumber()
    {
        Console.WriteLine(base.number); // 访问基类字段
    }
}

// 使用
DerivedClass derived = new DerivedClass();
derived.DisplayNumber(); // 输出: 10
```

## 说明
使用 `base` 关键字时，开发者需要注意以下几点：
- 确保在调用基类成员时，基类中确实包含该成员。
- 如果派生类覆盖了基类的方法，使用 `base` 可以避免调用被覆盖的版本。
- 在构造函数中使用 `base` 时，必须在派生类构造函数的初始化列表中调用。

## 一句话总结
`base` 关键字在 C# 中用于访问基类的成员，确保在派生类中能够有效地利用基类的功能。