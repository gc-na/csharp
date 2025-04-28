<!--
Meta Description: # C#における「finally」ブロックの使い方と解説 ## 概要 C#の「finally」ブロックは、例外処理の際にリソースの解放や後処理を行うために使用される構文です。try-catch文と共に使用され、例外が発生した場合でも必ず実行されるコードを定義します。 ## ドキュメンテーション 「f...
Meta Keywords: finally, try, ブロックは, における, csharp
-->

# C#における「finally」ブロックの使い方と解説

## 概要
C#の「finally」ブロックは、例外処理の際にリソースの解放や後処理を行うために使用される構文です。try-catch文と共に使用され、例外が発生した場合でも必ず実行されるコードを定義します。

## ドキュメンテーション
「finally」ブロックは、try-catch文の一部として使用され、リソースを解放するためや、必ず実行したいコードを記述するために利用されます。tryブロック内で例外が発生しても、finallyブロック内のコードは実行されます。これにより、ファイルのクローズ処理やデータベース接続の解放など、重要な後処理を確実に行うことができます。

### 使用方法
以下の基本的な構文で使用します：

```csharp
try
{
    // 例外が発生する可能性のあるコード
}
catch (Exception ex)
{
    // 例外処理
}
finally
{
    // 常に実行されるコード
}
```

## 例
以下は、C#における「finally」ブロックの基本的な使用例です。

```csharp
using System;

class Program
{
    static void Main()
    {
        FileStream fs = null;
        try
        {
            fs = new FileStream("example.txt", FileMode.Open);
            // ファイル操作
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine("ファイルが見つかりません: " + ex.Message);
        }
        finally
        {
            if (fs != null)
            {
                fs.Close(); // リソースの解放
                Console.WriteLine("ファイルストリームが閉じられました。");
            }
        }
    }
}
```

この例では、ファイルが存在しない場合の例外をキャッチし、finallyブロックでファイルストリームを閉じています。

## 説明
- **注意点**: finallyブロックは、tryブロック内で例外が発生しなかった場合でも必ず実行されます。例外が発生した場合でも、finallyブロック内のコードは実行されるため、リソースの解放処理を確実に行うことができます。
- **複数のcatchブロック**: finallyブロックは、try-catch構文において複数のcatchブロックが存在しても、常に実行されます。
- **return文との関係**: finallyブロック内でreturn文を使用すると、実行の流れが変更されることがありますが、finallyブロックは必ず実行されます。

## 一文要約
C#の「finally」ブロックは、例外処理の際に必ず実行されるコードを定義し、リソースの解放や後処理を行うために使用されます。