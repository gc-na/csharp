<!--
Meta Description: # استخدام الكلمة المحجوزة "sealed" في CSharp ## ملخص الكلمة المحجوزة "sealed" في CSharp تُستخدم لتحديد أن الفئة لا يمكن وراثتها. تعتبر هذه الكلمة مفيد...
Meta Keywords: sealed, public, csharp, class, display
-->

# استخدام الكلمة المحجوزة "sealed" في CSharp

## ملخص
الكلمة المحجوزة "sealed" في CSharp تُستخدم لتحديد أن الفئة لا يمكن وراثتها. تعتبر هذه الكلمة مفيدة عندما تريد منع إنشاء فئات فرعية من فئة معينة، مما يضمن عدم تغيير سلوك الفئة الأصلية.

## الوثائق
تُستخدم الكلمة المحجوزة "sealed" في CSharp لتحديد فئة أو دالة لا يمكن أن يتم تمديدها أو تجاوزها. عند استخدام "sealed" على فئة، فإن أي فئة أخرى تحاول وراثتها ستظهر كخطأ في الكود. هذه الخاصية تعزز من أمان الكود وتساعد في التحكم في سلوك الفئات.

### الاستخدام
يمكن استخدام "sealed" مع الفئات والدوال. إليك كيفية استخدامها:

- **لفئة:**
```csharp
public sealed class MyClass
{
    public void MyMethod()
    {
        // تنفيذ بعض العمليات
    }
}
```

- **لدالة:**
```csharp
public class BaseClass
{
    public sealed void MySealedMethod()
    {
        // تنفيذ بعض العمليات
    }
}
```

## الأمثلة
### مثال على استخدام "sealed" مع فئة
```csharp
public sealed class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

// محاولة وراثة الفئة Animal ستؤدي إلى خطأ
public class Dog : Animal // هذا سيؤدي إلى خطأ
{
}
```

### مثال على استخدام "sealed" مع دالة
```csharp
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Display from BaseClass");
    }
}

public class DerivedClass : BaseClass
{
    public sealed override void Display()
    {
        Console.WriteLine("Display from DerivedClass");
    }
}

// هذه الفئة ستظهر خطأ إذا حاولت تجاوز Display
public class AnotherDerivedClass : DerivedClass
{
    public override void Display() // هذا سيؤدي إلى خطأ
    {
        Console.WriteLine("Another Display");
    }
}
```

## الشرح
يجب الانتباه إلى أن استخدام "sealed" يمكن أن يؤدي إلى بعض القيود. على سبيل المثال، إذا كانت لديك فئة تحتوي على دوال محجوزة، فلن تستطيع الفئات الفرعية تجاوز تلك الدوال. كما أن الفئات المحجوزة تمنع التوسع، مما يمكن أن يؤثر على تصميم البرمجيات في بعض الأحيان. لذلك، استخدم "sealed" بحذر وفقط عندما تكون متأكدًا من أنك لا تحتاج إلى أي شكل من أشكال التمديد.

## ملخص بسيط
الكلمة المحجوزة "sealed" في CSharp تمنع وراثة الفئات، مما يعزز من أمان الكود ويوفر تحكمًا أفضل في سلوك الفئات.