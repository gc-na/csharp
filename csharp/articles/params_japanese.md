<!--
Meta Description: # CSharpにおける「params」キーワードの使い方 ## 概要 CSharpの「params」キーワードは、メソッドに可変数の引数を渡すための機能です。この機能により、引数の数を動的に変更でき、柔軟なメソッド設計が可能になります。 ## ドキュメンテーション 「params」キーワードは、メ...
Meta Keywords: params, mymethod, numbers, public, number
-->

# CSharpにおける「params」キーワードの使い方

## 概要
CSharpの「params」キーワードは、メソッドに可変数の引数を渡すための機能です。この機能により、引数の数を動的に変更でき、柔軟なメソッド設計が可能になります。

## ドキュメンテーション
「params」キーワードは、メソッドの引数リストの最後に配置される特殊な修飾子です。このキーワードを使用すると、特定の型の配列を引数として受け取ることができ、複数の値を配列として一度に渡せます。

### 用途
- **可変引数の処理**: 一定の数の引数を受け取るメソッドではなく、引数の数が不定のメソッドを定義したい場合に便利です。
- **配列の簡素化**: 配列を直接渡すことができ、配列のインスタンス化を省略できます。

### 使用方法
```csharp
public void MyMethod(params int[] numbers)
{
    foreach (var number in numbers)
    {
        Console.WriteLine(number);
    }
}
```
この例では、`MyMethod`は整数の配列を受け取り、各整数をコンソールに出力します。

## 例
```csharp
// 基本的な使用例
public class Program
{
    public static void Main()
    {
        MyMethod(1, 2, 3);
        MyMethod(4, 5);
        MyMethod();
    }

    public static void MyMethod(params int[] numbers)
    {
        if (numbers.Length == 0)
        {
            Console.WriteLine("引数はありません。");
            return;
        }

        foreach (var number in numbers)
        {
            Console.WriteLine(number);
        }
    }
}
```
この例では、`MyMethod`を異なる数の引数で呼び出すことができ、引数がない場合でも適切に処理されます。

## 説明
「params」キーワードの使用にはいくつかの注意点があります。
- **最後の引数にのみ使用**: `params`はメソッドの引数リストの最後にのみ置くことができます。他の引数の後に置くことはできません。
- **型の一致**: `params`で指定する配列の型は、他の引数の型と一致させる必要があります。
- **配列の省略**: 引数として配列を渡さなくても、個々の値をそのまま渡すことが可能です。

## 一文の要約
CSharpの「params」キーワードは、可変数の引数をメソッドに渡すためのシンプルで強力な機能です。