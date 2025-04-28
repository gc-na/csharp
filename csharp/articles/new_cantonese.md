<!--
Meta Description: # CSharp 中的 "new" 關鍵字：用途與示例 ## 摘要 在 CSharp 中，"new" 關鍵字用於創建對象的實例或隱藏基類中的成員。這是一個基本但重要的功能，對於面向對象編程至關重要。 ## 文檔 ### 目的 "new" 關鍵字通常用於以下兩個主要目的： 1. **創建對象實例**：...
Meta Keywords: new, public, csharp, person, class
-->

# CSharp 中的 "new" 關鍵字：用途與示例

## 摘要
在 CSharp 中，"new" 關鍵字用於創建對象的實例或隱藏基類中的成員。這是一個基本但重要的功能，對於面向對象編程至關重要。

## 文檔
### 目的
"new" 關鍵字通常用於以下兩個主要目的：
1. **創建對象實例**：使用 "new" 可以創建類的實例，並分配內存以存儲該實例的數據。
2. **隱藏基類成員**：在派生類中使用 "new" 可以隱藏基類中的成員，這樣可以避免名稱衝突。

### 用法
```csharp
// 創建對象實例
MyClass myObject = new MyClass();

// 隱藏基類成員
public class BaseClass
{
    public void Display() 
    {
        Console.WriteLine("BaseClass Display");
    }
}

public class DerivedClass : BaseClass
{
    public new void Display() 
    {
        Console.WriteLine("DerivedClass Display");
    }
}
```

## 示例
### 創建對象實例
```csharp
public class Person
{
    public string Name { get; set; }
    
    public Person(string name)
    {
        Name = name;
    }
}

Person person = new Person("John");
Console.WriteLine(person.Name); // 輸出: John
```

### 隱藏基類成員
```csharp
public class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public new void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

Animal myDog = new Dog();
myDog.Speak(); // 輸出: Animal speaks
```

## 解釋
- **常見陷阱**：使用 "new" 隱藏基類成員時，當使用基類類型的引用調用該成員時，會調用基類中的版本，而不是派生類中的版本。這可能會導致意外的行為。
  
- **注意事項**：在不需要隱藏行為的情況下，通常建議使用虛擬方法（`virtual`）和重寫方法（`override`）來實現多態性，這樣可以更清晰地表達代碼意圖。

## 一句總結
在 CSharp 中，"new" 關鍵字用於創建對象實例和隱藏基類的成員，但需謹慎使用以避免潛在的行為問題。