<!--
Meta Description: # C# 中的 "default" 關鍵字詳解 ## 概要 C# 中的 "default" 關鍵字用於簡化類型的預設值創建，特別是在泛型編程和條件運算中。它能夠返回任何類型的預設值，使得代碼更為簡潔與易讀。 ## 文檔 ### 目的 "default" 主要用於獲取某個類型的預設值。在 C# 中，預...
Meta Keywords: default, 預設值為, csharp, int, null
-->

# C# 中的 "default" 關鍵字詳解

## 概要
C# 中的 "default" 關鍵字用於簡化類型的預設值創建，特別是在泛型編程和條件運算中。它能夠返回任何類型的預設值，使得代碼更為簡潔與易讀。

## 文檔
### 目的
"default" 主要用於獲取某個類型的預設值。在 C# 中，預設值取決於變數的類型，例如：
- 對於數值類型，預設值為 0。
- 對於布林類型，預設值為 false。
- 對於引用類型，預設值為 null。

### 用法
"default" 可以用於任何類型，包括值類型和引用類型。其基本語法如下：
```csharp
default(類型名)
```
在泛型方法或類型中使用時，可以這樣寫：
```csharp
T defaultValue = default(T);
```
這樣的使用方式可以確保在不知道具體類型的情況下仍能獲取正確的預設值。

### 詳細說明
- **泛型上下文**：在泛型上下文中，使用 "default" 可以簡化預設值的獲取，並且不需要對具體類型進行編碼。
- **性能**：使用 "default" 可以避免手動初始化變數，提升代碼的性能和可維護性。

## 範例
以下是 "default" 的基本使用範例：

### 範例 1：獲取基本數據類型的預設值
```csharp
int defaultInt = default(int); // 預設值為 0
bool defaultBool = default(bool); // 預設值為 false
double defaultDouble = default(double); // 預設值為 0.0
```

### 範例 2：在泛型方法中使用
```csharp
public T GetDefaultValue<T>()
{
    return default(T);
}

// 使用範例
int defaultValue = GetDefaultValue<int>(); // returns 0
string defaultString = GetDefaultValue<string>(); // returns null
```

## 解釋
### 常見問題
- **引用類型的預設值**：如果你使用 "default" 來獲取引用類型的預設值，返回結果將是 null，這可能在某些情況下導致 NullReferenceException，因此在使用時需小心處理。
- **類型不匹配**：確保在使用 "default" 時所指定的類型必須是具體的類型或型別參數，否則將會導致編譯錯誤。

## 一行總結
C# 中的 "default" 關鍵字用於獲取任何類型的預設值，簡化代碼並提高可讀性。