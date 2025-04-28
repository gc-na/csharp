<!--
Meta Description: # C#における「base」キーワードの使い方 ## 概要 C#の「base」キーワードは、派生クラスから基底クラスのメンバーにアクセスするために使用されます。これにより、オーバーライドされたメソッドやプロパティにアクセスでき、基底クラスの機能を再利用することが可能になります。 ## ドキュメンテー...
Meta Keywords: base, public, console, writeline, dog
-->

# C#における「base」キーワードの使い方

## 概要
C#の「base」キーワードは、派生クラスから基底クラスのメンバーにアクセスするために使用されます。これにより、オーバーライドされたメソッドやプロパティにアクセスでき、基底クラスの機能を再利用することが可能になります。

## ドキュメンテーション
「base」キーワードは、主に次の目的で使用されます：

1. **基底クラスのメソッドの呼び出し**: 派生クラスでオーバーライドしたメソッド内から、基底クラスの同名のメソッドを呼び出すことができます。
2. **基底クラスのコンストラクタの呼び出し**: 派生クラスのコンストラクタにおいて、基底クラスの特定のコンストラクタを呼び出すことができます。
3. **プロパティのアクセス**: 基底クラスに定義されたプロパティにアクセスする際にも使用されます。

### 使用方法
```csharp
public class BaseClass
{
    public void Display()
    {
        Console.WriteLine("BaseClass Display Method");
    }

    public BaseClass(int value)
    {
        Console.WriteLine($"BaseClass Constructor with value: {value}");
    }
}

public class DerivedClass : BaseClass
{
    public DerivedClass(int value) : base(value)
    {
        Console.WriteLine("DerivedClass Constructor");
    }

    public void Show()
    {
        base.Display(); // 基底クラスのメソッドを呼び出し
    }
}
```

## 例
次の例では、基底クラスのコンストラクタとメソッドを「base」を使って呼び出す方法を示しています。

```csharp
public class Animal
{
    public Animal(string name)
    {
        Console.WriteLine($"{name} is an animal.");
    }

    public void Speak()
    {
        Console.WriteLine("Animal speaks!");
    }
}

public class Dog : Animal
{
    public Dog(string name) : base(name) // 基底クラスのコンストラクタを呼び出し
    {
        Console.WriteLine($"{name} is a dog.");
    }

    public void Bark()
    {
        base.Speak(); // 基底クラスのメソッドを呼び出し
        Console.WriteLine("Dog barks!");
    }
}

// 使用例
Dog myDog = new Dog("Buddy");
myDog.Bark();
```

## 説明
「base」キーワードを使用する際の一般的な注意点は以下の通りです：

- **オーバーライドとの組み合わせ**: 基底クラスのメソッドをオーバーライドする場合、必ずしも「base」を使用する必要はありませんが、基底クラスの実装を参照したい場合は利用します。
- **コンストラクタの呼び出し**: 派生クラスのコンストラクタで「base」で基底クラスのコンストラクタを呼び出す場合、引数の数と型を正確に指定する必要があります。
- **アクセス修飾子**: 基底クラスのメンバーがprivateである場合、派生クラスからはアクセスできないため、注意が必要です。

## 一文要約
C#における「base」キーワードは、派生クラスから基底クラスのメンバーやコンストラクタにアクセスするための重要な機能です。