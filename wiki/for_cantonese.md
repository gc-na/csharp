<!--
Meta Description: # C# “for” 迴圈語句：用法及範例 ## 簡介 C# 中的 “for” 迴圈是一種控制結構，允許開發者重複執行一段程式碼，直到滿足特定條件。它是進行迭代操作的基本工具之一，特別適用於已知執行次數的情況。 ## 文檔 ### 目的 “for” 迴圈的主要目的是簡化重複執行相同程式碼的過程。透過...
Meta Keywords: csharp, int, sum, 初始化, true
-->

# C# “for” 迴圈語句：用法及範例

## 簡介
C# 中的 “for” 迴圈是一種控制結構，允許開發者重複執行一段程式碼，直到滿足特定條件。它是進行迭代操作的基本工具之一，特別適用於已知執行次數的情況。

## 文檔
### 目的
“for” 迴圈的主要目的是簡化重複執行相同程式碼的過程。透過設置初始值、條件和遞增/遞減步驟，可以輕鬆地控制迴圈的執行。

### 語法
```csharp
for (初始化; 條件; 更新)
{
    // 執行的程式碼
}
```

- **初始化**：在迴圈開始之前執行的程式碼，通常用來定義迴圈變數。
- **條件**：每次迴圈執行前檢查的布林表達式，當其為 `true` 時，迴圈將繼續執行。
- **更新**：在每次迴圈結束後執行的程式碼，通常用於更新迴圈變數的值。

### 使用範例
以下是一些 C# 中 “for” 迴圈的基本用法範例：

**範例 1：印出 1 到 5 的數字**
```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```

**範例 2：計算 0 到 10 的總和**
```csharp
int sum = 0;
for (int i = 0; i <= 10; i++)
{
    sum += i;
}
Console.WriteLine("總和：" + sum);
```

## 解釋
### 常見陷阱與注意事項
1. **迴圈無窮迴圈**：如果條件永遠為 `true`，將導致無窮迴圈。在設計迴圈時，務必確認條件會在適當時候變為 `false`。
   
2. **變數範圍**：在迴圈內部定義的變數在迴圈外部無法訪問，這可能導致意想不到的錯誤。

3. **步進值**：確保步進值的設置正確。如果步進值過大或過小，可能會導致迴圈提前結束或無窮迴圈。

4. **多重迴圈**：在使用多重 “for” 迴圈時，務必注意每個迴圈的變數名稱不同，以避免衝突。

## 一句總結
C# 的 “for” 迴圈是一種強大且靈活的控制結構，用於執行重複操作，特別適合已知迭代次數的情況。