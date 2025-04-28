<!--
Meta Description: # CSharp 中的靜態 (static) 關鍵字詳細介紹 ## 概述 靜態 (static) 是 CSharp 中的一種關鍵字，用於定義靜態成員或靜態方法，這些成員和方法不需要實例化類別即可使用。靜態成員屬於類別本身而不是類別的實例，這使得它們在內存中只有一個副本，並且在所有實例間共享。 ## ...
Meta Keywords: static, csharp, public, int, class
-->

# CSharp 中的靜態 (static) 關鍵字詳細介紹

## 概述
靜態 (static) 是 CSharp 中的一種關鍵字，用於定義靜態成員或靜態方法，這些成員和方法不需要實例化類別即可使用。靜態成員屬於類別本身而不是類別的實例，這使得它們在內存中只有一個副本，並且在所有實例間共享。

## 文檔
靜態關鍵字的主要用途是定義靜態類別、靜態方法和靜態屬性。靜態類別是無法被實例化的類別，通常用於封裝靜態方法。靜態方法可以直接通過類別名稱來調用，而無需創建該類別的實例。靜態屬性則用於存儲全局狀態或數據。

### 用法
- **靜態方法**: 使用 `static` 關鍵字聲明的方法，可以在沒有類別實例的情況下調用。
- **靜態屬性**: 使用 `static` 關鍵字聲明的屬性，屬於類別，而不是某個特定的實例。
- **靜態類別**: 整個類別都可以被聲明為靜態，這樣該類別內的所有成員都必須是靜態的。

## 範例
### 靜態方法範例
```csharp
public class MathUtils
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}

// 使用靜態方法
int result = MathUtils.Add(5, 10);
```

### 靜態屬性範例
```csharp
public class Configuration
{
    public static string AppName { get; set; } = "我的應用程式";
}

// 使用靜態屬性
string appName = Configuration.AppName;
```

### 靜態類別範例
```csharp
public static class Logger
{
    public static void Log(string message)
    {
        Console.WriteLine(message);
    }
}

// 使用靜態類別
Logger.Log("這是一條日誌消息");
```

## 解釋
在使用靜態成員時，有一些常見的陷阱需要注意：
1. **無法訪問實例成員**: 靜態方法和靜態屬性無法直接訪問類別中非靜態的成員，必須通過實例來訪問。
2. **全局狀態問題**: 靜態屬性會在所有實例間共享，這可能導致意外的行為，特別是在多執行緒環境中。
3. **單元測試挑戰**: 靜態方法往往難以進行單元測試，因為它們無法被虛擬化或模擬。

## 一句總結
靜態 (static) 關鍵字使 CSharp 開發者能夠定義共享的類別成員和方法，無需創建實例即可使用。