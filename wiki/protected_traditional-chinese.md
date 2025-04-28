<!--
Meta Description: # C# 中的 `protected` 關鍵字：用於控制成員訪問的關鍵技術 ## 簡介 在 C# 編程語言中，`protected` 是一個訪問修飾符，用於控制類成員（屬性和方法）的可見性。它允許類的子類別（繼承的類）訪問父類別中的成員，但對於其他類別則保持封閉。 ## 文檔 ### 目的 `pro...
Meta Keywords: protected, public, class, void, animal
-->

# C# 中的 `protected` 關鍵字：用於控制成員訪問的關鍵技術

## 簡介
在 C# 編程語言中，`protected` 是一個訪問修飾符，用於控制類成員（屬性和方法）的可見性。它允許類的子類別（繼承的類）訪問父類別中的成員，但對於其他類別則保持封閉。

## 文檔
### 目的
`protected` 修飾符的主要目的是促進對繼承機制的支持，讓子類別可以訪問父類別的成員而不需要將這些成員公開給所有其他類別。

### 用法
在 C# 中，您可以在類內部定義屬性或方法時使用 `protected` 修飾符。這意味著該成員可以被同一類別或任何派生類別訪問。例如：

```csharp
public class BaseClass
{
    protected int protectedField;

    protected void ProtectedMethod()
    {
        // 方法實現
    }
}

public class DerivedClass : BaseClass
{
    public void AccessProtectedMembers()
    {
        protectedField = 10; // 可以訪問
        ProtectedMethod();    // 可以調用
    }
}
```

### 詳細說明
- `protected` 修飾符只能用於類的成員，無法用於類型或命名空間。
- 與 `private` 修飾符不同，`protected` 允許子類別訪問父類別的成員。
- 在 C# 中，還有一個 `protected internal` 修飾符，它結合了 `protected` 和 `internal` 的特性，允許同一個程序集中的類和所有派生類訪問。

## 示例
這是一個使用 `protected` 的簡單示例，顯示了如何在基類和派生類之間共享成員：

```csharp
public class Animal
{
    protected string name;

    protected void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public void Bark()
    {
        name = "Dog";
        Speak(); // 調用基類的受保護方法
        Console.WriteLine($"{name} barks");
    }
}
```

在這個例子中，`Dog` 類可以訪問 `Animal` 類中的 `name` 屬性和 `Speak` 方法。

## 說明
- **常見陷阱**：如果嘗試在非派生類別中訪問 `protected` 成員，將會導致編譯錯誤。
- **注意事項**：在設計類時，合理使用 `protected` 可以促進代碼重用和擴展性，但也要謹慎，避免過度暴露類的內部實現。

## 總結
`protected` 修飾符在 C# 中用於控制類成員的可見性，允許子類別訪問父類別的成員，從而支持良好的繼承機制。