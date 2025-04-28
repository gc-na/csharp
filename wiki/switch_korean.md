<!--
Meta Description: # C#의 switch 문: 조건문을 간편하게 처리하는 방법 ## 개요 C#의 `switch` 문은 여러 조건을 비교하여 실행할 코드를 선택하는 제어 흐름 명령어입니다. `switch` 문은 여러 `if-else` 문을 대체할 수 있으며, 가독성을 높이고 코드의 간결성...
Meta Keywords: case, switch, break, dayname, 실행될
-->

# C#의 switch 문: 조건문을 간편하게 처리하는 방법

## 개요
C#의 `switch` 문은 여러 조건을 비교하여 실행할 코드를 선택하는 제어 흐름 명령어입니다. `switch` 문은 여러 `if-else` 문을 대체할 수 있으며, 가독성을 높이고 코드의 간결성을 유지하는 데 도움을 줍니다.

## 문서화

### 목적
`switch` 문은 특정 변수의 값에 따라 다양한 경우(case)에 대한 처리를 간편하게 구현할 수 있도록 설계되었습니다. 이를 통해 코드의 명확성과 유지 보수성을 향상시킵니다.

### 사용법
`switch` 문은 다음과 같은 구조로 작성됩니다:

```csharp
switch (expression)
{
    case constant1:
        // constant1에 해당하는 경우 실행될 코드
        break;
    case constant2:
        // constant2에 해당하는 경우 실행될 코드
        break;
    default:
        // 어떤 경우에도 해당하지 않는 경우 실행될 코드
        break;
}
```

- **expression**: 비교할 값입니다.
- **case**: 특정 값과 일치할 때 실행될 코드 블록입니다.
- **break**: `case` 블록의 실행을 종료하고 `switch` 문을 빠져나갑니다. `break`가 없으면 다음 `case` 블록이 연속적으로 실행됩니다.
- **default**: 모든 `case`가 일치하지 않을 때 실행되는 코드 블록입니다. 선택 사항입니다.

### 세부 사항
- `switch` 문은 정수, 문자열, 열거형(enum) 타입 등 다양한 데이터 타입을 지원합니다.
- `case` 문에서 조건으로 사용할 값은 고정된 상수여야 하며, 변수는 사용할 수 없습니다.
- C# 7.0부터는 `switch` 표현식도 도입되어 더 간결한 구문으로 동일한 기능을 수행할 수 있습니다.

## 예제

### 기본 사용 예제

```csharp
int day = 3;
string dayName;

switch (day)
{
    case 1:
        dayName = "일요일";
        break;
    case 2:
        dayName = "월요일";
        break;
    case 3:
        dayName = "화요일";
        break;
    default:
        dayName = "유효하지 않은 날";
        break;
}

Console.WriteLine(dayName); // 출력: 화요일
```

### 문자열을 사용하는 예제

```csharp
string fruit = "사과";
switch (fruit)
{
    case "사과":
        Console.WriteLine("사과입니다.");
        break;
    case "바나나":
        Console.WriteLine("바나나입니다.");
        break;
    default:
        Console.WriteLine("알 수 없는 과일입니다.");
        break;
}
```

## 설명
- `switch` 문을 사용할 때 주의해야 할 점은 `case` 문에서 중복된 값을 사용하면 컴파일 오류가 발생한다는 것입니다.
- `break` 문을 생략하면 의도치 않게 다음 `case` 문이 실행될 수 있으므로 주의해야 합니다. 이를 방지하기 위해서는 각 `case` 블록의 끝에 반드시 `break`를 추가해야 합니다.
- `switch` 문은 코드의 가독성을 높이지만, 너무 많은 `case` 문이 추가될 경우 오히려 복잡해질 수 있으므로 적절한 사용이 필요합니다.

## 한 줄 요약
C#의 `switch` 문은 여러 조건을 비교하여 실행할 코드를 간편하게 선택하는 구조화된 제어 흐름 명령어입니다.