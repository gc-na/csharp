<!--
Meta Description: # C#의 break 문: 제어 흐름을 종료하는 방법 ## 개요 C#에서 `break` 문은 반복문이나 switch 문을 종료시키는 데 사용되는 제어 흐름 구문입니다. 이 명령어는 특정 조건이 충족되었을 때 반복문 또는 switch 문을 즉시 종료하고 다음 코드로 흐름...
Meta Keywords: break, switch, console, writeline, 반복문이나
-->

# C#의 break 문: 제어 흐름을 종료하는 방법

## 개요
C#에서 `break` 문은 반복문이나 switch 문을 종료시키는 데 사용되는 제어 흐름 구문입니다. 이 명령어는 특정 조건이 충족되었을 때 반복문 또는 switch 문을 즉시 종료하고 다음 코드로 흐름을 전환할 수 있게 합니다.

## 문서화
`break` 문은 C#에서 다음과 같은 목적을 가지고 사용됩니다:
- **반복문 종료**: `for`, `foreach`, `while`, `do-while`과 같은 반복문에서 사용되어 루프를 조기에 종료합니다.
- **switch 문 종료**: switch 문 내에서 특정 case가 실행된 후, 나머지 case를 건너뛰고 switch 블록을 종료합니다.

### 사용법
`break` 문은 다음과 같은 형식으로 사용됩니다:

```csharp
break;
```

### 세부사항
- `break` 문은 반복문이나 switch 문 내에서만 유효합니다.
- `break` 문이 호출되면, 해당 블록의 나머지 코드는 실행되지 않고 즉시 다음 코드로 넘어갑니다.
- 중첩된 반복문에서 `break`를 사용할 경우, 가장 가까운 반복문만 종료됩니다.

## 예제
### 반복문에서의 사용 예제
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // i가 5일 때 반복문 종료
    }
    Console.WriteLine(i);
}
```
위 코드는 0부터 4까지의 숫자를 출력한 후, i가 5일 때 반복문을 종료합니다.

### switch 문에서의 사용 예제
```csharp
int day = 3;
switch (day)
{
    case 1:
        Console.WriteLine("월요일");
        break;
    case 2:
        Console.WriteLine("화요일");
        break;
    case 3:
        Console.WriteLine("수요일");
        break; // case 3에서 switch 문 종료
    default:
        Console.WriteLine("주말입니다.");
        break;
}
```
위 코드는 "수요일"을 출력하고, switch 문을 종료합니다.

## 설명
`break` 문을 사용할 때 주의해야 할 점은 다음과 같습니다:
- `break` 문은 반복문이나 switch 문 외부에서 사용될 수 없습니다. 이러한 경우 컴파일 오류가 발생합니다.
- 중첩된 반복문에서 `break`를 사용하면 가장 가까운 반복문만 종료되므로, 중첩된 구조에서 흐름을 이해하는 것이 중요합니다.
- `break` 문을 남용하면 코드의 가독성이 떨어질 수 있으므로, 필요한 경우에만 사용하는 것이 좋습니다.

## 한 줄 요약
C#의 `break` 문은 반복문이나 switch 문을 조기에 종료하는 데 사용되는 제어 흐름 구문입니다.