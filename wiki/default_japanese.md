<!--
Meta Description: # C#の「default」キーワード：基本と使い方 ## 概要 C#における「default」キーワードは、デフォルト値を取得するために使用されます。このキーワードは、特にジェネリック型やNullable型と組み合わせて、型のデフォルト値を簡単に取得する手段を提供します。 ## ドキュメント 「d...
Meta Keywords: default, int, キーワードは, csharp, getdefaultvalue
-->

# C#の「default」キーワード：基本と使い方

## 概要
C#における「default」キーワードは、デフォルト値を取得するために使用されます。このキーワードは、特にジェネリック型やNullable型と組み合わせて、型のデフォルト値を簡単に取得する手段を提供します。

## ドキュメント
「default」キーワードは、C#プログラミングにおいて、デフォルトの初期値を取得するために使用されます。特に、次のような用途があります。

- **ジェネリック型のデフォルト値**: ジェネリック型を使用する際に、型のデフォルト値を取得するために使用します。
- **Nullable型の初期化**: Nullable型の変数を初期化する際に、デフォルト値を取得できます。

### 使用方法
「default」キーワードの基本的な構文は以下の通りです。

```csharp
default(型名)
```

ここで、「型名」は、デフォルト値を取得したい型を指定します。

デフォルト値は以下のように定義されます：
- 数値型（int、floatなど）の場合は0
- bool型の場合はfalse
- 参照型の場合はnull
- 値型構造体の場合は、その構造体のフィールドがすべてゼロ初期化された状態

## 例
以下に「default」キーワードの基本的な使用例を示します。

### 例1: ジェネリック型のデフォルト値取得
```csharp
public T GetDefaultValue<T>()
{
    return default(T);
}

// 使用例
var intDefault = GetDefaultValue<int>(); // intDefaultは0
var stringDefault = GetDefaultValue<string>(); // stringDefaultはnull
```

### 例2: Nullable型の初期化
```csharp
int? nullableInt = default(int?); // nullableIntはnull
```

## 説明
「default」キーワードを使用する際の一般的な落とし穴や注意点は以下の通りです。

- **型の明示的な指定**: ジェネリックメソッドを使用する際、型を明示的に指定しないと、期待するデフォルト値が得られない場合があります。
- **Nullable型の理解**: Nullable型を使用する場合、デフォルト値は常にnullであることを理解しておく必要があります。これにより、Nullable型の変数が意図しない状態になることを防ぎます。

## 一文要約
C#の「default」キーワードは、型に応じたデフォルト値を簡単に取得するための便利な機能です。