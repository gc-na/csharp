<!--
Meta Description: # C# 中的 const 關鍵字：不可變數的使用與實踐 ## 簡介 在 C# 編程中，`const` 關鍵字用於定義不可變的常數。這些常數在編譯時就已經被確定，並且在整個程式中保持不變，從而提高了代碼的可讀性和穩定性。 ## 文檔 `const` 是 C# 語言中的一個修飾符，用於聲明常數。常數是...
Meta Keywords: const, csharp, string, console, writeline
-->

# C# 中的 const 關鍵字：不可變數的使用與實踐

## 簡介
在 C# 編程中，`const` 關鍵字用於定義不可變的常數。這些常數在編譯時就已經被確定，並且在整個程式中保持不變，從而提高了代碼的可讀性和穩定性。

## 文檔
`const` 是 C# 語言中的一個修飾符，用於聲明常數。常數是在編譯時期就被賦值的變量，其值在運行時不能被修改。這意味著，使用 `const` 定義的變量在程序的生命週期中始終保持不變。

### 目的
`const` 的主要目的是提供一種方式來定義不會更改的值，這些值可以在程序的多個地方重用，從而減少錯誤的可能性並提高代碼的可維護性。

### 使用方式
要使用 `const`，只需在變量聲明時加上 `const` 關鍵字。以下是基本的語法：

```csharp
const <數據類型> <變量名稱> = <初始值>;
```

其中，數據類型可以是任何有效的 C# 數據類型，如 `int`, `string`, `double` 等。

### 詳細說明
- `const` 變量必須在聲明時進行初始化，並且不能在之後的代碼中被重新賦值。
- `const` 變量的值在編譯時確定，因此它們可以被用作其他常量的初始化。
- `const` 變量的作用域可以是全局的（如果在類外部定義）或局部的（如果在方法中定義）。

## 範例
以下是一些使用 `const` 的基本範例：

```csharp
class Program
{
    const double Pi = 3.14159;

    static void Main(string[] args)
    {
        Console.WriteLine("圓周率的值是: " + Pi);
        
        // 下面這行會導致編譯錯誤
        // Pi = 3.14; // Cannot assign to 'Pi' because it is read-only
    }
}
```

```csharp
class MathConstants
{
    public const int DaysInWeek = 7;
    public const string AppName = "My Application";
    
    public void DisplayConstants()
    {
        Console.WriteLine($"一周有 {DaysInWeek} 天");
        Console.WriteLine($"應用名稱: {AppName}");
    }
}
```

## 解釋
在使用 `const` 時，有一些常見的陷阱和注意事項：
- **初始化要求**：`const` 變量必須在聲明時初始化，否則會引發編譯錯誤。
- **類型限制**：雖然所有基本數據類型都可以使用 `const`，但當涉及到複雜類型（如對象）時，應使用 `readonly` 代替，因為 `const` 不能用於對象的實例。
- **範圍限制**：`const` 變量的作用域受限於其定義的範圍，這意味著你需要小心不要在不適當的範圍內使用它。

## 一行總結
`const` 是 C# 中用於定義在編譯時期固定的不可變常數的關鍵字，增強了代碼的可讀性和維護性。