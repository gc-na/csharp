<!--
Meta Description: # CSharp 中的 readonly 關鍵字：使用指南與示例 ## 概述 `readonly` 是 CSharp 中的一個關鍵字，用於定義只能在聲明時或構造函數中初始化的字段。使用 `readonly` 可以增強代碼的安全性，確保在對象的生命週期內字段的值不會被修改。 ## 文檔 `readon...
Meta Keywords: readonly, public, csharp, circle, length
-->

# CSharp 中的 readonly 關鍵字：使用指南與示例

## 概述
`readonly` 是 CSharp 中的一個關鍵字，用於定義只能在聲明時或構造函數中初始化的字段。使用 `readonly` 可以增強代碼的安全性，確保在對象的生命週期內字段的值不會被修改。

## 文檔
`readonly` 關鍵字的主要目的是保護對象的狀態，確保在對象創建後，字段的值不能被更改。這意味著一旦對象被實例化，`readonly` 字段只能在構造函數中賦值，而不能在類的其他方法中進行修改。此特性非常有用於不可變對象的設計，促進更清晰的代碼和更少的錯誤。

### 使用方法
在 CSharp 中，使用 `readonly` 關鍵字的基本語法如下：
```csharp
readonly <type> <fieldName>;
```
例如：
```csharp
public class Person
{
    public readonly string Name;

    public Person(string name)
    {
        Name = name; // 只能在此處賦值
    }
}
```
在這個例子中，`Name` 字段被標記為 `readonly`，只能在 `Person` 類的構造函數中賦值。

## 示例
以下是 `readonly` 的基本用法示例：

### 示例 1：基本用法
```csharp
public class Circle
{
    public readonly double Radius;

    public Circle(double radius)
    {
        Radius = radius;
    }
}

// 使用
Circle circle = new Circle(5.0);
Console.WriteLine(circle.Radius); // 輸出: 5.0
```
### 示例 2：試圖修改 `readonly` 字段
```csharp
public class Rectangle
{
    public readonly double Length;

    public Rectangle(double length)
    {
        Length = length;
    }

    public void ChangeLength(double newLength)
    {
        // Length = newLength; // 這將導致編譯錯誤
    }
}
```
在這個例子中，試圖在 `ChangeLength` 方法中修改 `Length` 字段會導致編譯錯誤，因為該字段是 `readonly`。

## 解釋
使用 `readonly` 時，有幾個常見的陷阱和注意事項：

1. **初始化限制**：`readonly` 字段只能在聲明時或構造函數中初始化，這意味著在對象創建後不能再更改。
2. **靜態字段**：如果 `readonly` 用於靜態字段，則可以在靜態構造函數中賦值。
3. **不可變對象**：在設計不可變對象時，`readonly` 特性提供了保護，防止對象狀態的意外變更。

## 一句總結
`readonly` 關鍵字在 CSharp 中用於創建不可變字段，增加了代碼的安全性和可讀性。