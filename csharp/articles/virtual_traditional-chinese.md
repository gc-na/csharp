<!--
Meta Description: # C# 中的虛擬 (virtual) 關鍵字：功能與用法 ## 簡介 在 C# 中，`virtual` 關鍵字用於定義可被派生類別重寫的方法或屬性。這使得透過多型性來實現動態綁定成為可能，從而提高了程式的靈活性和可維護性。 ## 文檔 ### 目的 `virtual` 關鍵字的主要目的是允許基類提...
Meta Keywords: public, virtual, animal, class, void
-->

# C# 中的虛擬 (virtual) 關鍵字：功能與用法

## 簡介
在 C# 中，`virtual` 關鍵字用於定義可被派生類別重寫的方法或屬性。這使得透過多型性來實現動態綁定成為可能，從而提高了程式的靈活性和可維護性。

## 文檔
### 目的
`virtual` 關鍵字的主要目的是允許基類提供一個預設的實現，並允許派生類別根據需求重寫該實現。這在面向對象的程式設計中非常重要，因為它支持多型性。

### 用法
當你在一個類別的方法或屬性前使用 `virtual` 關鍵字時，這表示該方法或屬性可以在任何派生類別中被重寫。定義方法為虛擬的語法如下：

```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Base class display");
    }
}
```

在派生類別中重寫 `Display` 方法的語法如下：

```csharp
public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Derived class display");
    }
}
```

### 詳細說明
- **虛擬方法**：可以在基類中定義一個虛擬方法，並在派生類別中使用 `override` 關鍵字來重寫它。
- **虛擬屬性**：同樣，屬性也可以被定義為虛擬的，允許派生類別提供不同的實現。
- **預設行為**：如果派生類別不重寫虛擬方法，則會使用基類中定義的預設行為。

## 示例
### 基本用法示例
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

public class Program
{
    public static void Main()
    {
        Animal myAnimal = new Animal();
        myAnimal.Speak(); // 輸出: Animal speaks

        Animal myDog = new Dog();
        myDog.Speak(); // 輸出: Dog barks
    }
}
```

### 輸出
- `Animal speaks`
- `Dog barks`

## 解釋
- **常見陷阱**：確保在派生類別中正確使用 `override` 關鍵字，否則編譯器會報錯。
- **無法重寫靜態成員**：`virtual` 關鍵字僅適用於實例成員，不能用於靜態方法。
- **虛擬方法的性能考量**：由於虛擬方法涉及運行時的動態綁定，可能會稍微影響性能，特別是在高頻調用的情況下。

## 一句總結
C# 中的 `virtual` 關鍵字允許基類定義可由派生類別重寫的方法或屬性，以實現靈活的多型性。