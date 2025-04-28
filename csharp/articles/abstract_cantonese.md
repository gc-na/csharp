<!--
Meta Description: # CSharp 中的抽象 (Abstract) 關鍵字 ## 概要 在 CSharp 中，`abstract` 關鍵字用於定義抽象類別和抽象方法，這些是用來提供基類的共同介面，讓衍生類別可以實現具體的行為。 ## 文件說明 `abstract` 是 CSharp 中的一個重要關鍵字，主要用於物件導...
Meta Keywords: abstract, public, csharp, class, void
-->

# CSharp 中的抽象 (Abstract) 關鍵字

## 概要
在 CSharp 中，`abstract` 關鍵字用於定義抽象類別和抽象方法，這些是用來提供基類的共同介面，讓衍生類別可以實現具體的行為。

## 文件說明
`abstract` 是 CSharp 中的一個重要關鍵字，主要用於物件導向程式設計。抽象類別不能被實例化，意即我們不能直接創建這類型的物件。相反，開發者應該創建衍生類別來實現抽象類別中的抽象方法。這種設計模式促進了代碼的重用性和可維護性。

### 目的
- 定義一個共同的類別結構，供其他類別繼承。
- 提供抽象方法，讓衍生類別實現各自的具體行為。

### 使用方法
- 使用 `abstract` 關鍵字來聲明類別或方法。
- 抽象類別可以包含已實現的方法和屬性，也可以包含抽象方法。

### 詳細說明
1. **抽象類別**: 
   - 使用 `abstract class` 來定義。
   - 不能被直接實例化。

2. **抽象方法**: 
   - 使用 `abstract` 修飾符來定義。
   - 必須在衍生類別中實現。

## 示例
以下是使用 `abstract` 關鍵字的基本範例：

```csharp
// 定義一個抽象類別
public abstract class 動物
{
    // 抽象方法
    public abstract void 發聲();

    // 已實現的方法
    public void 休息()
    {
        Console.WriteLine("動物正在休息。");
    }
}

// 繼承抽象類別
public class 狗 : 動物
{
    // 實現抽象方法
    public override void 發聲()
    {
        Console.WriteLine("汪汪！");
    }
}

// 主程式
public class Program
{
    public static void Main()
    {
        狗 myDog = new 狗();
        myDog.發聲(); // 輸出: 汪汪！
        myDog.休息(); // 輸出: 動物正在休息。
    }
}
```

## 解釋
在使用 `abstract` 關鍵字時，需要注意以下幾點：
- **不能實例化抽象類別**: 直接聲明 `new 動物()` 會導致編譯錯誤。
- **必須實現所有抽象方法**: 在衍生類別中，必須提供所有抽象方法的實現。
- **多重繼承**: CSharp 不支持多重繼承，但可以通過接口來實現類似的功能。

## 總結
`abstract` 關鍵字是 CSharp 中的一個強大工具，允許開發者定義基類架構並強制衍生類別實現具體行為。