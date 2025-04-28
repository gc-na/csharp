<!--
Meta Description: # الأحداث في CSharp: مفهومها واستخداماتها ## ملخص تُعتبر الأحداث في لغة CSharp آلية قوية تُستخدم لإبلاغ الكائنات بحدوث تغييرات أو أحداث معينة. تتيح هذ...
Meta Keywords: الأحداث, public, csharp, class, publisher
-->

# الأحداث في CSharp: مفهومها واستخداماتها

## ملخص
تُعتبر الأحداث في لغة CSharp آلية قوية تُستخدم لإبلاغ الكائنات بحدوث تغييرات أو أحداث معينة. تتيح هذه الميزة للكائنات التواصل مع بعضها البعض بطريقة منظمة وفعالة.

## الوثائق
تُستخدم الأحداث في CSharp لتعزيز مفهوم البرمجة القائمة على الأحداث. وهي عبارة عن مكونات تُستخدم للإشارة إلى حدوث شيء معين، مثل الضغط على زر أو تغيير قيمة. يتم تعريف الأحداث باستخدام الكلمة المفتاحية `event`، وعادةً ما يتم ربطها بأحداث مثل النقر، التمرير، أو حتى التغييرات في البيانات.

### الغرض
الغرض من الأحداث هو تمكين الكائنات من التواصل مع بعضها البعض بطريقة غير متزامنة، مما يتيح لك إنشاء تطبيقات تفاعلية وسريعة الاستجابة.

### الاستخدام
لتعريف حدث في CSharp، تُستخدم الكلمة المفتاحية `event` مع نوع المندوب (delegate) الذي يحدد توقيع الحدث. يتم استخدام الأحداث عادةً مع المندوبين لمراقبة الأحداث.

## أمثلة
### مثال 1: تعريف حدث بسيط
```csharp
using System;

public class Publisher
{
    public event EventHandler MyEvent;

    public void RaiseEvent()
    {
        MyEvent?.Invoke(this, EventArgs.Empty);
    }
}

public class Subscriber
{
    public void OnMyEvent(object sender, EventArgs e)
    {
        Console.WriteLine("حدث تم استدعاءه");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Publisher publisher = new Publisher();
        Subscriber subscriber = new Subscriber();

        publisher.MyEvent += subscriber.OnMyEvent;
        publisher.RaiseEvent(); // سيظهر "حدث تم استدعاءه"
    }
}
```

### مثال 2: استخدام الأحداث مع معلمات مخصصة
```csharp
using System;

public class DataChangedEventArgs : EventArgs
{
    public int NewValue { get; set; }
}

public class DataSource
{
    public event EventHandler<DataChangedEventArgs> DataChanged;

    private int _data;
    public int Data
    {
        get => _data;
        set
        {
            _data = value;
            OnDataChanged(new DataChangedEventArgs { NewValue = _data });
        }
    }

    protected virtual void OnDataChanged(DataChangedEventArgs e)
    {
        DataChanged?.Invoke(this, e);
    }
}

class Program
{
    static void Main(string[] args)
    {
        DataSource dataSource = new DataSource();
        dataSource.DataChanged += (sender, e) =>
        {
            Console.WriteLine($"تم تغيير القيمة إلى: {e.NewValue}");
        };

        dataSource.Data = 10; // سيظهر "تم تغيير القيمة إلى: 10"
    }
}
```

## الشرح
عند استخدام الأحداث، قد يواجه المطورون بعض العقبات. من الأمور الشائعة:
- **عدم تسجيل المستمعين**: إذا لم يتم تسجيل المستمعين بشكل صحيح، فلن يتم استدعاء الأحداث.
- **التسرب في الذاكرة**: إذا تم الاحتفاظ بمراجع إلى الكائنات في الأحداث دون إلغاء الاشتراك، قد يحدث تسرب في الذاكرة.
- **التنفيذ المتزامن**: يجب توخي الحذر عند التعامل مع الأحداث في بيئات متعددة الخيوط.

## ملخص بجملة واحدة
الأحداث في CSharp هي آلية تُستخدم للإبلاغ عن تغييرات أو أحداث معينة بين الكائنات بطريقة فعالة ومنظمة.