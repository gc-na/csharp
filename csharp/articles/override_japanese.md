<!--
Meta Description: # C#における「override」キーワードの詳細ガイド ## 概要 C#における「override」キーワードは、基底クラスから継承したメソッドの実装を派生クラスで再定義するために使用されます。この機能により、オブジェクト指向プログラミングのポリモーフィズムを実現し、より柔軟で拡張性のあるコード...
Meta Keywords: public, override, class, void, virtual
-->

# C#における「override」キーワードの詳細ガイド

## 概要
C#における「override」キーワードは、基底クラスから継承したメソッドの実装を派生クラスで再定義するために使用されます。この機能により、オブジェクト指向プログラミングのポリモーフィズムを実現し、より柔軟で拡張性のあるコードを書くことができます。

## ドキュメント
### 目的
「override」キーワードは、基底クラスのメソッドを派生クラスでオーバーライドするために使用されます。これにより、基底クラスのメソッドの動作を変更することができます。

### 使用法
「override」は、基底クラスのメソッドが「virtual」または「abstract」として定義されている必要があります。派生クラスで「override」を使ってメソッドを再定義する際には、次の構文を使用します。

```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("BaseClassのDisplayメソッド");
    }
}

public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("DerivedClassのDisplayメソッド");
    }
}
```

### 詳細
- **基底クラスのメソッドの定義**: 基底クラスでメソッドを「virtual」または「abstract」として定義する必要があります。
- **派生クラスでのオーバーライド**: 派生クラスで「override」キーワードを使用することで、基底クラスのメソッドの実装を変更できます。
- **呼び出し**: オーバーライドされたメソッドは、派生クラスのインスタンスを通じて呼び出されます。

## 例
以下は「override」の基本的な使用例です。

```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak(); // "Dog barks" と表示される
    }
}
```

## 説明
- **共通の落とし穴**: 基底クラスのメソッドが「virtual」または「abstract」として定義されていない場合、オーバーライドはできません。
- **メソッドのシグネチャ**: オーバーライドするメソッドは、基底クラスのメソッドと同じシグネチャを持つ必要があります。
- **baseキーワードの使用**: 基底クラスのメソッドを呼び出したい場合は、「base」キーワードを使用できます。

```csharp
public class DerivedClass : BaseClass
{
    public override void Display()
    {
        base.Display(); // 基底クラスのDisplayメソッドを呼び出す
        Console.WriteLine("DerivedClassのDisplayメソッド");
    }
}
```

## 1行要約
C#の「override」キーワードは、基底クラスのメソッドを派生クラスで再定義するために使用され、ポリモーフィズムを実現します。