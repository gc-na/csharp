<!--
Meta Description: # C# 中的 "break" 語句：用法與範例 ## 概述 "break" 是 C# 編程語言中的一個關鍵字，用於退出迴圈或 switch 語句。它可以幫助開發者控制程式的流程，避免不必要的迴圈執行或分支。 ## 文檔 ### 目的 "break" 語句的主要目的是立即終止當前的迴圈（如 for、...
Meta Keywords: break, switch, case, console, writeline
-->

# C# 中的 "break" 語句：用法與範例

## 概述
"break" 是 C# 編程語言中的一個關鍵字，用於退出迴圈或 switch 語句。它可以幫助開發者控制程式的流程，避免不必要的迴圈執行或分支。

## 文檔
### 目的
"break" 語句的主要目的是立即終止當前的迴圈（如 for、foreach、while 或 do-while）或 switch 語句，並將控制權轉移到迴圈或 switch 語句之後的第一行程式碼。

### 用法
在 C# 中，"break" 可以在任何支援迴圈或 switch 語句的地方使用。當 "break" 被執行時，控制權會跳出當前程式碼塊，繼續執行後續的程式碼。

### 詳細說明
- **迴圈中的使用**：當在迴圈內部使用 "break" 時，迴圈會被立即終止。
- **switch 語句中的使用**：在 switch 語句中，"break" 用於終止 case 的執行，防止 "fall-through" 行為。
- "break" 語句不返回任何值，僅僅用作控制流的指令。

## 範例
### 1. 在 for 迴圈中使用 "break"
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // 當 i 等於 5 時，終止迴圈
    }
    Console.WriteLine(i);
}
```
輸出：
```
0
1
2
3
4
```

### 2. 在 switch 語句中使用 "break"
```csharp
int day = 3;
switch (day)
{
    case 1:
        Console.WriteLine("星期一");
        break;
    case 2:
        Console.WriteLine("星期二");
        break;
    case 3:
        Console.WriteLine("星期三");
        break; // 終止此 case，避免執行後面的 case
    default:
        Console.WriteLine("無效的日子");
        break;
}
```
輸出：
```
星期三
```

## 說明
- **常見問題**：在迴圈中忘記使用 "break" 可能導致無限迴圈，這會使程序陷入死循環。
- **注意事項**：在 switch 語句中，如果沒有使用 "break"，控制會進入下一個 case，這可能不是預期的行為。

## 一句總結
"break" 語句在 C# 中用於立即終止迴圈或 switch 語句的執行，幫助開發者有效控制程式流程。