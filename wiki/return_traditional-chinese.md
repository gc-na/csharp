<!--
Meta Description: # C#中的「return」關鍵字：用於控制函數的返回值 ## 簡介 在C#編程語言中，「return」關鍵字用於從方法中返回值，並結束方法的執行。這個關鍵字對於控制方法的流程及其結果至關重要。 ## 文件說明 「return」關鍵字的主要目的是將一個值返回給調用該方法的代碼。它可以用於任何類型的函...
Meta Keywords: return, void, int, public, string
-->

# C#中的「return」關鍵字：用於控制函數的返回值

## 簡介
在C#編程語言中，「return」關鍵字用於從方法中返回值，並結束方法的執行。這個關鍵字對於控制方法的流程及其結果至關重要。

## 文件說明
「return」關鍵字的主要目的是將一個值返回給調用該方法的代碼。它可以用於任何類型的函數，包括無返回值的「void」方法。在這種情況下，使用「return」可以提前終止方法的執行。

### 使用方法
- 在有返回值的函數中，需指定與函數返回類型相符的值。
- 在「void」類型的方法中，使用「return」可以結束方法而不返回任何值。

### 詳細說明
1. **返回值類型**：返回值的類型必須與方法簽名中定義的返回類型相匹配。
2. **無返回值的情況**：在「void」方法中，使用「return」可以選擇性地提前結束方法的執行。
3. **多個返回點**：一個方法中可以包含多個「return」語句，根據不同的條件來選擇返回的值。
4. **結束方法執行**：當「return」語句執行時，方法的其餘部分將不會被執行。

## 範例
### 基本用法範例
```csharp
public int Add(int a, int b)
{
    return a + b; // 返回兩個數字的和
}

public void PrintMessage(string message)
{
    if (string.IsNullOrEmpty(message))
    {
        return; // 早期結束方法
    }
    Console.WriteLine(message);
}
```

### 進階範例
```csharp
public string GetStatus(int score)
{
    if (score >= 90)
    {
        return "優秀";
    }
    else if (score >= 75)
    {
        return "良好";
    }
    else
    {
        return "需要改進";
    }
}
```

## 說明
- **常見陷阱**：在方法中使用「return」時，需確保所有的控制路徑都有返回值。否則，編譯器將會報錯。
- **返回null的情況**：若方法的返回類型是可為null的類型（如參考類型），可以返回null作為有效的返回值。
- **可讀性**：過多的返回點可能會使代碼可讀性下降，因此在設計方法時應謹慎考慮。

## 一句話總結
「return」關鍵字在C#中用於從方法返回值並結束方法的執行，是控制程序流的重要工具。