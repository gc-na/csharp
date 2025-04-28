<!--
Meta Description: # تجاوز (override) في لغة C# ## ملخص تُستخدم عبارة "override" في لغة C# لتجاوز الطرق (methods) المعرفة في فئة أساسية (base class) داخل فئة مشتقة (deri...
Meta Keywords: public, class, الفئة, override, الطريقة
-->

# تجاوز (override) في لغة C#

## ملخص
تُستخدم عبارة "override" في لغة C# لتجاوز الطرق (methods) المعرفة في فئة أساسية (base class) داخل فئة مشتقة (derived class). يتيح هذا المفهوم للمطورين تخصيص سلوك الفئات وفقاً لاحتياجات تطبيقاتهم.

## الوثائق
تُعتبر عبارة "override" جزءًا أساسيًا من مفهوم الوراثة في البرمجة الكائنية (object-oriented programming) في C#. تُستخدم هذه العبارة لتحديد أن الطريقة الموجودة في الفئة المشتقة هي نسخة جديدة من طريقة موجودة مسبقًا في الفئة الأساسية. يجب أن تكون الطريقة في الفئة الأساسية مُعلمة بـ "virtual" أو "abstract".

### الغرض
- لتخصيص أو تعديل سلوك الطرق المعرفة في الفئات الأساسية.
- لتحسين قابلية استخدام الكود وإعادة استخدامه.

### الاستخدام
لتجاوز طريقة، يجب أن تتبع البنية التالية:

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
    public override void Display()
    {
        Console.WriteLine("Display from DerivedClass");
    }
}
```

## أمثلة
### مثال بسيط
```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal myDog = new Dog();
        myDog.Speak(); // ستظهر "Dog barks"
    }
}
```

### مثال مع طرق تجريدية
```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Circle : Shape
{
    private double radius;

    public Circle(double radius)
    {
        this.radius = radius;
    }

    public override double Area()
    {
        return Math.PI * radius * radius;
    }
}
```

## الشرح
### الأخطاء الشائعة
1. **نسيان استخدام "virtual"**: إذا لم تكن الطريقة في الفئة الأساسية مُعلمة بـ "virtual" أو "abstract"، فلن تتمكن من تجاوزها في الفئة المشتقة.
2. **عدم تطابق التوقيع**: يجب أن يتطابق توقيع الطريقة في الفئة المشتقة مع التوقيع في الفئة الأساسية، بما في ذلك اسم الطريقة، ونوع العائد، والمعلمات.
3. **الوصول إلى الأعضاء**: يجب الانتباه إلى مستويات الوصول (access modifiers)؛ حيث أن الطريقة المعلنة بـ "protected" يمكن تجاوزها ولكن لا يمكن الوصول إليها من خارج الفئة أو من فئات غير مشتقة.

## ملخص جملة واحدة
عبارة "override" في C# تُستخدم لتخصيص سلوك الطرق في الفئات المشتقة عن طريق تجاوز الطرق المعرفة في الفئات الأساسية.