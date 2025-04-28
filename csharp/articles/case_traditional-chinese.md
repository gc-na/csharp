<!--
Meta Description: # C# 中的 switch-case 陳述式：用法與範例 ## 概述 在 C# 中，switch-case 陳述式是一種多重選擇結構，用於根據變數的值執行不同的程式碼塊。它提供了一種比多重 if-else 陳述式更清晰和結構化的方式來處理多種情況。 ## 文檔 ### 目的 switch-case...
Meta Keywords: case, break, switch, dayname, expression
-->

# C# 中的 switch-case 陳述式：用法與範例

## 概述
在 C# 中，switch-case 陳述式是一種多重選擇結構，用於根據變數的值執行不同的程式碼塊。它提供了一種比多重 if-else 陳述式更清晰和結構化的方式來處理多種情況。

## 文檔
### 目的
switch-case 陳述式旨在根據變數的值選擇要執行的程式碼塊。這使得程式碼更具可讀性和可維護性，尤其是在處理多個選擇時。

### 使用方式
基本語法如下：
```csharp
switch (expression)
{
    case value1:
        // 當 expression 等於 value1 時執行的程式碼
        break;
    case value2:
        // 當 expression 等於 value2 時執行的程式碼
        break;
    default:
        // 當 expression 不符合任何 case 時執行的程式碼
        break;
}
```
- `expression`：要檢查的變數或表達式。
- `case value`：每個 case 的值，當 `expression` 與這些值匹配時執行相應的程式碼。
- `break`：用於結束 switch-case 陳述式，防止執行後續的 case。
- `default`：可選項，當沒有任何 case 匹配時執行。

## 範例
以下是一個簡單的範例，展示如何使用 switch-case 陳述式：
```csharp
int day = 3;
string dayName;

switch (day)
{
    case 1:
        dayName = "星期一";
        break;
    case 2:
        dayName = "星期二";
        break;
    case 3:
        dayName = "星期三";
        break;
    case 4:
        dayName = "星期四";
        break;
    case 5:
        dayName = "星期五";
        break;
    default:
        dayName = "週末";
        break;
}

Console.WriteLine(dayName);  // 輸出：星期三
```

## 解釋
在使用 switch-case 陳述式時，有幾個常見的問題需要注意：
1. **缺少 break**：如果沒有使用 `break`，程式將繼續執行後面的 case，這可能會導致意外的行為。
2. **資料類型限制**：在 C# 中，switch-case 陳述式只能用於整數、字串、列舉或可列舉的型別，不能用於浮點數或其他型別。
3. **不支持範圍**：case 的值必須是常量，無法使用範圍或變數作為 case 的值。

## 總結
C# 的 switch-case 陳述式提供了一個清晰的方式來處理多重選擇情況，透過簡單的語法結構讓程式碼的可讀性和可維護性大幅提升。