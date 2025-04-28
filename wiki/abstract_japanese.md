<!--
Meta Description: # C#の「abstract」キーワードについての詳細ガイド ## 概要 C#における「abstract」は、抽象クラスや抽象メソッドを定義するために使用されるキーワードであり、オブジェクト指向プログラミングの重要な概念であるポリモーフィズムを実現します。 ## ドキュメンテーション 「abstra...
Meta Keywords: abstract, radius, class, public, shape
-->

# C#の「abstract」キーワードについての詳細ガイド

## 概要
C#における「abstract」は、抽象クラスや抽象メソッドを定義するために使用されるキーワードであり、オブジェクト指向プログラミングの重要な概念であるポリモーフィズムを実現します。

## ドキュメンテーション
「abstract」キーワードは、C#プログラミング言語において、完全に実装されていないメソッドやクラスを定義するためのものです。抽象クラスは、直接インスタンス化することができず、他のクラスがそれを継承して具体的な実装を提供することを前提としています。抽象メソッドは、メソッドの署名のみを含み、実装は派生クラスで提供されます。

### 目的
- **コードの再利用性**: 抽象クラスを利用することで、共通の機能を持つクラスのベースを作成し、コードの重複を避けることができます。
- **ポリモーフィズムの実現**: 抽象クラスに基づく派生クラスは、異なる実装を持つことができ、同じインターフェースを通じて異なる動作を実現します。

### 使用方法
抽象クラスは「abstract」キーワードを使用して定義します。抽象メソッドも同様に「abstract」キーワードを使用して定義し、実装を省略します。

```csharp
abstract class Animal
{
    public abstract void Speak();  // 抽象メソッド
}

class Dog : Animal
{
    public override void Speak()  // 抽象メソッドの実装
    {
        Console.WriteLine("Woof!");
    }
}
```

## 例
以下に「abstract」を使った簡単な使用例を示します。

```csharp
// 抽象クラスの定義
abstract class Shape
{
    public abstract double Area(); // 抽象メソッド
}

// 派生クラスの定義
class Circle : Shape
{
    private double radius;

    public Circle(double radius)
    {
        this.radius = radius;
    }

    public override double Area() // 抽象メソッドの実装
    {
        return Math.PI * radius * radius;
    }
}

// 使用例
class Program
{
    static void Main(string[] args)
    {
        Shape shape = new Circle(5);
        Console.WriteLine($"Area of Circle: {shape.Area()}");
    }
}
```

## 説明
- **抽象クラスのインスタンス化**: 抽象クラスは直接インスタンス化できません。必ず派生クラスを作成し、そのクラスをインスタンス化する必要があります。
- **抽象メソッドの実装の義務**: 抽象メソッドを持つクラスは、そのメソッドをすべて派生クラスで実装しなければなりません。未実装のまま派生クラスを作成することはできません。
- **多重継承の制限**: C#では多重継承がサポートされていないため、抽象クラスは1つのクラスからのみ継承できますが、インターフェースは複数実装できます。

## 一文要約
C#の「abstract」キーワードは、抽象クラスや抽象メソッドを定義することで、オブジェクト指向プログラミングのポリモーフィズムを実現します。