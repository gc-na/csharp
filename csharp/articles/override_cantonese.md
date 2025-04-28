<!--
Meta Description: # CSharp 中的 "override" 關鍵字：用於方法重寫的完整指南 ## 概要 在 CSharp 中，`override` 關鍵字用於重寫基類中的虛擬方法，使子類能夠提供不同的實現。 ## 文檔 `override` 是 CSharp 中一個重要的關鍵字，主要用於物件導向編程。當一個基類（...
Meta Keywords: override, public, csharp, animal, speak
-->

# CSharp 中的 "override" 關鍵字：用於方法重寫的完整指南

## 概要
在 CSharp 中，`override` 關鍵字用於重寫基類中的虛擬方法，使子類能夠提供不同的實現。

## 文檔
`override` 是 CSharp 中一個重要的關鍵字，主要用於物件導向編程。當一個基類（父類）定義了一個虛擬方法（使用 `virtual` 關鍵字），子類（派生類）可以使用 `override` 關鍵字來提供該方法的具體實現。這種特性使得多態性成為可能，允許不同的對象以不同的方式響應相同的方法調用。

### 用法
- 在基類中定義虛擬方法：
  ```csharp
  public class Animal
  {
      public virtual void Speak()
      {
          Console.WriteLine("動物發出聲音");
      }
  }
  ```

- 在子類中重寫虛擬方法：
  ```csharp
  public class Dog : Animal
  {
      public override void Speak()
      {
          Console.WriteLine("狗叫：汪！");
      }
  }
  ```

## 範例
以下是使用 `override` 的基本示例：

```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("動物發出聲音");
    }
}

public class Cat : Animal
{
    public override void Speak()
    {
        Console.WriteLine("貓叫：喵！");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak(); // 輸出：狗叫：汪！

        Animal myCat = new Cat();
        myCat.Speak(); // 輸出：貓叫：喵！
    }
}
```

## 解釋
使用 `override` 時需要注意幾個常見的陷阱：

1. **基類方法必須標記為虛擬**：只有當基類中的方法被標記為 `virtual` 或 `abstract` 時，才能使用 `override` 進行重寫。
  
2. **方法簽名必須一致**：重寫的方法必須與基類中的虛擬方法具有相同的返回類型和參數列表。

3. **無法重寫非虛擬方法**：如果基類方法不是虛擬的，則無法使用 `override` 進行重寫。

4. **調用基類方法**：在重寫的方法中，可以使用 `base` 關鍵字來調用基類的實現。

### 額外提示
使用 `override` 可以增強代碼的可讀性和可維護性，並促進更好的設計模式，因此在設計類結構時應充分考慮。

## 一句總結
`override` 關鍵字在 CSharp 中用於重寫基類的虛擬方法，實現多態性和靈活的對象行為。