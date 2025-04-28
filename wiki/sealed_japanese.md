<!--
Meta Description: # C# の "sealed" キーワードについて ## 概要 C# における "sealed" キーワードは、クラスの継承を制限するために使用されます。これにより、他のクラスが sealed クラスを継承できなくなり、クラスの設計を厳密に制御できます。 ## ドキュメンテーション ### 目的 "...
Meta Keywords: sealed, public, class, キーワードは, derivedclass
-->

# C# の "sealed" キーワードについて

## 概要
C# における "sealed" キーワードは、クラスの継承を制限するために使用されます。これにより、他のクラスが sealed クラスを継承できなくなり、クラスの設計を厳密に制御できます。

## ドキュメンテーション
### 目的
"sealed" キーワードは、クラスの再利用性や拡張性を制限するために使われます。特に、設計者が特定のクラスの実装を固定したい場合に役立ちます。sealed クラスは、派生クラスを作成できないため、クラスの動作を保証することができます。

### 使用法
"sealed" キーワードは、クラス定義の前に付けて使用します。以下に基本的な構文を示します。

```csharp
sealed class クラス名
{
    // メンバーの定義
}
```

このように定義されたクラスは、他のクラスから継承することができません。

### 詳細
sealed クラスは、抽象クラスやインターフェースと組み合わせて使用されることが多いです。例えば、基底クラスが abstract である場合、派生クラスを sealed にすることで、特定の実装を固定することができます。

```csharp
public abstract class BaseClass
{
    public abstract void Display();
}

public sealed class DerivedClass : BaseClass
{
    public override void Display() 
    {
        Console.WriteLine("DerivedClass implementation.");
    }
}
```

この例では、`DerivedClass` は `BaseClass` を継承し、さらにそれ自体が sealed であるため、他のクラスは `DerivedClass` を継承できません。

## 例
以下は、sealed クラスの簡単な例です。

```csharp
public sealed class FinalClass
{
    public void ShowMessage()
    {
        Console.WriteLine("This is a sealed class.");
    }
}

// 使用例
FinalClass myClass = new FinalClass();
myClass.ShowMessage();
```

このコードでは、`FinalClass` をインスタンス化し、そのメソッドを呼び出しています。

## 説明
sealed クラスに関しての注意点として、以下の点が挙げられます。

- **継承の禁止**: sealed クラスは継承できないため、再利用性が制限されます。これを設計時に考慮する必要があります。
- **パフォーマンス向上**: sealed クラスは、JIT コンパイラ（Just-In-Time Compiler）により最適化される場合があり、パフォーマンス向上が期待できます。
- **多重継承の回避**: C# では多重継承がサポートされていないため、sealed クラスは明示的に一つのクラスのみを継承することを促進します。

## 1行要約
C# の "sealed" キーワードは、クラスの継承を禁止し、特定のクラスの設計を固定するために使用されます。