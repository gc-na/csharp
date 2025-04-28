<!--
Meta Description: # C# 클래스에 대한 모든 것: 정의, 사용법 및 예제 ## 개요 C#에서 클래스는 객체 지향 프로그래밍의 기본 단위로, 속성과 메서드를 포함하여 객체를 정의하는 데 사용됩니다. 클래스는 코드의 재사용성을 높이고, 데이터와 기능을 하나의 단위로 묶어 관리할 수 있도록...
Meta Keywords: public, model, 클래스의, 클래스는, color
-->

# C# 클래스에 대한 모든 것: 정의, 사용법 및 예제

## 개요
C#에서 클래스는 객체 지향 프로그래밍의 기본 단위로, 속성과 메서드를 포함하여 객체를 정의하는 데 사용됩니다. 클래스는 코드의 재사용성을 높이고, 데이터와 기능을 하나의 단위로 묶어 관리할 수 있도록 합니다.

## 문서
C# 클래스는 객체 지향 프로그래밍의 핵심 개념으로, 특정 데이터 구조와 관련된 행동을 정의하는 블루프린트입니다. 클래스는 다음과 같은 요소로 구성됩니다:

- **속성(Fields)**: 클래스가 보유하는 데이터입니다.
- **메서드(Methods)**: 클래스의 객체가 수행할 수 있는 동작입니다.
- **생성자(Constructor)**: 클래스의 인스턴스가 생성될 때 호출되는 특별한 메서드입니다.
- **소멸자(Destructor)**: 클래스의 인스턴스가 소멸될 때 호출됩니다.

### 사용법
클래스를 정의하려면 `class` 키워드를 사용합니다. 다음은 클래스 정의의 기본 구조입니다:

```csharp
public class ClassName
{
    // 필드
    private int field;

    // 생성자
    public ClassName(int value)
    {
        field = value;
    }

    // 메서드
    public void DisplayField()
    {
        Console.WriteLine(field);
    }
}
```

클래스를 인스턴스화하려면 `new` 키워드를 사용합니다:

```csharp
ClassName myObject = new ClassName(10);
myObject.DisplayField(); // 출력: 10
```

## 예제
다음은 C# 클래스의 기본 사용 예제입니다.

```csharp
public class Car
{
    // 속성
    public string Model { get; set; }
    public string Color { get; set; }

    // 생성자
    public Car(string model, string color)
    {
        Model = model;
        Color = color;
    }

    // 메서드
    public void DisplayInfo()
    {
        Console.WriteLine($"모델: {Model}, 색상: {Color}");
    }
}

// 클래스 사용
Car myCar = new Car("Tesla Model S", "Red");
myCar.DisplayInfo(); // 출력: 모델: Tesla Model S, 색상: Red
```

## 설명
클래스를 사용할 때 주의해야 할 몇 가지 일반적인 함정이 있습니다:

- **접근 제어자**: 클래스의 접근 제어자를 잘 설정해야 합니다. `public`, `private`, `protected` 등을 적절히 사용하지 않으면 데이터 은닉을 잘못할 수 있습니다.
- **생성자 오버로딩**: 여러 생성자를 정의할 수 있지만, 매개변수의 수와 타입을 구분하는 것이 중요합니다. 그렇지 않으면 컴파일러가 어떤 생성자를 호출할지 혼란스러워 할 수 있습니다.
- **상속**: 클래스를 상속할 때는 기본 클래스의 접근 제어자를 고려해야 하며, `virtual` 및 `override` 키워드를 적절히 사용해야 합니다.

## 한 줄 요약
C# 클래스는 객체 지향 프로그래밍의 기본 구성 요소로, 속성과 메서드를 통해 데이터와 행동을 정의합니다.