<!--
Meta Description: # C#におけるインターフェースの完全ガイド ## 概要 C#のインターフェースは、クラスや構造体が実装するべきメソッド、プロパティ、イベントの契約を定義するための重要な機能です。インターフェースを使用することで、異なるクラス間での一貫した動作を保証し、コードの再利用性を向上させます。 ## ドキュ...
Meta Keywords: public, void, ianimal, speak, class
-->

# C#におけるインターフェースの完全ガイド

## 概要
C#のインターフェースは、クラスや構造体が実装するべきメソッド、プロパティ、イベントの契約を定義するための重要な機能です。インターフェースを使用することで、異なるクラス間での一貫した動作を保証し、コードの再利用性を向上させます。

## ドキュメント
### 目的
インターフェースは、異なるクラスが同じメソッド名やプロパティ名を持つことを保証するための設計図を提供します。これにより、ポリモーフィズムを活用した柔軟なプログラミングが可能になります。

### 使用法
インターフェースは`interface`キーワードを使用して宣言します。インターフェースはメソッドやプロパティのシグネチャを含むことができますが、実際の実装は含まれません。クラスは`implements`キーワードを使用してインターフェースを実装します。

#### 基本構文
```csharp
public interface IExample
{
    void Method1();
    int Property1 { get; set; }
}
```

#### インターフェースの実装
```csharp
public class ExampleClass : IExample
{
    public void Method1()
    {
        // メソッドの実装
    }

    public int Property1 { get; set; }
}
```

## 例
以下は、C#でインターフェースを利用した基本的な例です。

```csharp
// インターフェースの定義
public interface IAnimal
{
    void Speak();
}

// インターフェースを実装するクラス
public class Dog : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("ワンワン");
    }
}

public class Cat : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("ニャー");
    }
}

// 使用例
class Program
{
    static void Main()
    {
        IAnimal myDog = new Dog();
        myDog.Speak(); // 出力: ワンワン

        IAnimal myCat = new Cat();
        myCat.Speak(); // 出力: ニャー
    }
}
```

## 解説
インターフェースを使用する際の一般的な落とし穴としては、インターフェースのメソッドを実装する際に適切なアクセス修飾子を使用しないことがあります。インターフェース内のメソッドは常に`public`でなければなりません。また、インターフェースを使用することで、異なるクラス間での依存関係を減少させることができますが、過度にインターフェースを使用すると、コードが複雑になる可能性もあるため、適切なバランスを保つことが重要です。

## 一文要約
C#のインターフェースは、クラス間での一貫性を確保し、コードの再利用性を向上させるための契約を定義する機能です。