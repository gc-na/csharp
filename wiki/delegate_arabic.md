<!--
Meta Description: # المندوب (Delegate) في CSharp: مفهوم شامل وأمثلة عملية ## ملخص: المندوب في CSharp هو نوع بيانات يشير إلى طريقة، مما يسمح لك بتمرير طرق كوسائط، وتخزين...
Meta Keywords: المندوب, public, int, csharp, delegate
-->

# المندوب (Delegate) في CSharp: مفهوم شامل وأمثلة عملية

## ملخص:
المندوب في CSharp هو نوع بيانات يشير إلى طريقة، مما يسمح لك بتمرير طرق كوسائط، وتخزينها، واستدعائها بطريقة مرنة.

## الوثائق:
المندوب (Delegate) هو نوع خاص في CSharp يُستخدم لتخزين مرجع لطريقة معينة. يُعتبر المندوب بمثابة نوع آمن لطريقة، حيث يمكنك استخدامه لاستدعاء الطرق بشكل غير مباشر. يُستخدم عادة في حالات مثل التعامل مع الأحداث (events) أو عند الحاجة إلى تنفيذ طريقة معينة بشكل ديناميكي.

### الاستخدام:
لتعريف مندوب، يتم استخدام الكلمة المفتاحية `delegate`، يليها توقيع الطريقة. إليك كيفية تعريف واستخدام المندوب:

```csharp
// تعريف المندوب
public delegate void MyDelegate(string message);

// استخدام المندوب
public class DelegateExample
{
    public void ShowMessage(string message)
    {
        Console.WriteLine(message);
    }

    public void ExecuteDelegate()
    {
        MyDelegate del = ShowMessage;
        del("مرحبًا بكم في CSharp!");
    }
}
```

## الأمثلة:
### مثال 1: تعريف المندوب واستدعاؤه
```csharp
public delegate int MathOperation(int x, int y);

public class Calculator
{
    public int Add(int a, int b) => a + b;
    public int Subtract(int a, int b) => a - b;

    public void PerformOperation(MathOperation operation, int x, int y)
    {
        int result = operation(x, y);
        Console.WriteLine($"النتيجة: {result}");
    }
}

// الاستخدام
var calc = new Calculator();
calc.PerformOperation(calc.Add, 5, 3); // النتيجة: 8
calc.PerformOperation(calc.Subtract, 5, 3); // النتيجة: 2
```

### مثال 2: استخدام المندوب مع أحداث
```csharp
public delegate void Notify(string message);

public class EventPublisher
{
    public event Notify OnNotify;

    public void TriggerEvent()
    {
        OnNotify?.Invoke("حدث تم تفعيله!");
    }
}

// الاستخدام
var publisher = new EventPublisher();
publisher.OnNotify += (msg) => Console.WriteLine(msg);
publisher.TriggerEvent(); // حدث تم تفعيله!
```

## الشرح:
### العوائق الشائعة:
1. **عدم التحقق من القيمة null:** عند استدعاء المندوب، يجب التأكد من أنه ليس null قبل الاستدعاء لتجنب حدوث استثناء.
2. **التوقيع غير المتطابق:** يجب أن يتطابق توقيع المندوب مع التوقيع الخاص بالطريقة التي سيتم تمريرها، بما في ذلك عدد ونوع المعاملات ونوع القيمة المرجعة.
3. **المندوبات متعددة:** يمكن أن تحتوي المندوبات على عدة طرق. عند استدعاء المندوب، سيتم استدعاء جميع الطرق المرتبطة به بالترتيب.

## ملخص بنمط جملة واحدة:
المندوب في CSharp هو نوع بيانات يسمح لك بتمرير واستدعاء الطرق بطريقة مرنة وآمنة.