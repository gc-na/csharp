<!--
Meta Description: # CSharp 中的 sizeof：用法與範例指南 ## 概述 `sizeof` 是 CSharp 中的一個關鍵字，用於取得特定數據類型在記憶體中所佔用的位元組數。這個功能對於性能優化和內存管理非常重要。 ## 文件說明 `sizeof` 關鍵字的主要目的是幫助開發者確定數據類型的大小，這在低層次...
Meta Keywords: sizeof, csharp, int, float, double
-->

# CSharp 中的 sizeof：用法與範例指南

## 概述
`sizeof` 是 CSharp 中的一個關鍵字，用於取得特定數據類型在記憶體中所佔用的位元組數。這個功能對於性能優化和內存管理非常重要。

## 文件說明
`sizeof` 關鍵字的主要目的是幫助開發者確定數據類型的大小，這在低層次的編程中尤其重要，如與非托管代碼互動或進行性能調優時。`sizeof` 只能用於已知的值類型，例如整數、浮點數和結構，而不能用於引用類型或自定義類型。

### 使用方法
使用 `sizeof` 時，需遵循以下語法：
```csharp
int size = sizeof(dataType);
```
在這裡，`dataType` 是你希望查詢大小的數據類型。例如，`sizeof(int)` 將返回 4，因為整數在 CSharp 中佔用 4 個位元組。

### 詳細說明
- `sizeof` 可以返回的數據類型包括：`int`、`float`、`double`、`char`、`bool`、`struct` 等。
- 若要使用 `sizeof` 來獲取結構體的大小，結構體必須為「已知大小」的結構體。
- 在 CSharp 中，`sizeof` 是一個編譯時運算符，這意味著它的值在編譯期間就已確定，而不是在運行時計算。

## 範例
以下是一些 `sizeof` 的基本用法範例：

```csharp
// 獲取基本數據類型的大小
int intSize = sizeof(int); // 4
float floatSize = sizeof(float); // 4
double doubleSize = sizeof(double); // 8
char charSize = sizeof(char); // 2

// 獲取結構體大小
struct MyStruct
{
    public int x;
    public float y;
}
int structSize = sizeof(MyStruct); // 8（4 + 4）
```

## 解釋
使用 `sizeof` 時，有幾個常見的陷阱和注意事項：
- 不能對引用類型（如類）使用 `sizeof`，因為它們的大小在運行時決定。
- 在使用 `sizeof` 獲取結構體大小時，必須確保所有成員都是已知大小的類型。
- 在某些情況下，結構體大小可能會因對齊要求而增加，因此實際佔用的內存可能與成員的總大小不同。

## 一句話總結
`sizeof` 是 CSharp 中用於取得數據類型在內存中佔用位元組數的關鍵字，對於性能優化和內存管理至關重要。