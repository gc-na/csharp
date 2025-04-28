<!--
Meta Description: # C# の「catch」: 例外処理の基本 ## 概要 C#における「catch」は、例外処理のための重要なキーワードであり、tryブロック内で発生した例外を捕捉して適切に処理するために使用されます。 ## ドキュメント ### 目的 「catch」は、プログラムの実行中に発生する可能性のあるエラ...
Meta Keywords: catch, try, console, writeline, csharp
-->

# C# の「catch」: 例外処理の基本

## 概要
C#における「catch」は、例外処理のための重要なキーワードであり、tryブロック内で発生した例外を捕捉して適切に処理するために使用されます。

## ドキュメント
### 目的
「catch」は、プログラムの実行中に発生する可能性のあるエラーや例外を処理するための構文です。これにより、プログラムが異常終了するのを防ぎ、ユーザーに適切なエラーメッセージを表示することができます。

### 使用法
「catch」は、通常「try」ブロックと組み合わせて使用されます。tryブロック内で例外が発生した場合、対応するcatchブロックが実行されます。

#### 構文
```csharp
try
{
    // 例外が発生する可能性のあるコード
}
catch (例外の型 例外変数)
{
    // 例外が発生した場合の処理
}
```

## 例
以下は、簡単な例外処理の使用例です。

### 例 1: 基本的な例外処理
```csharp
try
{
    int num = int.Parse("不正な数字");
}
catch (FormatException ex)
{
    Console.WriteLine("エラー: " + ex.Message);
}
```

### 例 2: 複数のcatchブロック
```csharp
try
{
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers[5]); // IndexOutOfRangeExceptionを発生させる
}
catch (IndexOutOfRangeException)
{
    Console.WriteLine("配列のインデックスが範囲外です。");
}
catch (Exception ex)
{
    Console.WriteLine("予期しないエラー: " + ex.Message);
}
```

## 説明
### 一般的な落とし穴
- **例外を捕捉しない場合:** すべての例外を適切に捕捉しないと、プログラムが予期しない動作をする可能性があります。
- **過度な例外処理:** 不要なcatchブロックを使うと、コードが読みにくくなる場合があります。必要な例外だけを捕捉するようにしましょう。

### 補足
- **finallyブロック:** catchブロックの後にfinallyブロックを追加することで、例外が発生してもしなくても実行されるコードを記述できます。
- **多重例外処理:** 複数のcatchブロックを使用して、異なる種類の例外に対処することができます。

## 一行要約
C#の「catch」は、tryブロック内で発生した例外を捕捉し、適切に処理するための構文です。