<!--
Meta Description: # C#에서의 Enum: 열거형에 대한 완벽 가이드 ## 개요 C#에서 `enum`(열거형)은 관련 상수 집합에 이름을 부여하여 코드를 더 읽기 쉽게 하고 유지보수를 용이하게 해주는 데이터 타입입니다. ## 문서화 C#의 `enum`은 특정 값의 집합을 정의할 수 있는...
Meta Keywords: enum, trafficlight, 열거형, 이름을, 데이터
-->

# C#에서의 Enum: 열거형에 대한 완벽 가이드

## 개요
C#에서 `enum`(열거형)은 관련 상수 집합에 이름을 부여하여 코드를 더 읽기 쉽게 하고 유지보수를 용이하게 해주는 데이터 타입입니다.

## 문서화
C#의 `enum`은 특정 값의 집합을 정의할 수 있는 사용자 지정 데이터 형식입니다. 열거형은 명확한 이름을 통해 코드의 가독성을 높이며, 코드에서 사용할 수 있는 상수의 집합을 정의합니다. `enum`은 기본적으로 정수형(int)을 기반으로 하며, 사용자가 직접 다른 기본 타입을 지정할 수도 있습니다.

### 목적
1. **가독성 향상**: 상수값에 접근할 때 의미 있는 이름을 사용하여 코드의 가독성을 높입니다.
2. **타입 안전성**: 열거형은 특정 값의 집합을 제한하여 잘못된 데이터 입력을 방지합니다.
3. **유지보수 용이성**: 상수값을 열거형으로 정의함으로써 코드의 변경이 필요할 때 관리가 수월해집니다.

### 사용법
열거형은 다음과 같이 정의할 수 있습니다:

```csharp
enum EnumName
{
    Value1,
    Value2,
    Value3
}
```

각 열거형 값은 기본적으로 0부터 시작하여 1씩 증가합니다. 그러나 사용자는 값을 명시적으로 지정할 수도 있습니다.

```csharp
enum Days
{
    Sunday = 1,
    Monday = 2,
    Tuesday = 3,
    Wednesday = 4,
    Thursday = 5,
    Friday = 6,
    Saturday = 7
}
```

## 예제
다음은 C#에서 열거형을 사용하는 기본적인 예제입니다.

```csharp
using System;

enum TrafficLight
{
    Red,
    Yellow,
    Green
}

class Program
{
    static void Main()
    {
        TrafficLight light = TrafficLight.Red;

        switch (light)
        {
            case TrafficLight.Red:
                Console.WriteLine("Stop!");
                break;
            case TrafficLight.Yellow:
                Console.WriteLine("Caution!");
                break;
            case TrafficLight.Green:
                Console.WriteLine("Go!");
                break;
        }
    }
}
```

이 예제는 교통 신호를 나타내는 열거형을 정의하고, 해당 신호에 따라 메시지를 출력합니다.

## 설명
열거형 사용 시 주의해야 할 점은 다음과 같습니다:
- **기본값**: 열거형을 선언하면 기본값은 0입니다. 이는 코드에서 열거형을 사용할 때 의도하지 않은 값을 가질 수 있으니 주의해야 합니다.
- **형 변환**: 열거형 값은 정수형으로 변환할 수 있으며, 반대로 정수형 값을 열거형으로 변환할 때 잘못된 값이 사용될 수 있습니다.
- **확장성**: 열거형에 새로운 값을 추가할 때 기존의 코드가 예상치 못한 동작을 할 수 있으니, 항상 기존 코드를 검토해야 합니다.

## 한 줄 요약
C#에서 `enum`은 관련 상수의 집합에 이름을 부여하여 코드의 가독성을 높이고 유지보수를 용이하게 해주는 강력한 데이터 형식입니다.