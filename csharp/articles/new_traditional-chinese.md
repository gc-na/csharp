<!--
Meta Description: # C# 中的 "new" 關鍵字：創建物件與隱藏成員 ## 簡介 在 C# 中，"new" 關鍵字是用來創建物件實例，以及在繼承關係中隱藏基類成員的重要工具。這個關鍵字對於物件導向程式設計至關重要，因為它允許開發人員有效地管理記憶體並構造新物件。 ## 文檔 ### 目的 C# 的 "new" 關...
Meta Keywords: new, public, class, console, writeline
-->

# C# 中的 "new" 關鍵字：創建物件與隱藏成員

## 簡介
在 C# 中，"new" 關鍵字是用來創建物件實例，以及在繼承關係中隱藏基類成員的重要工具。這個關鍵字對於物件導向程式設計至關重要，因為它允許開發人員有效地管理記憶體並構造新物件。

## 文檔
### 目的
C# 的 "new" 關鍵字主要用於兩個方面：
1. 創建物件的實例。
2. 在派生類別中隱藏基類別的成員。

### 用法
1. **創建物件：**
   當使用 "new" 來創建物件時，會在記憶體中分配空間，並呼叫該物件的建構函式來初始化其狀態。
   ```csharp
   ClassName obj = new ClassName();
   ```

2. **隱藏成員：**
   當子類別希望隱藏基類別的成員時，可以使用 "new" 關鍵字來指示這一點。
   ```csharp
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

## 範例
### 創建物件的範例
```csharp
public class Car
{
    public string Model { get; set; }

    public Car(string model)
    {
        Model = model;
    }
}

Car myCar = new Car("Toyota");
Console.WriteLine(myCar.Model); // 輸出: Toyota
```

### 隱藏成員的範例
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
    public new void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

Animal myDog = new Dog();
myDog.Speak(); // 輸出: Animal speaks
```

## 解釋
### 常見陷阱
- **隱藏成員的誤解：** 使用 "new" 隱藏成員時，基類的成員仍然存在。這可能導致混淆，特別是在多型性使用時，因為基類參考將呼叫基類的方法，而不是派生類別的方法。
  
- **未初始化的物件：** 在使用 "new" 創建物件時，確保所有必要的參數都已傳遞給建構函式，以避免未初始化的物件導致的錯誤。

### 附加說明
- "new" 關鍵字在 C# 中具有多重用途，並且在正確使用時可以增強代碼的可讀性和可維護性。
- 儘管 "new" 關鍵字在某些情況下是可選的，為了明確性，建議在隱藏基類成員時始終使用它。

## 一句總結
C# 中的 "new" 關鍵字用於創建物件實例及在繼承中隱藏基類成員，對於物件導向程式設計至關重要。