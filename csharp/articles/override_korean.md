<!--
Meta Description: # CSharp의 Override: 메서드 재정의의 모든 것 ## 개요 CSharp에서 `override` 키워드는 상속받은 클래스의 메서드를 재정의할 때 사용됩니다. 이를 통해 자식 클래스가 부모 클래스의 메서드를 변경하거나 확장하여 새로운 기능을 구현할 수 있습니다...
Meta Keywords: override, 클래스의, public, 메서드를, class
-->

# CSharp의 Override: 메서드 재정의의 모든 것

## 개요
CSharp에서 `override` 키워드는 상속받은 클래스의 메서드를 재정의할 때 사용됩니다. 이를 통해 자식 클래스가 부모 클래스의 메서드를 변경하거나 확장하여 새로운 기능을 구현할 수 있습니다.

## 문서화
### 목적
`override` 키워드는 상속 관계에 있는 클래스에서 메서드의 동작을 수정하고자 할 때 사용됩니다. 기본적으로 부모 클래스에서 정의된 가상 메서드를 자식 클래스에서 재정의하여, 자식 클래스에 특화된 구현을 제공할 수 있습니다.

### 사용법
- `override` 키워드는 부모 클래스의 메서드 앞에 붙여 사용합니다.
- 부모 클래스의 메서드는 `virtual`이나 `abstract`로 선언되어야 합니다.
- 반환 타입과 매개변수는 부모 클래스의 메서드와 동일해야 합니다.

### 세부사항
- `override` 키워드를 사용하면, 다형성을 활용하여 부모 클래스의 메서드를 호출할 때 자식 클래스의 메서드가 실행됩니다.
- `base` 키워드를 사용하여 부모 클래스의 메서드를 호출할 수도 있습니다.
- `override` 메서드는 기본적으로 `virtual` 메서드의 동작을 변경하므로, 메서드의 접근 제한자도 일치해야 합니다.

## 예제
### 기본 사용 예제

```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks.");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks.");
    }
}

class Program
{
    static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak(); // 출력: Dog barks.
    }
}
```

### 추가 예제

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

class Program
{
    static void Main()
    {
        Shape myCircle = new Circle(5);
        Console.WriteLine(myCircle.Area()); // 출력: 78.53981633974483
    }
}
```

## 설명
- **공통적인 오류**: `override` 키워드를 사용할 때 부모 메서드의 시그니처와 정확히 일치해야 합니다. 시그니처가 다르면 컴파일 오류가 발생합니다. 
- **가상 메서드와의 차이**: `virtual` 메서드는 기본 구현을 제공하지만, `override`는 그 메서드를 구체적으로 정의하여 다르게 동작하도록 할 수 있습니다.
- **추상 클래스**: `abstract` 메서드는 반드시 자식 클래스에서 재정의해야 하므로, `override` 키워드를 사용해야 합니다.
- **다형성**: 부모 클래스 타입의 참조변수로 자식 클래스 객체를 다룰 수 있어, 코드의 유연성과 재사용성을 높일 수 있습니다.

## 한 줄 요약
CSharp에서 `override` 키워드는 부모 클래스의 메서드를 자식 클래스에서 재정의하여 다형성을 활용하는 데 필수적인 키워드입니다.