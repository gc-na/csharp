<!--
Meta Description: # C# 中的「as」關鍵字：安全類型轉換 ## 簡介 「as」關鍵字是 C# 中用於進行安全類型轉換的操作符。它允許開發者將一個物件轉換為另一個類型，並且在轉換失敗時不會引發異常，而是返回 null。 ## 文檔 ### 目的 「as」關鍵字的主要用途是進行類型轉換，特別是在處理可能為 null ...
Meta Keywords: null, dog, animal, targettype, csharp
-->

# C# 中的「as」關鍵字：安全類型轉換

## 簡介
「as」關鍵字是 C# 中用於進行安全類型轉換的操作符。它允許開發者將一個物件轉換為另一個類型，並且在轉換失敗時不會引發異常，而是返回 null。

## 文檔
### 目的
「as」關鍵字的主要用途是進行類型轉換，特別是在處理可能為 null 的物件時，它提供了一種安全的方式來避免類型轉換引起的例外。

### 使用方法
「as」操作符的語法如下：

```csharp
var result = obj as TargetType;
```

在這裡，`obj` 是要轉換的物件，`TargetType` 是目標類型。如果 `obj` 可以成功轉換為 `TargetType`，則 `result` 將是該類型的物件；如果轉換失敗，則 `result` 將是 null。

### 詳細信息
- 「as」操作符僅用於引用類型和可為 null 的值類型。
- 若 `TargetType` 是值類型，則必須使用 `Nullable<T>`，否則會引發編譯錯誤。
- 使用「as」操作符後，建議在使用轉換結果之前，先檢查結果是否為 null，以避免 NullReferenceException。

## 範例
### 基本用法範例
以下是使用「as」操作符的簡單範例：

```csharp
class Animal { }
class Dog : Animal { }

Animal animal = new Dog();
Dog dog = animal as Dog;

if (dog != null)
{
    Console.WriteLine("成功轉換為 Dog 類型");
}
else
{
    Console.WriteLine("轉換失敗");
}
```

### 轉換為 null 的範例
```csharp
Animal animal = new Animal();
Dog dog = animal as Dog; // 將會是 null

if (dog == null)
{
    Console.WriteLine("轉換失敗，dog 為 null");
}
```

## 解釋
### 常見陷阱
- **轉換失敗**：如果將一個類型轉換為不相關的類型，結果將是 null，而不會引發異常。這可能會導致開發者誤以為轉換成功，從而在後續代碼中產生 NullReferenceException。
- **不支持值類型**：對於值類型的轉換，必須使用可為 null 的值類型，否則將導致編譯錯誤。例如，`int` 不能直接用「as」進行轉換，但 `int?` 可以。

### 額外說明
使用「as」操作符時，應該總是與 null 檢查結合使用，以確保後續代碼的安全性。

## 一句總結
「as」關鍵字在 C# 中用於安全地進行類型轉換，若轉換失敗則返回 null，從而避免異常發生。