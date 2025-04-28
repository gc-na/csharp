<!--
Meta Description: # C# 委派 (delegate) 的完全指南 ## 概述 在 C# 中，委派（delegate）是一種類型安全的函數指標，可以代表對某個方法的引用。委派允許將方法作為參數傳遞，並支持事件和回調的實現。 ## 文件說明 委派的主要目的是為了提供一種靈活的方式來調用方法。它們可以用來封裝方法，並且可...
Meta Keywords: public, int, process, delegate, csharp
-->

# C# 委派 (delegate) 的完全指南

## 概述
在 C# 中，委派（delegate）是一種類型安全的函數指標，可以代表對某個方法的引用。委派允許將方法作為參數傳遞，並支持事件和回調的實現。

## 文件說明
委派的主要目的是為了提供一種靈活的方式來調用方法。它們可以用來封裝方法，並且可以在運行時動態選擇要調用的方法。委派在事件處理和異步編程中尤為重要，因為它們允許程式對方法的調用進行封裝和傳遞。

### 委派的定義
在 C# 中，可以使用以下語法來定義委派：

```csharp
public delegate 返回類型 委派名稱(參數類型 參數名稱);
```

### 使用方式
一旦定義了委派，可以通過以下步驟使用它：

1. 創建委派的實例，並將其指向特定的方法。
2. 使用委派來調用方法。

### 委派的細節
- 委派可以鏈接多個方法，稱為多播委派。
- 委派的參數類型和返回類型必須與其所代表的方法相匹配。
- 委派可以用於事件處理，通常通過事件來促發委派。

## 示例
以下是一些基本使用委派的示例：

### 定義和實例化委派

```csharp
// 定義委派
public delegate int Operation(int x, int y);

// 方法
public static int Add(int a, int b)
{
    return a + b;
}

// 使用
Operation op = Add;
int result = op(5, 3);  // result 將為 8
```

### 多播委派

```csharp
public delegate void Notify();  // 定義委派

public class Process
{
    public event Notify ProcessCompleted;  // 事件

    public void StartProcess()
    {
        // 處理過程...
        OnProcessCompleted();
    }

    protected virtual void OnProcessCompleted()
    {
        ProcessCompleted?.Invoke();  // 調用所有註冊的處理程序
    }
}

// 使用範例
Process process = new Process();
process.ProcessCompleted += () => Console.WriteLine("Process Completed!");
process.StartProcess();
```

## 解釋
使用委派時，需要注意以下幾點：

- **參數和返回類型**：確保委派的參數和返回類型與所調用的方法相匹配，否則將會引發編譯錯誤。
- **多播委派的返回值**：多播委派只返回最後一個方法的返回值，這可能會導致一些混淆。
- **空引用檢查**：在調用委派之前，應始終檢查是否為 `null`，以避免 `NullReferenceException`。

## 總結
C# 中的委派是一種強大且靈活的工具，用於方法的封裝和動態調用，特別是在事件處理和回調場景中。