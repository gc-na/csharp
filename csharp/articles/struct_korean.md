<!--
Meta Description: # C#의 구조체 (struct): 기본 개념과 활용 ## 개요 C#의 구조체(struct)는 값 타입의 데이터 구조로, 관련된 데이터 필드를 하나의 단위로 묶어줍니다. 구조체는 클래스와 유사하지만, 메모리 할당, 상속 및 생성자 사용 방식에서 차이가 있습니다. ## ...
Meta Keywords: 데이터, 구조체는, person, public, int
-->

# C#의 구조체 (struct): 기본 개념과 활용

## 개요
C#의 구조체(struct)는 값 타입의 데이터 구조로, 관련된 데이터 필드를 하나의 단위로 묶어줍니다. 구조체는 클래스와 유사하지만, 메모리 할당, 상속 및 생성자 사용 방식에서 차이가 있습니다.

## 문서화
구조체는 주로 작은 데이터 구조를 정의할 때 사용됩니다. 클래스와 비교할 때, 구조체는 기본적으로 값 타입이며, 스택에 저장됩니다. 구조체는 효율적인 데이터 처리를 가능하게 하며, 간단한 데이터 모델을 정의하는 데 유용합니다.

### 목적
- 값 타입 데이터의 그룹화
- 메모리 효율성 증대
- 간단한 데이터 구조 구현

### 사용법
구조체를 정의하려면 `struct` 키워드를 사용합니다. 다음은 기본적인 구조체 정의 방법입니다:

```csharp
struct Person
{
    public string Name;
    public int Age;

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

구조체를 인스턴스화하려면 다음과 같이 합니다:

```csharp
Person person = new Person("홍길동", 30);
Console.WriteLine($"이름: {person.Name}, 나이: {person.Age}");
```

## 예제
다음은 구조체를 사용하는 간단한 예제입니다.

```csharp
struct Rectangle
{
    public int Width;
    public int Height;

    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;
    }

    public int Area()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main()
    {
        Rectangle rect = new Rectangle(10, 5);
        Console.WriteLine($"면적: {rect.Area()}");
    }
}
```

## 설명
구조체를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **불변성**: 구조체는 값 타입이므로, 복사될 때마다 새로운 인스턴스가 생성됩니다. 이로 인해 의도치 않은 데이터 변경이 발생할 수 있습니다.
- **상속**: 구조체는 다른 구조체나 클래스에서 상속받을 수 없습니다. 그러나 인터페이스는 구현할 수 있습니다.
- **기본 생성자**: 구조체는 기본 생성자를 제공하지 않으므로, 모든 필드를 초기화하는 사용자 정의 생성자를 제공해야 합니다.

## 한 줄 요약
C#의 구조체는 값 타입 데이터 구조로, 관련된 필드를 묶어 효율적인 데이터 처리를 가능하게 합니다.