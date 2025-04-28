<!--
Meta Description: # C# の「case」文: スイッチ文の条件分岐を活用する方法 ## 概要 C# の「case」文は、`switch` 文の一部として使用され、特定の値に基づいて異なるコードブロックを実行するための条件分岐を提供します。これにより、複雑な条件分岐を簡潔に記述することが可能になります。 ## ドキュ...
Meta Keywords: case, break, switch, console, writeline
-->

# C# の「case」文: スイッチ文の条件分岐を活用する方法

## 概要
C# の「case」文は、`switch` 文の一部として使用され、特定の値に基づいて異なるコードブロックを実行するための条件分岐を提供します。これにより、複雑な条件分岐を簡潔に記述することが可能になります。

## ドキュメント
### 目的
`case` 文は、`switch` ステートメント内で特定の値に一致するコードの実行を制御します。これにより、条件が多い場合に `if-else` 文を使用するよりも可読性が向上し、コードのメンテナンスが容易になります。

### 使用法
`case` 文は `switch` 文と共に使用され、以下の構文で記述されます。

```csharp
switch (式)
{
    case 値1:
        // 値1と一致する場合の処理
        break;
    case 値2:
        // 値2と一致する場合の処理
        break;
    default:
        // どのケースにも一致しない場合の処理
        break;
}
```

- `式`: 評価される値。
- `値`: `式` と比較される各ケースの値。
- `break`: 各ケースの処理が完了した後に `switch` 文を終了します。
- `default`: どのケースにも一致しない場合に実行されるコード。

## 例
以下は、`case` 文を使用した基本的な例です。

```csharp
int number = 2;

switch (number)
{
    case 1:
        Console.WriteLine("1が選ばれました。");
        break;
    case 2:
        Console.WriteLine("2が選ばれました。");
        break;
    case 3:
        Console.WriteLine("3が選ばれました。");
        break;
    default:
        Console.WriteLine("1から3のいずれでもありません。");
        break;
}
```

この例では、`number` の値が `2` のため、「2が選ばれました。」が出力されます。

## 説明
- **共通の落とし穴**: `switch` 文の各ケースに `break` 文を忘れると、次のケースのコードが実行されるフォールスルーが発生します。これを避けるために、各ケースに必ず `break` を追加することが重要です。
- **型の一致**: `switch` 文では、整数、文字列、列挙型などの値を使用できますが、すべてのケースの型は一致している必要があります。
- **複数の値の処理**: 一つのケースで複数の値を処理することも可能です。カンマで区切って複数の値を指定できます。

```csharp
switch (day)
{
    case "月曜日":
    case "火曜日":
    case "水曜日":
        Console.WriteLine("平日です。");
        break;
    case "土曜日":
    case "日曜日":
        Console.WriteLine("週末です。");
        break;
    default:
        Console.WriteLine("無効な日です。");
        break;
}
```

## 一文要約
C# の「case」文は、`switch` 文の中で特定の値に基づいて異なる処理を行うための強力な条件分岐機能です。