<!--
Meta Description: # C#における「virtual」キーワードの完全ガイド ## 概要 C#の「virtual」キーワードは、クラスのメソッドやプロパティが派生クラスでオーバーライド可能であることを示すために使用されます。この機能により、ポリモーフィズムを実現し、オブジェクト指向プログラミングの柔軟性を高めます。 #...
Meta Keywords: virtual, public, class, void, animal
-->

# C#における「virtual」キーワードの完全ガイド

## 概要
C#の「virtual」キーワードは、クラスのメソッドやプロパティが派生クラスでオーバーライド可能であることを示すために使用されます。この機能により、ポリモーフィズムを実現し、オブジェクト指向プログラミングの柔軟性を高めます。

## ドキュメンテーション
### 目的
「virtual」キーワードは、クラスのメンバーに対して基本クラスでのデフォルトの実装を提供し、派生クラスでその実装を変更することを可能にします。これにより、クラスの設計が柔軟になり、異なる動作を持つオブジェクトを容易に作成できます。

### 使用法
「virtual」を使用するには、メソッドまたはプロパティの前にキーワードを付けます。派生クラスでは、これらのメンバーを「override」キーワードを使用してオーバーライドすることができます。

```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Base class display");
    }
}

public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Derived class display");
    }
}
```

### 詳細
- **オーバーライドの必須**: 派生クラスで「virtual」メソッドをオーバーライドする場合、「override」キーワードを使用する必要があります。
- **基底クラスの呼び出し**: オーバーライドしたメソッド内から基底クラスの実装を呼び出すことができます。
- **アクセス修飾子**: 「virtual」メンバーに対するアクセス修飾子は、派生クラスでのオーバーライドに影響を与えません。

## 例
以下は「virtual」キーワードの基本的な使用例です。

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

public class Cat : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Cat meows");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        myDog.Speak(); // 出力: Dog barks
        myCat.Speak(); // 出力: Cat meows
    }
}
```

## 説明
- **共通の落とし穴**: 「virtual」メソッドをオーバーライドしない場合、基底クラスの実装が呼び出されます。意図しない動作を避けるために、必要に応じてオーバーライドを行いましょう。
- **抽象クラスとの違い**: 「virtual」メソッドは基本クラスの実装を持ちますが、抽象メソッドは実装を持たず、必ず派生クラスでオーバーライドされる必要があります。

## 一行要約
C#の「virtual」キーワードは、クラスのメソッドやプロパティを派生クラスでオーバーライド可能にするためのキーワードです。