<!--
Meta Description: # C# 中的 switch 陳述式：用於條件選擇的強大工具 ## 簡介 C# 中的 `switch` 陳述式是一種控制結構，用於根據變數的不同值執行不同的程式碼區塊。它提供了一種更清晰、更有組織的方法來處理多個條件，比傳統的 `if-else` 結構更易於閱讀和維護。 ## 文檔 `switch`...
Meta Keywords: case, break, switch, dayname, expression
-->

# C# 中的 switch 陳述式：用於條件選擇的強大工具

## 簡介
C# 中的 `switch` 陳述式是一種控制結構，用於根據變數的不同值執行不同的程式碼區塊。它提供了一種更清晰、更有組織的方法來處理多個條件，比傳統的 `if-else` 結構更易於閱讀和維護。

## 文檔
`switch` 陳述式的主要用途是檢查一個變數（通常稱為表達式）是否與多個條件（或稱為案例）匹配。當匹配時，對應的程式碼區塊將執行。這對於簡化多個條件檢查的邏輯非常有用。

### 基本語法
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
        // 當沒有匹配任何 case 時執行的程式碼
        break;
}
```

### 用法
- `expression` 是要檢查的變數。
- 每個 `case` 表示一個可能的值，當 `expression` 匹配該值時，將執行相應的程式碼。
- `break` 語句用於終止 `switch` 陳述式，防止落入下一個 `case`。
- `default` 是可選的，表示當沒有匹配的 `case` 時的處理邏輯。

## 範例
### 基本範例
以下是一個簡單的 `switch` 陳述式範例，用於根據數字顯示對應的星期幾：
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
    case 6:
        dayName = "星期六";
        break;
    case 7:
        dayName = "星期日";
        break;
    default:
        dayName = "無效的天數";
        break;
}

Console.WriteLine(dayName); // 輸出: 星期三
```

### 多個值的範例
`switch` 也可以處理多個值：
```csharp
char grade = 'B';

switch (grade)
{
    case 'A':
    case 'B':
    case 'C':
        Console.WriteLine("及格");
        break;
    case 'D':
    case 'F':
        Console.WriteLine("不及格");
        break;
    default:
        Console.WriteLine("無效的成績");
        break;
}
```

## 解釋
### 常見陷阱
- **遺漏 `break`**：如果在 `case` 之後不加 `break`，程式碼會繼續執行下一個 `case`，這可能導致意外的行為。
- **使用不當的類型**：`switch` 陳述式中的 `expression` 和 `case` 值必須是相同類型，否則會出現編譯錯誤。

### 注意事項
- `switch` 陳述式在 C# 7.0 及更高版本中還引入了模式匹配功能，可以使用更複雜的條件判斷。
- 請考慮使用 `switch` 表達式來簡化代碼，尤其是在 C# 8.0 及更高版本中。

## 總結
C# 的 `switch` 陳述式是一種有效的條件選擇工具，能夠幫助開發者更直觀地處理多個條件分支。