<!--
Meta Description: # C# 中的 Switch 語句：使用指南與範例 ## 概要 C# 的 `switch` 語句是一種控制結構，可根據變量的值選擇執行不同的代碼區塊。它提供了一種清晰且易於維護的方式來處理多條件邏輯，特別是當有多個可能的情況需要考慮時。 ## 文檔 ### 目的 `switch` 語句的主要目的是根...
Meta Keywords: case, break, switch, dayname, default
-->

# C# 中的 Switch 語句：使用指南與範例

## 概要
C# 的 `switch` 語句是一種控制結構，可根據變量的值選擇執行不同的代碼區塊。它提供了一種清晰且易於維護的方式來處理多條件邏輯，特別是當有多個可能的情況需要考慮時。

## 文檔
### 目的
`switch` 語句的主要目的是根據一個表達式的結果來執行不同的代碼塊。這在需要根據用戶輸入或其他條件來決定程序流時特別有用。

### 使用方法
`switch` 語句的基本語法結構如下：

```csharp
switch (expression)
{
    case value1:
        // 執行代碼塊1
        break;
    case value2:
        // 執行代碼塊2
        break;
    default:
        // 默認執行代碼塊
        break;
}
```

在這段代碼中：
- `expression` 是要檢查的變量或表達式。
- `case` 語句用來匹配 `expression` 的值。
- `break` 語句用來結束 `switch` 語句的執行，防止執行到後面的 `case`。
- `default` 是可選的，當沒有匹配的 `case` 時會執行這一部分。

### 詳細說明
1. **表達式類型**：`switch` 語句的表達式可以是整數、字串或枚舉類型。
2. **隱式穿透**：如果沒有在 `case` 的代碼塊中使用 `break`，則會繼續執行後面的 `case` 代碼，這被稱為「隱式穿透」。
3. **case 標籤**：每個 `case` 標籤必須是唯一的，並且不能重複。
4. **default 標籤**：`default` 標籤不需要是最後一個，但通常會放在最後以提高可讀性。

## 範例
### 基本使用範例
以下是一個簡單的 `switch` 語句範例：

```csharp
int day = 4;
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
        dayName = "星期天";
        break;
    default:
        dayName = "無效的天數";
        break;
}

Console.WriteLine(dayName);
```

### 多個條件的範例
以下是使用 `switch` 處理多個條件的範例：

```csharp
char grade = 'B';
string result;

switch (grade)
{
    case 'A':
    case 'B':
    case 'C':
        result = "及格";
        break;
    case 'D':
    case 'F':
        result = "不及格";
        break;
    default:
        result = "無效的成績";
        break;
}

Console.WriteLine(result);
```

## 解釋
### 常見陷阱
- **隱式穿透**：在某些情況下，可能會無意中繼續執行下去，這可能會導致意外結果。為了避免這種情況，應始終在每個 `case` 的末尾使用 `break`。
- **未處理的情況**：如果沒有 `default` 標籤並且所有的 `case` 都不匹配，則不會執行任何代碼，這可能會導致錯誤或異常行為。

### 附加注意事項
- 在 C# 8.0 及更高版本中，`switch` 表達式提供了更簡潔的語法選擇，適合更複雜的情況。
- 使用 `switch` 時，對於字串比較，大小寫是敏感的。

## 一句總結
C# 的 `switch` 語句是一種強大而靈活的控制結構，能有效處理多條件邏輯，增強代碼的可讀性及維護性。