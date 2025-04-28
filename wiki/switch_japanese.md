<!--
Meta Description: # C#のswitch文：効率的な条件分岐の実現 ## 概要 C#の`switch`文は、複数の条件に基づいて異なる処理を実行するための制御構造です。特定の値に応じて異なるコードブロックを実行できるため、`if`文の代替として使われることが多いです。 ## ドキュメンテーション ### 目的 `sw...
Meta Keywords: case, break, switch, dayname, default
-->

# C#のswitch文：効率的な条件分岐の実現

## 概要
C#の`switch`文は、複数の条件に基づいて異なる処理を実行するための制御構造です。特定の値に応じて異なるコードブロックを実行できるため、`if`文の代替として使われることが多いです。

## ドキュメンテーション
### 目的
`switch`文は、特定の変数の値に基づいて複数の選択肢から処理を選択するために使用されます。これにより、コードの可読性が向上し、条件分岐が簡潔に表現できるようになります。

### 使用法
`switch`文の基本構造は以下の通りです。

```csharp
switch (変数)
{
    case 値1:
        // 値1に対する処理
        break;
    case 値2:
        // 値2に対する処理
        break;
    default:
        // どのcaseにも該当しない場合の処理
        break;
}
```

### 詳細
- `switch`の後には、条件に基づく変数が続きます。
- 各`case`には、変数が一致する値を指定します。
- `break`ステートメントは、`switch`文の終了を示します。これがないと、次の`case`に処理が流れてしまう「フォールスルー」が発生します。
- `default`は、どの`case`にも該当しない場合の処理を定義するために使います。

## 例
以下は、`switch`文の基本的な使用例です。

```csharp
int day = 3;
string dayName;

switch (day)
{
    case 1:
        dayName = "月曜日";
        break;
    case 2:
        dayName = "火曜日";
        break;
    case 3:
        dayName = "水曜日";
        break;
    case 4:
        dayName = "木曜日";
        break;
    case 5:
        dayName = "金曜日";
        break;
    case 6:
        dayName = "土曜日";
        break;
    case 7:
        dayName = "日曜日";
        break;
    default:
        dayName = "無効な日";
        break;
}

Console.WriteLine(dayName); // 出力: 水曜日
```

## 説明
- **共通の落とし穴**：`break`を忘れると、次の`case`が実行されるため、意図しない動作を引き起こすことがあります。
- **型の制限**：`switch`文は、整数型、文字型、列挙型、文字列型に対して使用できますが、浮動小数点型には使用できません。
- **パターンマッチング**：C# 7.0以降、`switch`文はパターンマッチングをサポートし、より複雑な条件分岐を簡潔に記述できます。

## 一文要約
C#の`switch`文は、特定の値に基づいて効率的に条件分岐を実現するための強力な制御構造です。