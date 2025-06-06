<!--
Meta Description: # الكلمة المفتاحية "checked" في لغة CSharp: الاستخدامات والفهم ## ملخص تُستخدم الكلمة المفتاحية "checked" في لغة CSharp للتحقق من تجاوزات الأعداد أثنا...
Meta Keywords: checked, استخدام, csharp, الكلمة, العمليات
-->

# الكلمة المفتاحية "checked" في لغة CSharp: الاستخدامات والفهم

## ملخص
تُستخدم الكلمة المفتاحية "checked" في لغة CSharp للتحقق من تجاوزات الأعداد أثناء إجراء العمليات الحسابية. تعمل هذه الكلمة على ضمان أن العمليات الحسابية التي قد تؤدي إلى تجاوز حدود نوع البيانات ستُظهر استثناءً بدلاً من أن تنتج قيمة غير صحيحة.

## التوثيق
تعتبر "checked" جزءًا من نظام التعامل مع الأخطاء في CSharp، حيث تسمح للمطورين بالتحكم في كيفية التعامل مع تجاوزات الأعداد. عند استخدام "checked"، يتم تفعيل التحقق من الحدود خلال العمليات الحسابية، مما يساعد على منع الأخطاء غير المرغوب فيها.

### الاستخدام
يمكن استخدام الكلمة المفتاحية "checked" في عدة سياقات، مثل:
- العمليات الحسابية.
- تحويلات البيانات بين الأنواع.
- الكتل البرمجية.

### التفاصيل
عند استخدام "checked" في الكود، يقوم المترجم بإجراء التحقق من التجاوزات. إذا حدث تجاوز، سيتم رفع استثناء من نوع `OverflowException`. يمكن استخدام "checked" بشكل منفصل أو كجزء من تعبير أكبر. يمكن أن تُستخدم أيضًا في الكتل:

```csharp
checked 
{
    // العمليات الحسابية هنا
}
```

## الأمثلة
### مثال أساسي 1: استخدام "checked" مع عمليات الجمع
```csharp
int a = 2147483647; // القيمة القصوى لـ int
int b = 1;

try
{
    int result = checked(a + b); // سيؤدي إلى استثناء OverflowException
}
catch (OverflowException)
{
    Console.WriteLine("تجاوز الحد الأقصى للقيمة المسموح بها.");
}
```

### مثال أساسي 2: استخدام "checked" مع تحويلات الأنواع
```csharp
byte b = 255;
try
{
    checked
    {
        b += 1; // سيؤدي إلى استثناء OverflowException
    }
}
catch (OverflowException)
{
    Console.WriteLine("حدث تجاوز في تحويل الأنواع.");
}
```

## الشرح
هناك بعض النقاط الهامة التي يجب الانتباه إليها عند استخدام "checked":
- إذا لم يتم استخدام "checked"، فإن تجاوزات الأعداد قد تؤدي إلى نتائج غير متوقعة دون رفع استثناء.
- يمكن استخدام الكلمة المفتاحية "unchecked" لتعطيل هذا التحقق إذا كان المطور واثقًا من عدم حدوث تجاوز.
- يجب أن تكون حذرًا عند استخدام "checked" في كتل كبيرة من الكود حيث إن التحقق من التجاوز قد يؤدي إلى زيادة زمن التنفيذ.

## ملخص جملة واحدة
تُستخدم الكلمة المفتاحية "checked" في CSharp للتحقق من تجاوزات الأعداد أثناء العمليات الحسابية وتساعد في تجنب الأخطاء الناتجة عن القيم غير الصحيحة.