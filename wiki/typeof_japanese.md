<!--
Meta Description: # C# の typeof 演算子: 型情報を取得する方法 ## 概要 C# の `typeof` 演算子は、指定した型の Type オブジェクトを取得するための機能です。この演算子は、型に関するメタデータを取得したり、型の情報をプログラム内で動的に扱う際に非常に便利です。 ## ドキュメント `t...
Meta Keywords: typeof, type, system, csharp, 演算子は
-->

# C# の typeof 演算子: 型情報を取得する方法

## 概要
C# の `typeof` 演算子は、指定した型の Type オブジェクトを取得するための機能です。この演算子は、型に関するメタデータを取得したり、型の情報をプログラム内で動的に扱う際に非常に便利です。

## ドキュメント
`typeof` 演算子は、C# コンパイラに組み込まれた演算子であり、クラス、構造体、インターフェース、列挙型、またはデリゲート型などの型を指定して、その型に対応する `System.Type` オブジェクトを取得します。この `Type` オブジェクトには、型の名前、メソッド、プロパティ、フィールドなどの情報が含まれています。

### 使用法
`typeof` 演算子の基本的な構文は以下のようになります。

```csharp
Type typeInfo = typeof(型名);
```

ここで、`型名` は取得したい型の名前です。例えば、`int` 型の Type オブジェクトを取得するには、次のように記述します。

```csharp
Type intType = typeof(int);
```

## 例
以下は、`typeof` 演算子を使用した基本的な例です。

### 例 1: 基本的な型の使用
```csharp
using System;

class Program
{
    static void Main()
    {
        Type intType = typeof(int);
        Console.WriteLine(intType); // 出力: System.Int32
    }
}
```

### 例 2: カスタムクラスの使用
```csharp
using System;

class MyClass { }

class Program
{
    static void Main()
    {
        Type myClassType = typeof(MyClass);
        Console.WriteLine(myClassType); // 出力: Namespace.MyClass
    }
}
```

### 例 3: ジェネリック型の使用
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Type listType = typeof(List<string>);
        Console.WriteLine(listType); // 出力: System.Collections.Generic.List`1[System.String]
    }
}
```

## 説明
### 一般的な落とし穴
- **型の指定ミス**: `typeof` 演算子に指定する型名は正確である必要があります。存在しない型を指定すると、コンパイルエラーが発生します。
- **ジェネリック型の表現**: ジェネリック型を使用する場合、型パラメータは具体的な型でなければなりません。`List<T>` のように指定する必要があります。

### 追加の注意点
- `typeof` 演算子は、コンパイル時に解決されるため、動的型情報を扱う場合には `GetType()` メソッドを使用することを検討してください。
- `typeof` を使用して取得した `Type` オブジェクトは、リフレクションを利用して型の詳細情報を取得する際に役立ちます。

## 一文の要約
C# の `typeof` 演算子は、指定した型の Type オブジェクトを取得し、型に関するメタデータを扱うための基本的な手段です。