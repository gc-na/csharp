<!--
Meta Description: # استخدام عبارة "else" في لغة C# ## ملخص عبارة "else" في لغة C# تُستخدم للتحكم في تدفق البرنامج، حيث تسمح بتنفيذ كود بديل في حال كانت العبارة الشرطية ...
Meta Keywords: else, استخدام, عبارة, الشرطية, الكود
-->

# استخدام عبارة "else" في لغة C#

## ملخص
عبارة "else" في لغة C# تُستخدم للتحكم في تدفق البرنامج، حيث تسمح بتنفيذ كود بديل في حال كانت العبارة الشرطية السابقة (if) غير صحيحة. 

## التوثيق
عبارة "else" هي جزء من بنية التحكم الشرطية في C#. تُستخدم مع عبارة "if" لتوفير خيار بديل يتم تنفيذه عندما تكون العبارة الشرطية غير صحيحة. يعزز استخدام "else" من مرونة البرامج ويتيح للمطور التحكم في مسار التنفيذ بناءً على الشروط المحددة.

### الغرض
- توفير مسار بديل للتنفيذ في حال عدم تحقق شرط معين.
- تحسين تنظيم الكود وجعله أكثر وضوحًا.

### الاستخدام
تظهر جملة "else" كالتالي:

```csharp
if (condition)
{
    // الكود الذي سيتم تنفيذه إذا كانت الشرطية صحيحة
}
else
{
    // الكود الذي سيتم تنفيذه إذا كانت الشرطية غير صحيحة
}
```

يمكن أيضًا استخدام "else if" لتحديد شروط إضافية.

## أمثلة
### مثال 1: استخدام بسيط
```csharp
int number = 10;

if (number > 5)
{
    Console.WriteLine("العدد أكبر من 5");
}
else
{
    Console.WriteLine("العدد 5 أو أقل");
}
```

### مثال 2: استخدام else if
```csharp
int number = 5;

if (number > 5)
{
    Console.WriteLine("العدد أكبر من 5");
}
else if (number == 5)
{
    Console.WriteLine("العدد يساوي 5");
}
else
{
    Console.WriteLine("العدد أقل من 5");
}
```

## الشرح
### الأخطاء الشائعة
- **نسيان القوسين**: تأكد من استخدام القوسين `{}` حول الكود داخل جملتي `if` و`else`، وإلا، سيتم تنفيذ السطر الأول فقط.
- **استخدام جملة `else` بدون جملة `if`**: يجب دائمًا أن تتبع جملة `else` جملة `if`، وإلا سيظهر خطأ في الترجمة.

### ملاحظات إضافية
- يمكن استخدام عبارات `else` داخل حلقات التكرار (loops) أيضًا، مما يزيد من تعقيد التدفق الشرطي.
- استخدام عبارة `else` يجعل الكود أكثر قابلية للقراءة وينظم المنطق بشكل أفضل.

## ملخص من سطر واحد
عبارة "else" في C# توفر مسارًا بديلاً للتنفيذ في حال عدم تحقق شرط معين، مما يعزز من مرونة البرنامج.