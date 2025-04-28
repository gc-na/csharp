<!--
Meta Description: # CSharp의 explicit 키워드: 명시적 형 변환 이해하기 ## 개요 CSharp에서 `explicit` 키워드는 명시적 형 변환을 정의하는 데 사용됩니다. 이 키워드는 타입 변환이 안전성을 보장해야 할 때, 즉 암시적 변환이 불가능한 경우에 사용됩니다. ##...
Meta Keywords: explicit, value, 변환을, meter, public
-->

# CSharp의 explicit 키워드: 명시적 형 변환 이해하기

## 개요
CSharp에서 `explicit` 키워드는 명시적 형 변환을 정의하는 데 사용됩니다. 이 키워드는 타입 변환이 안전성을 보장해야 할 때, 즉 암시적 변환이 불가능한 경우에 사용됩니다.

## 문서화
`explicit` 키워드는 클래스에서 사용자 정의 형 변환을 구현할 때 사용됩니다. 이를 통해 사용자는 특정 타입 간의 변환이 명시적으로 이루어져야 함을 지정할 수 있습니다. 예를 들어, 자동으로 변환되어서는 안 되는 경우, 개발자는 `explicit` 키워드를 사용하여 변환 메서드를 정의할 수 있습니다.

### 목적
- 안전한 형 변환을 보장하기 위해 사용됩니다.
- 개발자가 의도하지 않은 형 변환을 방지합니다.

### 사용법
`explicit` 키워드는 다음과 같은 형식으로 사용됩니다:

```csharp
public static explicit operator TargetType(SourceType source)
{
    // 변환 로직
}
```

여기서 `TargetType`은 변환할 대상 타입이며, `SourceType`은 변환할 원본 타입입니다.

## 예제
다음은 `explicit` 키워드를 사용하여 사용자 정의 형 변환을 구현한 예제입니다.

```csharp
public class Meter
{
    public double Value { get; }

    public Meter(double value)
    {
        Value = value;
    }

    // 명시적 형 변환
    public static explicit operator Centimeter(Meter meter)
    {
        return new Centimeter(meter.Value * 100);
    }
}

public class Centimeter
{
    public double Value { get; }

    public Centimeter(double value)
    {
        Value = value;
    }
}

// 사용 예
class Program
{
    static void Main()
    {
        Meter meter = new Meter(1);
        Centimeter centimeter = (Centimeter)meter; // 명시적 변환
        Console.WriteLine(centimeter.Value); // 100 출력
    }
}
```

## 설명
- `explicit` 변환은 반드시 명시적으로 호출해야 하므로, 개발자가 의도한 변환만 이루어지도록 합니다.
- 일반적으로 컴파일러는 암시적 변환을 허용하지만, `explicit` 키워드를 사용하면 이를 방지할 수 있습니다.
- 잘못된 형 변환을 시도하면 컴파일 오류가 발생합니다. 이에 따라 코드의 안정성이 높아집니다.

## 한 줄 요약
CSharp의 `explicit` 키워드는 안전한 형 변환을 위해 명시적 형 변환을 정의하는 데 사용됩니다.