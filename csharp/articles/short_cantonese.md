<!--
Meta Description: # CSharp 中的 "short" 數據類型：簡介及使用指南 ## 概要 在 CSharp 程式語言中，`short` 是一種整數數據類型，用於儲存範圍較小的整數值，通常用於節省記憶體空間。 ## 文檔 `short` 是 CSharp 中的一種值類型，表示 16 位元的有符號整數。它的數值範圍...
Meta Keywords: short, csharp, number, 768, 767
-->

# CSharp 中的 "short" 數據類型：簡介及使用指南

## 概要
在 CSharp 程式語言中，`short` 是一種整數數據類型，用於儲存範圍較小的整數值，通常用於節省記憶體空間。

## 文檔
`short` 是 CSharp 中的一種值類型，表示 16 位元的有符號整數。它的數值範圍為 -32,768 到 32,767。由於其佔用的記憶體較小，`short` 常用於需要大量整數型資料的應用程式，特別是在數據量較大時，可以有效減少記憶體的使用。

### 用法
在 CSharp 中，您可以使用 `short` 關鍵字來宣告變數。以下是其基本語法：

```csharp
short myShortVariable;
```

您可以將整數值賦值給 `short` 變數，前提是這些值在其範圍內。

## 範例
以下是一些基本的 `short` 使用範例：

```csharp
// 宣告一個 short 變數並賦值
short number = 10000;

// 輸出變數的值
Console.WriteLine(number);

// 使用 short 進行運算
short sum = (short)(number + 2000);
Console.WriteLine(sum);
```

## 解釋
雖然 `short` 是一個方便的數據類型，但在使用時需要注意以下幾點：

1. **範圍限制**：如果您嘗試將超出 -32,768 到 32,767 範圍的值賦給 `short` 變數，將會引發溢出錯誤。
   
2. **類型轉換**：在進行數學運算時，`short` 可能會自動提升為 `int`，因此在運算後需要將結果轉回 `short`，如上例所示。

3. **使用場景**：儘管 `short` 在某些情況下是合適的，但在處理需要更大範圍的數值時，建議使用 `int` 或 `long`。

## 一句總結
`short` 是 CSharp 中一種佔用較小記憶體的整數數據類型，適合用於儲存範圍較小的整數值。