<!--
Meta Description: # C#의 catch 문: 예외 처리의 핵심 ## 개요 C#의 `catch` 문은 예외 처리를 위한 구조의 일부분으로, 프로그램 실행 중 발생할 수 있는 오류를 잡아내고 처리하는 데 사용됩니다. 이를 통해 안정적인 코드를 작성하고 예외 상황에 대한 적절한 대응이 가능합...
Meta Keywords: catch, try, console, writeline, 처리를
-->

# C#의 catch 문: 예외 처리의 핵심

## 개요
C#의 `catch` 문은 예외 처리를 위한 구조의 일부분으로, 프로그램 실행 중 발생할 수 있는 오류를 잡아내고 처리하는 데 사용됩니다. 이를 통해 안정적인 코드를 작성하고 예외 상황에 대한 적절한 대응이 가능합니다.

## 문서화
`catch` 문은 `try` 블록과 함께 사용되어, 코드 실행 중 발생하는 예외를 처리하는 데 도움을 줍니다. `try` 블록 내의 코드에서 예외가 발생하면, 해당 예외는 `catch` 블록으로 전달되어 처리됩니다.

### 목적
- 오류 발생 시 프로그램의 비정상적인 종료를 방지합니다.
- 예외에 대한 구체적인 처리를 통해 사용자에게 유용한 피드백을 제공합니다.
- 코드의 가독성을 높이고 유지보수를 용이하게 합니다.

### 사용법
`catch` 문은 다음과 같은 형태로 사용됩니다:

```csharp
try
{
    // 예외가 발생할 가능성이 있는 코드
}
catch (ExceptionType ex)
{
    // 예외 처리 코드
}
```

여기서 `ExceptionType`은 잡고자 하는 특정 예외의 유형이며, `ex`는 예외 객체입니다.

## 예제
### 기본 사용 예
```csharp
try
{
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers[5]); // 인덱스 초과
}
catch (IndexOutOfRangeException ex)
{
    Console.WriteLine("인덱스가 범위를 초과했습니다: " + ex.Message);
}
```

### 여러 개의 catch 블록
```csharp
try
{
    int number = int.Parse("NotANumber");
}
catch (FormatException ex)
{
    Console.WriteLine("형식이 잘못되었습니다: " + ex.Message);
}
catch (OverflowException ex)
{
    Console.WriteLine("오버플로우 오류: " + ex.Message);
}
```

## 설명
- **일반적인 함정**: `catch` 블록이 너무 일반적인 예외를 처리하도록 설정할 경우, 코드의 문제를 숨길 수 있습니다. `catch (Exception ex)`와 같은 일반 예외 처리기는 예외의 원인을 파악하는 데 방해가 될 수 있습니다.
- **finally 블록**: `catch` 문은 `finally` 문과 함께 사용될 수 있으며, `finally` 블록은 예외 발생 여부와 관계없이 항상 실행됩니다. 이를 통해 리소스 해제를 보장할 수 있습니다.

## 한줄 요약
C#의 `catch` 문은 예외 처리를 통해 안정적인 프로그램 실행과 오류에 대한 사용자 피드백을 제공합니다.