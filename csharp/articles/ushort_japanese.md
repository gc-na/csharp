<!--
Meta Description: # CSharpのushort型: 短整数データ型の完全ガイド ## 概要 CSharpにおける`ushort`は、0から65,535までの数値を扱うことができる16ビットの符号なし整数データ型です。この型は、メモリ効率が重要な場面で特に有用です。 ## ドキュメンテーション `ushort`は、C...
Meta Keywords: ushort, 0から65, csharp, console, writeline
-->

# CSharpのushort型: 短整数データ型の完全ガイド

## 概要
CSharpにおける`ushort`は、0から65,535までの数値を扱うことができる16ビットの符号なし整数データ型です。この型は、メモリ効率が重要な場面で特に有用です。

## ドキュメンテーション
`ushort`は、CSharpの基本データ型の一つで、次の特性を持っています。

- **範囲**: `ushort`は、0から65,535（2^16 - 1）までの整数を格納できます。
- **サイズ**: メモリ上では16ビット（2バイト）を占有します。
- **用途**: 主に、負の値を必要としないカウンターやインデックスなどに使用されます。

### 宣言と初期化
`ushort`型の変数は、次のように宣言できます。

```csharp
ushort number = 5000;
```

また、数値リテラルを使って初期化することができます。

### 演算
`ushort`型同士の演算は、通常の算術演算子を使用できます。ただし、結果が65535を超える場合は、オーバーフローが発生します。この場合、例外はスローされず、結果は0に戻ります。

## 例
以下は、`ushort`型の基本的な使用例です。

```csharp
using System;

class Program
{
    static void Main()
    {
        // ushort型の変数を宣言
        ushort a = 30000;
        ushort b = 5000;

        // 加算
        ushort sum = (ushort)(a + b);
        Console.WriteLine("合計: " + sum); // 合計: 35000

        // 減算
        ushort difference = (ushort)(a - b);
        Console.WriteLine("差: " + difference); // 差: 25000

        // オーバーフローの例
        ushort overflowExample = (ushort)(65535 + 1);
        Console.WriteLine("オーバーフロー: " + overflowExample); // オーバーフロー: 0
    }
}
```

## 説明
`ushort`型を使用する際の注意点として、以下の点があります。

- **オーバーフロー**: 計算結果が`ushort`の範囲を超える場合、オーバーフローが発生します。このとき、例外はスローされず、値は0に戻ります。オーバーフローを防ぐためには、`checked`ブロックを使用することができます。
  
```csharp
ushort result;
checked
{
    result = (ushort)(65535 + 1); // ここで例外がスローされる
}
```

- **型変換**: `ushort`型と他の数値型（例えば、`int`）との間での演算を行う場合、明示的な型変換が必要です。暗黙的な型変換は行われません。

## 一文要約
CSharpの`ushort`型は、0から65,535までの符号なし整数を扱う16ビットのデータ型で、メモリ効率を重視したプログラミングに最適です。