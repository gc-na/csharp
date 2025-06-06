<!--
Meta Description: # استخدام كلمة "using" في لغة CSharp ## ملخص تعتبر كلمة "using" في لغة CSharp أداة قوية تُستخدم لإدارة الموارد والتعامل مع الفضاءات الاسمية. تساعد هذه...
Meta Keywords: using, csharp, استخدام, الموارد, الفضاءات
-->

# استخدام كلمة "using" في لغة CSharp

## ملخص
تعتبر كلمة "using" في لغة CSharp أداة قوية تُستخدم لإدارة الموارد والتعامل مع الفضاءات الاسمية. تساعد هذه الكلمة في تبسيط التعليمات البرمجية، وضمان تحرير الموارد بشكل صحيح.

## الوثائق
تُستخدم كلمة "using" في CSharp في سياقين رئيسيين: إدارة الفضاءات الاسمية (Namespaces) وإدارة الموارد (Resource Management).

### 1. إدارة الفضاءات الاسمية
تتيح لك "using" استيراد الفضاءات الاسمية التي تحتوي على الفئات والدوال التي ترغب في استخدامها. بدلاً من كتابة اسم الفضاء الاسمي بالكامل في كل مرة، يمكنك استخدام "using" لتسهيل الأمر.

**مثال:**
```csharp
using System;
```

### 2. إدارة الموارد
تستخدم "using" أيضًا لإنشاء كتل "using" التي تضمن تحرير الموارد مثل الملفات أو الاتصالات بالشبكة بعد الانتهاء من استخدامها. بعد انتهاء الكود داخل كتلة "using"، يتم استدعاء `Dispose()` تلقائيًا.

**مثال:**
```csharp
using (var fileStream = new FileStream("file.txt", FileMode.Open))
{
    // عمليات القراءة أو الكتابة
}
```

## الأمثلة
### مثال 1: استخدام الفضاءات الاسمية
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("مرحبا بالعالم!");
    }
}
```

### مثال 2: إدارة الموارد
```csharp
using System.IO;

class Program
{
    static void Main()
    {
        using (var writer = new StreamWriter("output.txt"))
        {
            writer.WriteLine("هذا نص داخل ملف.");
        } // يتم إغلاق StreamWriter تلقائيًا هنا.
    }
}
```

## الشرح
### المشكلات الشائعة
- **نسيان استخدام "using"**: إذا نسيت استخدام "using" لإدارة الموارد، فقد يؤدي ذلك إلى تسرب الذاكرة.
- **تعارض الأسماء**: عند استخدام عدة فضاءات اسمية، قد يحدث تعارض في أسماء الفئات. يمكنك استخدام "using" مع توضيح الاسم إذا لزم الأمر.

### ملاحظات إضافية
- يمكنك استخدام "using static" لاستيراد الأعضاء الثابتة من الفئات، مما يتيح لك استخدامها بدون كتابة اسم الفئة.
  
**مثال:**
```csharp
using static System.Math;

class Program
{
    static void Main()
    {
        double result = Sqrt(16); // لا حاجة لكتابة Math.Sqrt
    }
}
```

## ملخص جملة واحدة
كلمة "using" في CSharp تُستخدم لإدارة الفضاءات الاسمية والموارد بكفاءة، مما يسهل كتابة التعليمات البرمجية وإدارتها.