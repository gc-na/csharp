<!--
Meta Description: # CSharpにおける「static」キーワードの完全ガイド ## 概要 CSharpでの「static」キーワードは、クラスやメソッド、変数に対して特定のスコープを持たせるために使用されます。これにより、インスタンスを生成せずにアクセスできるメンバーを定義することが可能になります。 ## ドキュ...
Meta Keywords: static, public, csharp, int, class
-->

# CSharpにおける「static」キーワードの完全ガイド

## 概要
CSharpでの「static」キーワードは、クラスやメソッド、変数に対して特定のスコープを持たせるために使用されます。これにより、インスタンスを生成せずにアクセスできるメンバーを定義することが可能になります。

## ドキュメンテーション
### 目的
「static」キーワードは、クラスのインスタンスに依存しないメンバーを宣言するために使用します。主に以下の用途があります：
- **静的メソッド**: インスタンスを生成せずに呼び出せるメソッド。
- **静的変数**: クラス全体で共有される変数。
- **静的クラス**: インスタンスを持たないクラス。

### 使用法
「static」はクラス、メソッド、フィールドなどの前に記述します。以下は各用途の基本的なシンタックスです：

- **静的メソッド**:
```csharp
public static void StaticMethod()
{
    // メソッドの処理
}
```

- **静的変数**:
```csharp
public static int StaticVariable;
```

- **静的クラス**:
```csharp
public static class StaticClass
{
    // クラスのメンバー
}
```

## 例
### 静的メソッドの例
```csharp
public class MathUtils
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}

// 使用方法
int result = MathUtils.Add(5, 10); // resultは15
```

### 静的変数の例
```csharp
public class Counter
{
    public static int Count = 0;

    public static void Increment()
    {
        Count++;
    }
}

// 使用方法
Counter.Increment(); // Countは1になる
```

### 静的クラスの例
```csharp
public static class Constants
{
    public const double Pi = 3.14;
}

// 使用方法
double area = Constants.Pi * radius * radius;
```

## 説明
### 一般的な落とし穴
- **インスタンスメンバーとの混同**: 静的メンバーはインスタンスメンバーから独立しているため、インスタンスメソッドから静的メソッドを呼び出す際には注意が必要です。
- **スレッドセーフ**: 静的変数はアプリケーション全体で共有されるため、マルチスレッド環境では競合状態に注意する必要があります。

### 追加の注意点
- **初期化**: 静的変数はクラスが初めて呼ばれたときに初期化されます。
- **静的コンストラクタ**: 静的メンバーの初期化を行うために、静的コンストラクタを使用できます。

## 一文要約
CSharpにおける「static」キーワードは、インスタンスを必要とせずにアクセス可能なクラスメンバーを定義するために使用される。