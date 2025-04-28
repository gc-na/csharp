<!--
Meta Description: # CSharp에서 readonly 키워드 이해하기: 효율적인 데이터 보호 ## 개요 CSharp에서 `readonly` 키워드는 필드를 선언할 때 사용되며, 객체가 생성된 후 해당 필드의 값을 변경할 수 없도록 합니다. 이 키워드는 불변성을 제공하여 데이터의 무결성을...
Meta Keywords: readonly, circle, radius, public, 키워드는
-->

# CSharp에서 readonly 키워드 이해하기: 효율적인 데이터 보호

## 개요
CSharp에서 `readonly` 키워드는 필드를 선언할 때 사용되며, 객체가 생성된 후 해당 필드의 값을 변경할 수 없도록 합니다. 이 키워드는 불변성을 제공하여 데이터의 무결성을 유지하는 데 유용합니다.

## 문서화
### 목적
`readonly` 키워드는 클래스의 필드에 사용되어, 해당 필드가 객체 생성 시에만 초기화할 수 있고, 그 이후에는 수정할 수 없도록 합니다. 이를 통해 코드의 안정성을 높이고, 예기치 않은 값 변경으로 인한 오류를 방지할 수 있습니다.

### 사용법
`readonly`는 필드 선언 시 사용되며, 생성자 내에서 초기화할 수 있습니다. 예를 들어:

```csharp
public class Example
{
    public readonly int ReadOnlyField;

    public Example(int value)
    {
        ReadOnlyField = value;
    }
}
```

이 경우, `ReadOnlyField`는 `Example` 객체가 생성될 때만 초기화되며, 이후에는 값을 변경할 수 없습니다.

## 예제
다음은 `readonly` 필드를 사용하는 간단한 예제입니다:

```csharp
public class Circle
{
    public readonly double Radius;

    public Circle(double radius)
    {
        Radius = radius;
    }
}

class Program
{
    static void Main()
    {
        Circle circle = new Circle(5);
        Console.WriteLine(circle.Radius); // 출력: 5

        // 다음 줄은 컴파일 오류를 발생시킵니다.
        // circle.Radius = 10; 
    }
}
```

위의 예제에서, `Circle` 클래스의 `Radius` 필드는 `readonly`로 선언되어 있어, 객체 생성 후에는 값을 변경할 수 없습니다.

## 설명
`readonly` 필드를 사용할 때 주의할 점은:
- `readonly` 필드는 객체의 생성자에서만 초기화할 수 있으며, 이후에는 수정할 수 없습니다.
- 다른 메서드나 프로퍼티에서 값을 변경하려고 하면 컴파일 오류가 발생합니다.
- `readonly`는 참조형 타입의 경우, 필드의 참조가 변경되지 않음을 보장하지 않습니다. 즉, 참조하는 객체의 속성은 여전히 변경될 수 있습니다. 따라서 `readonly`는 불변성을 제공하는 것이 아니라, 필드 자체의 재할당을 방지하는 것입니다.

## 한 줄 요약
CSharp의 `readonly` 키워드는 객체 생성 후 필드 값을 변경할 수 없도록 하여 데이터의 무결성을 보장합니다.