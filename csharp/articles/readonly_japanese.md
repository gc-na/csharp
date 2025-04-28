<!--
Meta Description: # CSharpにおけるreadonlyキーワードの詳細ガイド ## 概要 CSharpの`readonly`キーワードは、フィールドの値を初期化後に変更できないことを保証するために使用されます。これにより、オブジェクトの不変性を保ちながら、安全なプログラミングを促進します。 ## ドキュメント `...
Meta Keywords: readonly, public, circle, radius, double
-->

# CSharpにおけるreadonlyキーワードの詳細ガイド

## 概要
CSharpの`readonly`キーワードは、フィールドの値を初期化後に変更できないことを保証するために使用されます。これにより、オブジェクトの不変性を保ちながら、安全なプログラミングを促進します。

## ドキュメント
`readonly`修飾子は、クラスのフィールドに適用され、フィールドがコンストラクタ内またはフィールド宣言時にのみ初期化できることを示します。このキーワードを使用することで、オブジェクトの状態が予期せず変更されるリスクを軽減し、コードの可読性とメンテナンス性を向上させます。

### 使用方法
- `readonly`は、フィールド宣言の前に配置します。
- `readonly`フィールドは、インスタンス化後に再代入できませんが、コンストラクタ内では値を設定できます。

```csharp
public class ExampleClass
{
    public readonly int ReadOnlyField;

    public ExampleClass(int value)
    {
        ReadOnlyField = value; // 初期化時に設定
    }
}
```

## 例
以下に`readonly`の基本的な使用例を示します。

```csharp
public class Circle
{
    public readonly double Pi = 3.14;

    public Circle(double radius)
    {
        Radius = radius;
    }

    public double Radius { get; }
    
    public double GetArea()
    {
        return Pi * Radius * Radius; // Piは変更不可
    }
}

// 使用例
Circle circle = new Circle(5);
Console.WriteLine(circle.GetArea()); // 78.5
```

## 説明
`readonly`フィールドにはいくつかの注意点があります。

1. **変更不可**: `readonly`フィールドは、オブジェクトが作成された後に変更できません。これにより、意図しない変更から保護されます。
2. **コンストラクタ内での初期化**: 初期化は必ずコンストラクタ内で行う必要があります。クラスのインスタンスが生成されると、そのフィールドの値は固定されます。
3. **配列やオブジェクトの参照**: `readonly`は参照型のフィールドに対しても適用されます。つまり、フィールド自体の参照は変更できませんが、参照先のオブジェクトの内容は変更可能です。

## 一文要約
CSharpの`readonly`キーワードは、フィールドの不変性を保ち、安全で信頼性の高いコードを書くための重要な機能です。