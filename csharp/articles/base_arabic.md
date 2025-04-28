<!--
Meta Description: # استخدام كلمة "base" في لغة C# ## ملخص كلمة "base" في لغة C# هي كلمة محجوزة تستخدم للإشارة إلى أعضاء الفئة الأساسية (الأب) من داخل الفئة المشتقة (الا...
Meta Keywords: الفئة, base, الأساسية, public, إلى
-->

# استخدام كلمة "base" في لغة C#

## ملخص
كلمة "base" في لغة C# هي كلمة محجوزة تستخدم للإشارة إلى أعضاء الفئة الأساسية (الأب) من داخل الفئة المشتقة (الابن). توفر هذه الكلمة وسيلة للوصول إلى الأعضاء (الطرق والخصائص) التي تم تعريفها في الفئة الأساسية.

## الوثائق
تعتبر "base" جزءًا من نظام الوراثة في C#. عند إنشاء فئة جديدة ترث من فئة أخرى، يمكنك استخدام "base" لاستدعاء طرق أو خصائص الفئة الأساسية. هذا يمكن أن يكون مفيدًا عند الحاجة إلى تخصيص سلوك الفئة الأساسية دون فقدان إمكانية الوصول إلى أعضائها.

### الاستخدام
1. **استدعاء Constructors**: يمكنك استخدام "base" لاستدعاء مُنشئ الفئة الأساسية من مُنشئ الفئة المشتقة.
2. **الوصول إلى الأعضاء**: يمكنك استخدام "base" للوصول إلى طرق أو خصائص الفئة الأساسية على الرغم من أن لديك طرق أو خصائص بنفس الاسم في الفئة المشتقة.

### التفاصيل
- **الكتابة**: تكون كلمة "base" غالبًا ما تستخدم في سياق الكود التالي:
  
  ```csharp
  public class Parent
  {
      public void ShowMessage()
      {
          Console.WriteLine("Message from Parent");
      }
  }

  public class Child : Parent
  {
      public void ShowChildMessage()
      {
          base.ShowMessage(); // استدعاء الطريقة من الفئة الأساسية
          Console.WriteLine("Message from Child");
      }
  }
  ```

## الأمثلة
### مثال 1: استدعاء الطرق من الفئة الأساسية
```csharp
public class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public void Speak()
    {
        base.Speak(); // استدعاء Speak من الفئة Animal
        Console.WriteLine("Dog barks");
    }
}

// الاستخدام
Dog dog = new Dog();
dog.Speak();
// الناتج: "Animal speaks" ثم "Dog barks"
```

### مثال 2: استدعاء المُنشئ من الفئة الأساسية
```csharp
public class Vehicle
{
    public Vehicle(string name)
    {
        Console.WriteLine($"Vehicle created: {name}");
    }
}

public class Car : Vehicle
{
    public Car(string name) : base(name) // استدعاء مُنشئ Vehicle
    {
        Console.WriteLine("Car created");
    }
}

// الاستخدام
Car car = new Car("Toyota");
// الناتج: "Vehicle created: Toyota" ثم "Car created"
```

## الشرح
### الأخطاء الشائعة
- **عدم استخدام "base" بشكل صحيح**: يمكن أن يؤدي عدم استخدام "base" عند الحاجة إلى فقدان سلوك الفئة الأساسية. تأكد من فهم كيفية استدعاء الأعضاء الأساسية عند القيام بتجاوز الطرق.
- **تجاوز الأعضاء**: إذا قمت بتجاوز طريقة من الفئة الأساسية بدون استخدام "base"، فلن يتم تنفيذ الكود الأصلي من الفئة الأساسية، مما قد يؤدي إلى سلوك غير متوقع.

## ملخص جملة واحدة
تستخدم كلمة "base" في C# للإشارة إلى الأعضاء في الفئة الأساسية، مما يتيح الوصول إليها من الفئة المشتقة.