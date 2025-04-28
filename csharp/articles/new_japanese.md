<!--
Meta Description: # C# における "new" キーワードの使い方 ## 概要 C# の "new" キーワードは、オブジェクトのインスタンスを作成するために使用されます。また、オーバーライドされたメソッドやプロパティを隠すためにも用いられます。 ## ドキュメント ### 目的 "new" キーワードの主な目的は...
Meta Keywords: new, public, class, display, person
-->

# C# における "new" キーワードの使い方

## 概要
C# の "new" キーワードは、オブジェクトのインスタンスを作成するために使用されます。また、オーバーライドされたメソッドやプロパティを隠すためにも用いられます。

## ドキュメント
### 目的
"new" キーワードの主な目的は、クラスや構造体の新しいインスタンスを生成することです。これにより、メモリに新しいオブジェクトが割り当てられ、プログラム内で使用できるようになります。また、既存のメンバーを隠すためにも使用されます。

### 使用法
以下のように "new" を使ってオブジェクトを生成します。

```csharp
class MyClass
{
    public int Value { get; set; }
}

MyClass myObject = new MyClass();
```

このコードでは、`MyClass` の新しいインスタンスが作成され、`myObject` という変数に格納されます。

### 詳細
- **オブジェクトの生成**: "new"を使うことで、クラスのコンストラクタが呼び出され、必要な初期化が行われます。
- **メンバーの隠蔽**: "new" キーワードは、親クラスに存在するメンバーを隠すためにも使用できます。例えば、以下のように定義します。

```csharp
class BaseClass
{
    public void Display()
    {
        Console.WriteLine("BaseClass Display");
    }
}

class DerivedClass : BaseClass
{
    public new void Display()
    {
        Console.WriteLine("DerivedClass Display");
    }
}
```

この場合、`DerivedClass` の `Display` メソッドは `BaseClass` の `Display` メソッドを隠します。

## 例
### 基本的な使用例
```csharp
class Person
{
    public string Name { get; set; }

    public Person(string name)
    {
        Name = name;
    }
}

// インスタンスの生成
Person person = new Person("山田太郎");
Console.WriteLine(person.Name);  // 出力: 山田太郎
```

### メンバーの隠蔽の例
```csharp
class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

class Dog : Animal
{
    public new void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

Animal myDog = new Dog();
myDog.Speak();  // 出力: Animal speaks
```

## 説明
"new" キーワードを使用する際の注意点として、メソッドの隠蔽があるため、親クラスのメソッドを呼び出す際には注意が必要です。隠蔽されたメソッドは、親クラスの参照を通じて呼び出すことができないため、オーバーライドを使用するケースと異なります。

## 一文要約
C# における "new" キーワードは、オブジェクトのインスタンスを作成し、メンバーを隠すために使用される重要な機能です。