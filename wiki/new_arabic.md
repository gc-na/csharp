<!--
Meta Description: # استخدام الكلمة المفتاحية "new" في CSharp: الدليل الشامل ## الملخص تعتبر الكلمة المفتاحية "new" في لغة CSharp أداة مهمة تُستخدم لإنشاء كائنات جديدة أ...
Meta Keywords: new, الأعضاء, class, public, csharp
-->

# استخدام الكلمة المفتاحية "new" في CSharp: الدليل الشامل

## الملخص
تعتبر الكلمة المفتاحية "new" في لغة CSharp أداة مهمة تُستخدم لإنشاء كائنات جديدة أو لإخفاء الأعضاء الموروثة في الفئات.

## الوثائق
تستخدم الكلمة المفتاحية "new" في CSharp لأغراض متعددة:

1. **إنشاء كائنات جديدة**: عند استخدام "new" مع مُنشئ فئة، يتم إنشاء كائن جديد من تلك الفئة.
2. **إخفاء الأعضاء**: يمكن أيضًا استخدام "new" لإخفاء الأعضاء الموروثة من الفئة الأساسية عند تعريف فئة مشتقة.

### الاستخدام:
- **إنشاء كائن**: 
  ```csharp
  MyClass myObject = new MyClass();
  ```
- **إخفاء الأعضاء**:
  ```csharp
  class BaseClass
  {
      public void Display() { Console.WriteLine("Base Class"); }
  }

  class DerivedClass : BaseClass
  {
      public new void Display() { Console.WriteLine("Derived Class"); }
  }
  ```

## الأمثلة
### المثال 1: إنشاء كائن جديد
```csharp
public class Car
{
    public string Model { get; set; }

    public Car(string model)
    {
        Model = model;
    }
}

class Program
{
    static void Main()
    {
        Car myCar = new Car("Toyota");
        Console.WriteLine(myCar.Model);
    }
}
```

### المثال 2: إخفاء الأعضاء
```csharp
public class Animal
{
    public void Speak() { Console.WriteLine("Animal speaks"); }
}

public class Dog : Animal
{
    public new void Speak() { Console.WriteLine("Dog barks"); }
}

class Program
{
    static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak(); // ستظهر "Animal speaks"
        
        Dog realDog = new Dog();
        realDog.Speak(); // ستظهر "Dog barks"
    }
}
```

## الشرح
- **المزالق الشائعة**: 
  - من الضروري فهم أن استخدام "new" لإخفاء الأعضاء لا يؤدي إلى تغيير السلوك عند استدعاء الأعضاء من الفئة الأساسية. في المثال أعلاه، عند استدعاء `Speak` من خلال مرجع من نوع `Animal`، سيتم استدعاء النسخة من `Animal` وليس `Dog`.
  
- **ملاحظات إضافية**:
  - استخدام "new" ليس إلزاميًا دائمًا، ولكن من المستحسن لتوضيح النية عند إخفاء الأعضاء.
  - يمكن استخدام "new" فقط في الفئات التي تُشتق من فئة أساسية، ولا يمكن استخدامها في الفئات المستقلة.

## ملخص من سطر واحد
تُستخدم الكلمة المفتاحية "new" في CSharp لإنشاء كائنات جديدة وإخفاء الأعضاء الموروثة من الفئات الأساسية.