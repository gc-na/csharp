<!--
Meta Description: # C# 中的 Override 關鍵字：深入探討與實例 ## 摘要 在 C# 中，`override` 關鍵字用於重新定義基類中的虛擬方法，使得子類別可以提供特定的實現。這是物件導向編程中多態性的核心元素之一。 ## 文檔 ### 目的 `override` 允許開發者在衍生類別中重寫基類中的虛擬...
Meta Keywords: override, public, animal, speak, virtual
-->

# C# 中的 Override 關鍵字：深入探討與實例

## 摘要
在 C# 中，`override` 關鍵字用於重新定義基類中的虛擬方法，使得子類別可以提供特定的實現。這是物件導向編程中多態性的核心元素之一。

## 文檔
### 目的
`override` 允許開發者在衍生類別中重寫基類中的虛擬方法，從而提供特定的行為。這使得同一方法在不同類別中可以有不同的實現，增強了程式碼的可擴展性與可維護性。

### 使用方法
要使用 `override`，必須遵循以下步驟：
1. 在基類中聲明一個虛擬方法，使用 `virtual` 關鍵字。
2. 在衍生類別中使用 `override` 來重寫該虛擬方法。

### 詳細說明
- `override` 只能用於虛擬方法，這些方法必須在基類中定義。
- 當重寫方法時，方法簽名必須與基類中的虛擬方法完全匹配，包括方法名、返回類型和參數。
- 使用 `base` 關鍵字可以在重寫的方法中調用基類的實現。

## 範例
### 基本用法示例
以下是一個簡單的範例，展示如何使用 `override` 來重寫方法：

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

public class Cat : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Cat meows");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal myDog = new Dog();
        myDog.Speak(); // 輸出: Dog barks

        Animal myCat = new Cat();
        myCat.Speak(); // 輸出: Cat meows
    }
}
```

## 解釋
### 常見陷阱
- **方法簽名不匹配**：確保重寫的方法簽名與基類中的虛擬方法完全一致，否則會導致編譯錯誤。
- **未使用 `virtual` 關鍵字**：在基類中未將方法標記為 `virtual`，則不能被重寫。
- **無法重寫非虛擬方法**：只有虛擬方法和抽象方法可以被重寫，普通方法則無法使用 `override`。

### 附加說明
- `override` 方法可以使用 `new` 關鍵字來隱藏基類中的方法，但這並不等同於重寫。使用 `new` 會創建一個新的方法，而不是重寫基類的方法。

## 一句總結
在 C# 中，`override` 關鍵字允許子類別重新定義基類的虛擬方法，實現多態性和特定行為的定制。