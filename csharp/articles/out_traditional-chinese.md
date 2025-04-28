<!--
Meta Description: # C# 的 "out" 關鍵字詳細解析 ## 摘要 在 C# 中，`out` 關鍵字用於方法參數，以允許方法返回多個值。這是通過參考參數來實現的，能夠有效地將值從方法傳遞回調用者。 ## 文檔 `out` 關鍵字主要用於方法的參數列表中，讓開發者能夠傳遞參數的引用，而不是值。這樣可以讓方法在執行過...
Meta Keywords: out, int, sum, product, csharp
-->

# C# 的 "out" 關鍵字詳細解析

## 摘要
在 C# 中，`out` 關鍵字用於方法參數，以允許方法返回多個值。這是通過參考參數來實現的，能夠有效地將值從方法傳遞回調用者。

## 文檔
`out` 關鍵字主要用於方法的參數列表中，讓開發者能夠傳遞參數的引用，而不是值。這樣可以讓方法在執行過程中修改這些參數的值，並將其返回給調用者。`out` 參數在方法內部必須被初始化，否則編譯器會報錯。使用 `out` 的主要目的包括：
- 返回多個值
- 提高性能，因為避免了不必要的數據複製

基本語法如下：
```csharp
void 方法名稱(out 參數類型 參數名稱)
```

### 使用方式
在聲明方法時，使用 `out` 關鍵字來定義一個或多個輸出參數。以下是聲明和調用方法的示例：

```csharp
public void GetValues(out int a, out int b)
{
    a = 10;
    b = 20;
}

// 調用方法
GetValues(out int x, out int y);
```

在這個例子中，`GetValues` 方法使用了 `out` 參數 `a` 和 `b`，並在方法內部給這些參數賦值。調用該方法後，變量 `x` 和 `y` 將分別獲得值 10 和 20。

## 示例
以下是幾個 `out` 關鍵字的基本使用示例：

### 示例 1: 簡單的 `out` 使用
```csharp
public void GetCoordinates(out double x, out double y)
{
    x = 5.0;
    y = 10.0;
}

GetCoordinates(out double coordX, out double coordY);
Console.WriteLine($"X: {coordX}, Y: {coordY}"); // 輸出：X: 5.0, Y: 10.0
```

### 示例 2: 使用 `out` 的計算
```csharp
public void Calculate(out int sum, out int product)
{
    sum = 0;
    product = 1;
    for (int i = 1; i <= 5; i++)
    {
        sum += i;
        product *= i;
    }
}

Calculate(out int total, out int totalProduct);
Console.WriteLine($"Sum: {total}, Product: {totalProduct}"); // 輸出：Sum: 15, Product: 120
```

## 解釋
使用 `out` 參數時，開發者需要注意以下幾點：
1. **必須初始化**：在方法內部，所有的 `out` 參數都必須被賦值，否則將產生編譯錯誤。
2. **不需初始化**：調用方法時，傳入的變量不需要先初始化，因為方法內部會賦值。
3. **性能考量**：雖然 `out` 提供了一種方便的方式來返回多個值，但在某些情況下，使用元組或類來組合返回值可能更具可讀性和維護性。

## 一句話總結
C# 的 `out` 關鍵字允許方法通過參考參數返回多個值，增強了方法的靈活性和性能。