<!--
Meta Description: # CSharp에서의 "virtual" 키워드: 다형성의 기초 ## 개요 CSharp에서 "virtual" 키워드는 메서드, 속성, 또는 인덱서를 자식 클래스에서 재정의할 수 있도록 허용하는 기능입니다. 이는 객체 지향 프로그래밍의 다형성을 지원하여 코드의 유연성을 높...
Meta Keywords: virtual, public, 클래스에서, 키워드는, 클래스의
-->

# CSharp에서의 "virtual" 키워드: 다형성의 기초

## 개요
CSharp에서 "virtual" 키워드는 메서드, 속성, 또는 인덱서를 자식 클래스에서 재정의할 수 있도록 허용하는 기능입니다. 이는 객체 지향 프로그래밍의 다형성을 지원하여 코드의 유연성을 높입니다.

## 문서화
### 목적
"virtual" 키워드는 기본 클래스에서 정의된 메서드나 속성을 자식 클래스에서 재정의할 수 있게 하여, 동일한 인터페이스를 통해 다양한 객체를 사용할 수 있도록 돕습니다. 이를 통해 코드의 재사용성과 유지보수성을 향상시킬 수 있습니다.

### 사용법
"virtual" 키워드는 클래스 내부의 메서드나 속성을 정의할 때 사용됩니다. 기본 클래스에서 해당 메서드나 속성을 "virtual"로 선언하면, 자식 클래스에서 "override" 키워드를 사용하여 이를 재정의할 수 있습니다.

```csharp
public class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal sound");
    }
}

public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Bark");
    }
}
```

### 세부 사항
- "virtual" 키워드는 메서드, 속성, 인덱서에 모두 적용 가능합니다.
- "override" 키워드는 자식 클래스에서 부모 클래스의 "virtual" 메서드를 재정의할 때 사용합니다.
- "sealed" 키워드를 사용하여 더 이상 재정의할 수 없도록 할 수 있습니다.

## 예제
### 기본 사용 예제
```csharp
public class Shape
{
    public virtual double Area()
    {
        return 0;
    }
}

public class Circle : Shape
{
    private double radius;

    public Circle(double r)
    {
        radius = r;
    }

    public override double Area()
    {
        return Math.PI * radius * radius;
    }
}
```

이 예제에서 `Shape` 클래스의 `Area` 메서드는 "virtual"로 선언되어 `Circle` 클래스에서 재정의되었습니다.

## 설명
- "virtual" 메서드를 사용할 때는 부모 클래스의 메서드가 호출될 수 있는 상황을 고려해야 합니다. 자식 클래스의 객체가 부모 클래스의 참조로 사용될 경우, 부모 클래스의 메서드가 호출됩니다.
- "virtual" 메서드는 다형성을 지원하지만, 성능상 오버헤드가 발생할 수 있습니다. 메서드 호출 시 가상 테이블을 통해 메서드를 찾기 때문입니다.

## 한 줄 요약
CSharp의 "virtual" 키워드는 클래스에서 메서드나 속성을 재정의 가능하게 하여 다형성을 제공하는 기능입니다.