<!--
Meta Description: # CSharp 中的 "default" 關鍵字：完整指南 ## 概述 在 CSharp 中，`default` 關鍵字用於獲取某種類型的預設值。這在使用泛型或當需要初始化變數而不想指定具體值時特別有用。 ## 文檔 `default` 關鍵字的主要目的在於為某個類型返回其預設值。這對於值類型和引...
Meta Keywords: default, csharp, null, int, string
-->

# CSharp 中的 "default" 關鍵字：完整指南

## 概述
在 CSharp 中，`default` 關鍵字用於獲取某種類型的預設值。這在使用泛型或當需要初始化變數而不想指定具體值時特別有用。

## 文檔
`default` 關鍵字的主要目的在於為某個類型返回其預設值。這對於值類型和引用類型的行為有所不同：對於值類型，`default` 返回該類型的零值（例如，整數的預設值是 0，布爾值是 false）；而對於引用類型，`default` 返回 `null`。

### 用法
`default` 可以用於任何類型，包括：
- 值類型（如 `int`, `float`, `bool` 等）
- 參考類型（如 `string`, 自訂類別等）
- 泛型類型

以下是基本語法：
```csharp
T defaultValue = default(T);
```
在這裡，`T` 是任何有效的類型。

## 示例
以下是幾個 `default` 關鍵字的基本使用示例：

### 示例 1：值類型
```csharp
int defaultInt = default(int); // defaultInt 將是 0
bool defaultBool = default(bool); // defaultBool 將是 false
```

### 示例 2：引用類型
```csharp
string defaultString = default(string); // defaultString 將是 null
MyClass defaultObject = default(MyClass); // defaultObject 將是 null
```

### 示例 3：泛型
```csharp
public T GetDefaultValue<T>()
{
    return default(T);
}

// 使用泛型方法
int myInt = GetDefaultValue<int>(); // myInt 將是 0
string myString = GetDefaultValue<string>(); // myString 將是 null
```

## 解釋
使用 `default` 時要注意以下幾點：
- 對於值類型，`default` 提供了類型的零值，這在初始化變數時非常方便。
- 對於引用類型，`default` 返回 `null`，這可能在某些情況下導致 `NullReferenceException`，因此在使用前應確認變數是否為 `null`。
- 在泛型上下文中，使用 `default` 可以避免寫出冗長的初始化代碼。

## 總結
`default` 關鍵字在 CSharp 中用於獲取類型的預設值，對於值類型返回零值，對於引用類型返回 `null`，使得類型初始化變得簡單高效。