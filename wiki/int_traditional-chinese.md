<!--
Meta Description: # C# 中的整數類型 (int) 深入解析 ## 簡介 在 C# 中，`int` 是一種基本數據類型，用於表示整數數值。它是應用程式中最常用的數據類型之一，因為它提供了高效的數值運算和存儲。 ## 文檔 `int` 是 C# 中的整數類型，屬於值類型。它在內存中佔用 4 個字節（32 位元），可以...
Meta Keywords: int, csharp, console, writeline, 中的整數類型
-->

# C# 中的整數類型 (int) 深入解析

## 簡介
在 C# 中，`int` 是一種基本數據類型，用於表示整數數值。它是應用程式中最常用的數據類型之一，因為它提供了高效的數值運算和存儲。

## 文檔
`int` 是 C# 中的整數類型，屬於值類型。它在內存中佔用 4 個字節（32 位元），可以表示的整數範圍從 -2,147,483,648 到 2,147,483,647。`int` 在數值計算中十分常用，因為它能夠提供足夠的範圍來滿足大多數應用的需求。 

### 使用方法
在 C# 中，可以使用 `int` 來聲明變量，進行運算和控制流處理。基本的聲明語法如下：

```csharp
int myNumber = 42;
```

`int` 也可以用於數組和集合，例如：

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
```

## 範例
以下是一些 `int` 的基本使用範例：

### 基本聲明和賦值
```csharp
int age = 30;
Console.WriteLine(age); // 輸出: 30
```

### 數學運算
```csharp
int a = 10;
int b = 20;
int sum = a + b;
Console.WriteLine(sum); // 輸出: 30
```

### 使用條件語句
```csharp
int score = 85;
if (score >= 60) {
    Console.WriteLine("及格");
} else {
    Console.WriteLine("不及格");
}
```

## 解釋
使用 `int` 類型時，開發者應注意以下幾點：

1. **溢出**：如果計算結果超出 `int` 的範圍，將會發生溢出。可以使用 `checked` 關鍵字來捕獲溢出錯誤。
   ```csharp
   int result = checked(a + b); // 溢出時將拋出例外
   ```

2. **初始化**：未初始化的 `int` 變量會有預設值 `0`。開發者應根據需要進行明確初始化。

3. **與其他類型的轉換**：當 `int` 與其他數據類型（如 `float` 或 `double`）進行操作時，可能會出現隱式轉換或精度丟失的問題。

## 一句總結
`int` 是 C# 中一種常用的整數數據類型，提供高效的數值運算和存儲能力。