<!--
Meta Description: # C# 中的 "base" 關鍵字：用於基類的引用與調用 ## 簡介 在 C# 中，`base` 是一個重要的關鍵字，用於引用基類的成員，包括方法、屬性和索引器。這使得派生類能夠訪問其基類中的成員，特別是在覆寫方法或使用基類的構造函數時。 ## 文檔 ### 目的 `base` 關鍵字的主要目的是...
Meta Keywords: base, dog, animal, public, name
-->

# C# 中的 "base" 關鍵字：用於基類的引用與調用

## 簡介
在 C# 中，`base` 是一個重要的關鍵字，用於引用基類的成員，包括方法、屬性和索引器。這使得派生類能夠訪問其基類中的成員，特別是在覆寫方法或使用基類的構造函數時。

## 文檔
### 目的
`base` 關鍵字的主要目的是提供對基類成員的訪問，讓開發者能夠在派生類中調用基類的實現。

### 用法
`base` 可以用於以下情況：
1. **調用基類的構造函數**：在派生類的構造函數中使用 `base()` 可以調用基類的構造函數。
2. **訪問基類的成員**：在派生類中可以用 `base.成員名稱` 的方式調用基類中的方法或屬性。

### 詳細說明
- **基類構造函數調用**：當創建派生類的實例時，通常會先調用基類的構造函數。若基類有參數構造函數，則需要在派生類的構造函數中使用 `base(參數)` 來正確初始化基類部分。
  
- **方法覆寫**：當派生類覆寫基類的方法時，可以使用 `base.方法名稱()` 來調用基類的原始方法，這對於保留基類的行為非常有用。

## 範例
以下是使用 `base` 的基本範例：

```csharp
public class Animal
{
    public Animal(string name)
    {
        Console.WriteLine($"Animal: {name}");
    }
    
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public Dog(string name) : base(name)
    {
    }
    
    public void Bark()
    {
        base.Speak(); // 調用基類的 Speak 方法
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main()
    {
        Dog dog = new Dog("Buddy");
        dog.Bark();
    }
}
```

### 輸出
```
Animal: Buddy
Animal speaks
Dog barks
```

## 解釋
- **常見陷阱**：在使用 `base` 進行方法調用時，若基類中不存在相應的方法，將導致編譯錯誤。確保基類中定義了要調用的成員。
- **覆寫限制**：在派生類中，對基類成員的訪問受到訪問修飾符的限制，只有公共或保護的成員可以被派生類通過 `base` 訪問。

## 一句話總結
`base` 關鍵字用於在 C# 中引用基類的成員，特別是在構造函數和方法覆寫的情況下。