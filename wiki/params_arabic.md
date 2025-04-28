<!--
Meta Description: # استخدام "params" في لغة C# ## ملخص تُستخدم كلمة "params" في لغة C# لتسهيل تمرير مجموعة من القيم إلى طريقة (function) معينة، مما يسمح بمرونة أكبر عند...
Meta Keywords: params, المعطيات, استخدام, csharp, public
-->

# استخدام "params" في لغة C#

## ملخص
تُستخدم كلمة "params" في لغة C# لتسهيل تمرير مجموعة من القيم إلى طريقة (function) معينة، مما يسمح بمرونة أكبر عند التعامل مع المعطيات.

## الوثائق
تعتبر كلمة "params" ميزة قوية في C# تتيح لك إرسال عدد متغير من المعطيات إلى دالة واحدة. يمكن أن تكون هذه المعطيات من نوع واحد فقط، مما يسمح لك بتمرير مصفوفة أو مجموعة من القيم دون الحاجة لإنشاء مصفوفة بشكل صريح.

### الغرض
الغرض من استخدام "params" هو تبسيط الكود وزيادة قابليته للقراءة، حيث يمكنك استدعاء دالة مع عدد غير محدود من المعطيات من نفس النوع.

### الاستخدام
لإعلان دالة باستخدام "params"، يجب وضعها كآخر معطى في قائمة المعطيات. على سبيل المثال:

```csharp
public void PrintNumbers(params int[] numbers)
{
    foreach (var number in numbers)
    {
        Console.WriteLine(number);
    }
}
```

في هذا المثال، يمكن استدعاء الدالة `PrintNumbers` بتمرير أي عدد من القيم الصحيحة:

```csharp
PrintNumbers(1, 2, 3, 4);
PrintNumbers(5, 6);
```

## الأمثلة
### مثال 1: استخدام "params" مع أرقام صحيحة
```csharp
public class Example
{
    public void DisplayValues(params int[] values)
    {
        foreach (var value in values)
        {
            Console.WriteLine(value);
        }
    }
}

// استدعاء الدالة
Example example = new Example();
example.DisplayValues(10, 20, 30);
```

### مثال 2: استخدام "params" مع سلاسل نصية
```csharp
public class StringExample
{
    public void ConcatenateStrings(params string[] strings)
    {
        string result = string.Join(", ", strings);
        Console.WriteLine(result);
    }
}

// استدعاء الدالة
StringExample stringExample = new StringExample();
stringExample.ConcatenateStrings("Hello", "World", "CSharp");
```

## الشرح
### الأخطاء الشائعة
- **عدم وضع "params" في آخر المعطيات**: يجب أن تكون كلمة "params" دائمًا كآخر معطى في دالتك، وإذا وضعتها في مكان آخر، ستحصل على خطأ في الترجمة.
- **عدم توافق الأنواع**: لا يمكنك استخدام "params" مع أنواع مختلفة في نفس المصفوفة. جميع المعطيات يجب أن تكون من نفس النوع المحدد.

### ملاحظات إضافية
- يمكن استخدام "params" مع الأنواع القابلة للتعديل (reference types) مثل الكائنات (objects) والسلاسل النصية (strings) أو مع الأنواع القابلة للتعديل (value types) مثل الأعداد الصحيحة (integers).
- يمكنك تمرير مصفوفة موجودة بالفعل إلى الدالة التي تحتوي على "params"، مما يجعله مريحًا للغاية.

## ملخص جملة واحدة
تُستخدم كلمة "params" في C# لتسهيل تمرير عدد متغير من المعطيات إلى دالة واحدة، مما يجعل الكود أكثر مرونة وقابلية للقراءة.