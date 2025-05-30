<!--
Meta Description: # حلقة "for" في لغة C# ## ملخص حلقة "for" في لغة C# تُستخدم لتنفيذ مجموعة من التعليمات بشكل متكرر، حيث يتم تحديد عدد مرات التكرار مسبقًا. تعتبر هذه ال...
Meta Keywords: حلقة, التعليمات, تكرار, يتم, الحلقة
-->

# حلقة "for" في لغة C#

## ملخص
حلقة "for" في لغة C# تُستخدم لتنفيذ مجموعة من التعليمات بشكل متكرر، حيث يتم تحديد عدد مرات التكرار مسبقًا. تعتبر هذه الحلقة من الأدوات الأساسية في البرمجة للتحكم في تدفق البرنامج.

## الوثائق
حلقة "for" هي عبارة عن بنية تحكم تتيح لك تكرار تنفيذ كتلة من التعليمات لعدد محدد من المرات. تتكون صيغة حلقة "for" من ثلاثة أجزاء رئيسية:

1. **التهيئة**: تُستخدم لإعداد المتغيرات التي ستتحكم في عدد مرات التكرار.
2. **شرط الاستمرار**: شرط يُقيم قبل كل تكرار، إذا كان صحيحاً يتم تنفيذ التعليمات، وإذا كان خاطئاً يتم إنهاء الحلقة.
3. **تحديث**: تُستخدم لتحديث المتغيرات بعد كل تكرار.

### الصيغة العامة:
```csharp
for (initialization; condition; increment)
{
    // كتلة التعليمات
}
```

### الغرض والاستخدام
يتم استخدام حلقة "for" في الحالات التي نعرف فيها مسبقًا عدد المرات التي نرغب في تكرار التعليمات. تُعتبر فعالة في التعامل مع المصفوفات والقوائم، حيث تُستخدم للتكرار عبر عناصرها.

## أمثلة
### مثال 1: حلقة "for" بسيطة
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("العدد هو: " + i);
}
```
**الوصف**: هذا المثال سيطبع الأعداد من 0 إلى 4.

### مثال 2: استخدام حلقة "for" مع مصفوفة
```csharp
string[] الفواكه = { "تفاح", "موز", "برتقال" };
for (int i = 0; i < الفواكه.Length; i++)
{
    Console.WriteLine(الفواكه[i]);
}
```
**الوصف**: هذا المثال سيطبع جميع العناصر في مصفوفة الفواكه.

## الشرح
### الأخطاء الشائعة
- **عدم تحديث المتغير**: إذا نسيت تحديث المتغير في قسم التحديث، ستدخل الحلقة في حالة تكرار غير نهائي.
- **شرط خاطئ**: إذا كان الشرط غير صحيح في البداية، قد لا يتم تنفيذ التعليمات داخل الحلقة أبدًا.
- **نطاق المتغيرات**: تأكد من أن المتغيرات المستخدمة في الحلقة لها نطاق صالح.

### ملاحظات إضافية
- يمكن استخدام حلقة "for" للتكرار في الاتجاه العكسي باستخدام قيم سالبة في قسم التحديث.
- من الممكن استخدام حلقة "for" في سياقات أكثر تعقيدًا، مثل إدراج الشروط أو العمليات الحسابية في أقسامها.

## ملخص مختصر
حلقة "for" في C# تتيح تكرار تنفيذ التعليمات لعدد محدد من المرات، مما يسهل التحكم في تدفق البرنامج.