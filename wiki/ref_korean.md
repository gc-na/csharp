<!--
Meta Description: # CSharp의 "ref" 키워드에 대한 완벽 가이드 ## 개요 CSharp에서 "ref" 키워드는 메서드에 인수로 전달된 변수의 참조를 전달할 수 있게 해주는 기능입니다. 이를 통해 메서드 내에서 변수의 값을 직접 수정할 수 있으며, 성능 향상에도 기여할 수 있습니...
Meta Keywords: ref, point, 변수의, 메서드, int
-->

# CSharp의 "ref" 키워드에 대한 완벽 가이드

## 개요
CSharp에서 "ref" 키워드는 메서드에 인수로 전달된 변수의 참조를 전달할 수 있게 해주는 기능입니다. 이를 통해 메서드 내에서 변수의 값을 직접 수정할 수 있으며, 성능 향상에도 기여할 수 있습니다.

## 문서화
"ref" 키워드는 CSharp에서 변수의 참조를 메서드에 전달할 때 사용됩니다. 기본적으로 메서드에 인수를 전달할 때는 값이 복사되지만, "ref"를 사용하면 원본 변수를 참조하게 되어 메서드 내에서 변수의 값을 변경할 수 있습니다. 

### 목적
- **변수 수정 가능**: 메서드 내에서 인수로 전달된 변수의 값을 직접 수정할 수 있습니다.
- **성능 향상**: 큰 데이터 구조체를 전달할 때 값 복사로 인한 성능 저하를 피할 수 있습니다.

### 사용법
"ref" 키워드는 메서드 정의와 호출 모두에서 사용해야 합니다. 

```csharp
void UpdateValue(ref int number) {
    number += 10;
}

int myNumber = 5;
UpdateValue(ref myNumber); // myNumber는 이제 15입니다.
```

## 예제
1. **기본 사용 예**
    ```csharp
    void Increment(ref int value) {
        value++;
    }

    int count = 1;
    Increment(ref count);
    Console.WriteLine(count); // 출력: 2
    ```

2. **구조체와 함께 사용**
    ```csharp
    struct Point {
        public int X;
        public int Y;
    }

    void Move(ref Point p) {
        p.X += 1;
        p.Y += 1;
    }

    Point point = new Point { X = 0, Y = 0 };
    Move(ref point);
    Console.WriteLine($"X: {point.X}, Y: {point.Y}"); // 출력: X: 1, Y: 1
    ```

## 설명
"ref" 키워드를 사용할 때 주의해야 할 몇 가지 점이 있습니다:

- **초기화 필수**: "ref" 변수를 메서드에 전달하기 전에 반드시 초기화해야 합니다. 초기화되지 않은 변수를 "ref"로 전달하면 컴파일 오류가 발생합니다.
- **모든 호출에서 사용**: 메서드 호출 시 "ref" 키워드를 반드시 명시해야 하며, 메서드 정의에서도 이를 포함해야 합니다.
- **읽기 전용 변수 사용 불가**: 읽기 전용(읽기 전용 속성이 있는) 변수를 "ref"로 사용할 수 없습니다.

## 요약
CSharp에서 "ref" 키워드는 메서드에 인수로 전달된 변수의 참조를 사용하여 값을 직접 수정할 수 있게 해주는 유용한 기능입니다.