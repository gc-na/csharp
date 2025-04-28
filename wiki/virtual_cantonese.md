<!--
Meta Description: # CSharp 中的 "virtual" 關鍵字：功能與應用 ## 概述 在 CSharp 中，`virtual` 關鍵字用於定義可以在派生類別中被覆寫的方法或屬性。這使得多態性成為可能，讓開發者能夠根據具體實現來改變行為。 ## 文檔 ### 目的 `virtual` 關鍵字主要用於支持面向對象...
Meta Keywords: virtual, animal, public, csharp, override
-->

# CSharp 中的 "virtual" 關鍵字：功能與應用

## 概述
在 CSharp 中，`virtual` 關鍵字用於定義可以在派生類別中被覆寫的方法或屬性。這使得多態性成為可能，讓開發者能夠根據具體實現來改變行為。

## 文檔
### 目的
`virtual` 關鍵字主要用於支持面向對象編程中的多態性。它允許派生類別覆寫基類的方法或屬性，以提供特定的實現。

### 用法
要使用 `virtual` 關鍵字，您需要在基類中聲明一個方法或屬性為 `virtual`，然後在派生類中使用 `override` 關鍵字來提供具體實現。

### 詳情
- **聲明**：當您在基類中聲明一個方法為 `virtual` 時，該方法可以在任何繼承這個類的子類中被覆寫。
- **覆寫**：在派生類中，您可以通過 `override` 關鍵字來定義具體實現。
- **靜態與虛擬**：注意，`virtual` 方法無法是靜態方法，因為靜態方法與實例無關，無法在運行時決定具體的實現。

## 範例
以下是一個使用 `virtual` 關鍵字的基本範例：

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

## 解釋
- **常見陷阱**：如果在基類中不使用 `virtual` 標記，則派生類將無法覆寫該方法。
- **隱式覆寫**：如果您在派生類中定義一個方法與基類同名但不使用 `override`，則將創建一個新的方法，這可能導致混淆。
- **抽象類**：如果您希望強制所有派生類都必須實現某個方法，可以使用 `abstract` 關鍵字，這將使該方法無法擁有實現。

## 一句話總結
`virtual` 關鍵字在 CSharp 中用於定義可被派生類覆寫的方法，從而實現多態性。