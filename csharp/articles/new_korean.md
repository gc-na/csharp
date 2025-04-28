<!--
Meta Description: # CSharp의 "new" 키워드: 객체 생성 및 멤버 숨기기 ## 개요 CSharp에서 "new" 키워드는 객체를 생성하거나, 부모 클래스의 멤버를 자식 클래스에서 숨기는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 핵심 개념을 지원하며, 메모리 관리와 코드...
Meta Keywords: new, 클래스의, public, model, 숨기기
-->

# CSharp의 "new" 키워드: 객체 생성 및 멤버 숨기기

## 개요
CSharp에서 "new" 키워드는 객체를 생성하거나, 부모 클래스의 멤버를 자식 클래스에서 숨기는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 핵심 개념을 지원하며, 메모리 관리와 코드 구조를 최적화하는 데 중요한 역할을 합니다.

## 문서화
"new" 키워드는 두 가지 주요 용도로 사용됩니다.

1. **객체 생성**: "new" 키워드를 사용하여 클래스의 인스턴스를 생성할 수 있습니다. 이 경우, 메모리에서 새로운 객체가 할당되고, 생성자가 호출됩니다.

   ```csharp
   MyClass myObject = new MyClass();
   ```

2. **멤버 숨기기**: 자식 클래스에서 부모 클래스의 멤버(변수 또는 메서드)를 숨기기 위해 "new" 키워드를 사용할 수 있습니다. 이 경우, 자식 클래스의 멤버가 같은 이름의 부모 클래스 멤버를 가립니다.

   ```csharp
   class Parent
   {
       public void Display()
       {
           Console.WriteLine("Parent display");
       }
   }

   class Child : Parent
   {
       public new void Display()
       {
           Console.WriteLine("Child display");
       }
   }
   ```

## 예제
### 객체 생성 예제
```csharp
public class Car
{
    public string Model { get; set; }

    public Car(string model)
    {
        Model = model;
    }
}

Car myCar = new Car("Tesla Model 3");
Console.WriteLine(myCar.Model); // 출력: Tesla Model 3
```

### 멤버 숨기기 예제
```csharp
class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

class Dog : Animal
{
    public new void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

Animal myDog = new Dog();
myDog.Speak(); // 출력: Animal speaks
```

## 설명
"new" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **객체 생성 시**: "new" 키워드로 생성된 객체는 힙 메모리에 할당됩니다. 따라서, 생성된 객체는 사용이 끝난 후 적절히 해제해야 합니다. C#의 가비지 컬렉터가 자동으로 메모리를 관리하지만, 불필요한 객체 생성을 피하는 것이 좋습니다.

- **멤버 숨기기 시**: "new" 키워드로 부모 클래스의 멤버를 숨기면, 부모 클래스 타입의 변수를 통해 호출할 경우 부모 클래스의 멤버가 호출됩니다. 이로 인해 의도하지 않은 동작이 발생할 수 있으므로, 멤버 숨기기를 사용할 때는 주의가 필요합니다.

## 한 문장 요약
CSharp의 "new" 키워드는 객체 생성 및 부모 클래스의 멤버를 자식 클래스에서 숨기는 데 사용되는 중요한 키워드입니다.