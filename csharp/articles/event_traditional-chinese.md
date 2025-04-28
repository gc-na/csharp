<!--
Meta Description: # C# 事件(Event) 完全指南：理解與實作 ## 摘要 在C#中，事件(Event)是一種用於處理應用程式中的異步操作或狀態變化的強大工具。它允許物件通知其他物件特定情況的發生，從而提供了一種簡單的方式來實現事件驅動的程式設計。 ## 文件說明 事件是C#中的一種特殊類型的委託，通常用於實現...
Meta Keywords: public, void, eventargs, event, class
-->

# C# 事件(Event) 完全指南：理解與實作

## 摘要
在C#中，事件(Event)是一種用於處理應用程式中的異步操作或狀態變化的強大工具。它允許物件通知其他物件特定情況的發生，從而提供了一種簡單的方式來實現事件驅動的程式設計。

## 文件說明
事件是C#中的一種特殊類型的委託，通常用於實現觀察者模式。它們允許一個物件（發佈者）在狀態發生變化時通知其他物件（訂閱者）。事件在用戶界面應用、遊戲開發和任何需要異步響應的場景中都非常有用。

### 目的
- 提供一種解耦的方式來處理物件之間的交互。
- 促進事件驅動程式設計，讓開發者能夠輕鬆管理程序流。

### 使用方法
在C#中，定義事件時，通常需要以下步驟：
1. 定義一個委託，該委託將用於描述事件的處理方法。
2. 在類中定義事件，並使用該委託類型。
3. 提供方法來觸發事件。
4. 讓其他類別訂閱事件，並實現對事件的處理。

### 事件的定義範例
```csharp
public delegate void EventHandler(object sender, EventArgs e);

public class SampleClass
{
    public event EventHandler SampleEvent;

    protected virtual void OnSampleEvent(EventArgs e)
    {
        SampleEvent?.Invoke(this, e);
    }

    public void TriggerEvent()
    {
        OnSampleEvent(EventArgs.Empty);
    }
}
```

## 範例
以下是如何使用事件的基本範例：

```csharp
public class Publisher
{
    public event EventHandler Notify;

    public void RaiseEvent()
    {
        Notify?.Invoke(this, EventArgs.Empty);
    }
}

public class Subscriber
{
    public void OnNotify(object sender, EventArgs e)
    {
        Console.WriteLine("事件已觸發!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Publisher pub = new Publisher();
        Subscriber sub = new Subscriber();

        pub.Notify += sub.OnNotify; // 訂閱事件
        pub.RaiseEvent(); // 觸發事件
    }
}
```

## 解釋
- **常見陷阱**：如果沒有檢查事件是否為null（使用`?.Invoke`），可能會導致`NullReferenceException`。
- **解除訂閱**：在不需要再接收事件通知時，應該適當地解除訂閱，以避免內存洩漏。
- **多播委託**：事件可以有多個訂閱者，當事件被觸發時，所有訂閱的處理方法都會被執行。

## 一行總結
C#中的事件提供了一種簡單而有效的方式來實現物件之間的通知和交互，特別是在事件驅動的應用程式中。