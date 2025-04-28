<!--
Meta Description: # CSharp 中的「case」語句：用於條件控制的關鍵字 ## 概述 在 CSharp 編程語言中，「case」語句通常用於控制結構中的「switch」語句，允許根據不同的條件執行不同的代碼塊。這使得在處理多個可能值時，代碼更加簡潔與可讀。 ## 文檔 ### 目的 「case」語句的主要目的是...
Meta Keywords: case, break, dayname, switch, expression
-->

# CSharp 中的「case」語句：用於條件控制的關鍵字

## 概述
在 CSharp 編程語言中，「case」語句通常用於控制結構中的「switch」語句，允許根據不同的條件執行不同的代碼塊。這使得在處理多個可能值時，代碼更加簡潔與可讀。

## 文檔
### 目的
「case」語句的主要目的是在「switch」語句中定義各種條件，並根據變量的值選擇要執行的代碼塊。這種結構比多個「if-else」語句更易於管理，特別是在可能值較多的情況下。

### 用法
「case」語句必須與「switch」語句一起使用。基本語法如下：

```csharp
switch (expression)
{
    case constant1:
        // 當 expression 等於 constant1 時執行的代碼
        break;
    case constant2:
        // 當 expression 等於 constant2 時執行的代碼
        break;
    default:
        // 當 expression 不符合任何 case 時執行的代碼
        break;
}
```

- `expression`：要進行判斷的變量或表達式。
- `case constantN`：每個 `case` 需要一個常量值，當 `expression` 的值等於該常量時，會執行對應的代碼塊。
- `break`：用於終止當前的 `switch` 語句。如果省略，將會繼續執行下一個 `case`（稱為「fall-through」行為）。
- `default`（可選）：當所有 `case` 均不符合時執行的代碼塊。

## 示例
以下是一個用於演示「case」語句的簡單示例：

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
        dayName = "無效的日期";
        break;
}

Console.WriteLine(dayName); // 輸出：星期三
```

## 解釋
### 常見陷阱
- **缺少 `break`**：如果在某個 `case` 中忘記寫 `break`，將會導致「fall-through」行為，這意味著該 `case` 後的所有代碼也會被執行，這可能不是預期的結果。
- **重複的常量**：在同一個 `switch` 語句中，不能有相同的 `case` 常量，否則會導致編譯錯誤。
- **不支持範圍**：`case` 語句不支持範圍判斷，例如 `case 1 to 5` 是不合法的。

## 一句總結
CSharp 中的「case」語句是一種有效的條件控制方式，用於根據變量的值選擇執行的代碼塊。