<!--
Meta Description: # C# 中的 typeof：类型获取的关键字 ## 概述 `typeof` 是 C# 中的一个关键字，用于获取特定类型的 Type 对象。这在反射、类型检查以及动态编程中非常有用。 ## 文档 ### 目的 `typeof` 关键字允许开发者在编程时以类型作为参数，从而获取该类型的元数据。它是一种...
Meta Keywords: typeof, type, csharp, console, writeline
-->

# C# 中的 typeof：类型获取的关键字

## 概述
`typeof` 是 C# 中的一个关键字，用于获取特定类型的 Type 对象。这在反射、类型检查以及动态编程中非常有用。

## 文档
### 目的
`typeof` 关键字允许开发者在编程时以类型作为参数，从而获取该类型的元数据。它是一种编译时操作，意味着在编译时就已确定类型。

### 使用方法
使用 `typeof` 的基本语法如下：
```csharp
Type type = typeof(YourType);
```
其中，`YourType` 可以是任何有效的 C# 类型，包括基本类型、类、结构、接口等。

### 详细信息
- `typeof` 返回一个 Type 对象，代表所指定的类型。
- 该 Type 对象可用于获取类型的信息，例如属性、方法、字段等。
- `typeof` 是一个操作符，不是一个方法，因此不需要括号。

## 示例
### 示例 1：获取基本类型
```csharp
Type intType = typeof(int);
Console.WriteLine(intType); // 输出：System.Int32
```

### 示例 2：获取自定义类类型
```csharp
public class MyClass { }

Type myClassType = typeof(MyClass);
Console.WriteLine(myClassType); // 输出：YourNamespace.MyClass
```

### 示例 3：获取接口类型
```csharp
public interface IMyInterface { }

Type interfaceType = typeof(IMyInterface);
Console.WriteLine(interfaceType); // 输出：YourNamespace.IMyInterface
```

## 说明
在使用 `typeof` 时，开发者需要注意以下几点：
- 确保使用的类型名称是有效且可访问的，如果类型不存在，将在编译时引发错误。
- `typeof` 只能用于类型，不能用于实例。即不能对变量或对象使用 `typeof`。
- `typeof` 的返回结果是一个 Type 对象，可以使用该对象的各种方法和属性来获取更多信息。

## 一句话总结
`typeof` 是 C# 中用于获取指定类型的 Type 对象的关键字，便于类型反射和元数据操作。