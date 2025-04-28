<!--
Meta Description: # C# 中的 sealed 关键字详解 ## 摘要 `sealed` 关键字用于 C# 中的类和方法，表示该类无法被继承，或该方法不能被重写，确保了类的封闭性和安全性。 ## 文档 在 C# 中，`sealed` 关键字可以应用于类和方法。其主要目的是阻止其他类从 `sealed` 类派生，或者阻...
Meta Keywords: sealed, public, class, void, derivedclass
-->

# C# 中的 sealed 关键字详解

## 摘要
`sealed` 关键字用于 C# 中的类和方法，表示该类无法被继承，或该方法不能被重写，确保了类的封闭性和安全性。

## 文档
在 C# 中，`sealed` 关键字可以应用于类和方法。其主要目的是阻止其他类从 `sealed` 类派生，或者阻止派生类重写 `sealed` 方法。

### 用途
1. **类的封闭性**：当一个类被声明为 `sealed` 时，表示该类不能作为基类被继承。这在需要保持类的完整性和限制扩展时非常有用。
2. **方法的封闭性**：当一个虚方法被声明为 `sealed` 时，表示该方法在派生类中不能被重写。这有助于防止对关键逻辑的意外修改。

### 使用方式
- 对类的定义：在类前面加上 `sealed` 关键字。
- 对方法的定义：在虚方法（`virtual`）前面加上 `sealed` 关键字，并且还需要加上 `override` 关键字。

## 示例
### 示例 1：封闭类
```csharp
public sealed class SealedClass
{
    public void Display()
    {
        Console.WriteLine("这是一个封闭类。");
    }
}

// 下面的代码将导致编译错误：无法从 'SealedClass' 继承
// public class DerivedClass : SealedClass { }
```

### 示例 2：封闭方法
```csharp
public class BaseClass
{
    public virtual void Show()
    {
        Console.WriteLine("基类方法。");
    }
}

public class DerivedClass : BaseClass
{
    public sealed override void Show()
    {
        Console.WriteLine("派生类的封闭方法。");
    }
}

// 下面的代码将导致编译错误：无法重写 'DerivedClass.Show()'
// public class AnotherDerivedClass : DerivedClass
// {
//     public override void Show() { }
// }
```

## 说明
- **常见陷阱**：使用 `sealed` 关键字时，开发者必须确保确实不需要让其他类扩展该类或重写该方法。过早地将类或方法标记为 `sealed` 可能会限制未来的扩展性。
- **继承链限制**：如果一个类已经被声明为 `sealed`，那么所有尝试从其继承的类都会导致编译错误。
- **性能考虑**：在某些情况下，使用 `sealed` 关键字可以提升性能，特别是在某些运行时优化的场景中，因为它允许编译器做出一定的假设。

## 一句话总结
C# 中的 `sealed` 关键字用于限制类的继承和方法的重写，确保类的封闭性和安全性。