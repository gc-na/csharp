<!--
Meta Description: # CSharp의 Case 구문: 조건문에서의 활용과 예제 ## 개요 CSharp에서 `case` 구문은 `switch` 문과 함께 사용되어 특정 값에 따라 여러 경로 중 하나를 선택할 수 있게 해주는 제어문입니다. 주로 여러 조건을 간결하게 표현할 수 있는 방법으로 ...
Meta Keywords: case, break, number, switch, 조건을
-->

# CSharp의 Case 구문: 조건문에서의 활용과 예제

## 개요
CSharp에서 `case` 구문은 `switch` 문과 함께 사용되어 특정 값에 따라 여러 경로 중 하나를 선택할 수 있게 해주는 제어문입니다. 주로 여러 조건을 간결하게 표현할 수 있는 방법으로 활용됩니다.

## 문서화
`case` 구문은 `switch` 문 내부에서 사용되며, 각 `case`는 특정 조건을 검사하여 그 조건이 참일 때 실행할 코드를 정의합니다. `switch` 문은 주어진 변수의 값을 평가하고, 해당 값과 일치하는 `case`로 제어를 전환합니다. 

### 사용 목적
- 여러 조건을 간결하게 표현
- 코드 가독성 향상
- 복잡한 조건문을 간단하게 처리

### 사용법
```csharp
switch (변수)
{
    case 값1:
        // 값1이 변수와 일치할 때 실행될 코드
        break;
    case 값2:
        // 값2가 변수와 일치할 때 실행될 코드
        break;
    default:
        // 어떤 case에도 일치하지 않을 때 실행될 코드
        break;
}
```

## 예제
다음은 `case` 구문을 활용한 간단한 예제입니다.

```csharp
int number = 2;

switch (number)
{
    case 1:
        Console.WriteLine("Number is 1");
        break;
    case 2:
        Console.WriteLine("Number is 2");
        break;
    case 3:
        Console.WriteLine("Number is 3");
        break;
    default:
        Console.WriteLine("Number is not 1, 2, or 3");
        break;
}
```
위의 예제에서 `number`가 2일 경우 "Number is 2"가 출력됩니다.

## 설명
`case` 구문을 사용할 때 주의해야 할 점은 다음과 같습니다:

- **break 문**: 각 `case` 블록의 끝에 반드시 `break` 문을 포함해야 합니다. 이를 생략할 경우, 다음 `case`로 제어가 넘어가면서 원치 않는 결과를 초래할 수 있습니다.
- **default 문**: 모든 `case`에 해당하지 않을 때 실행되는 `default` 블록을 추가하는 것이 좋습니다. 이는 예기치 않은 입력에 대한 처리를 가능하게 합니다.
- **값의 타입**: `case`에 사용되는 값은 `switch` 문에서 평가되는 변수와 같은 타입이어야 합니다.

## 한 줄 요약
CSharp의 `case` 구문은 `switch` 문과 함께 사용되어 다양한 조건을 간결하게 처리할 수 있는 강력한 제어문입니다.