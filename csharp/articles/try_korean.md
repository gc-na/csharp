<!--
Meta Description: # CSharp의 try 문: 오류 처리의 기초 ## 개요 CSharp에서 `try` 문은 예외 처리를 위한 기본 구조로, 프로그램 실행 중 발생할 수 있는 오류를 처리하여 안정적인 코드 실행을 보장합니다. 이를 통해 프로그램의 비정상적인 종료를 방지하고, 오류 발생 ...
Meta Keywords: try, catch, finally, console, writeline
-->

# CSharp의 try 문: 오류 처리의 기초

## 개요
CSharp에서 `try` 문은 예외 처리를 위한 기본 구조로, 프로그램 실행 중 발생할 수 있는 오류를 처리하여 안정적인 코드 실행을 보장합니다. 이를 통해 프로그램의 비정상적인 종료를 방지하고, 오류 발생 시 적절한 대처를 가능하게 합니다.

## 문서화
`try` 문은 CSharp의 예외 처리 메커니즘의 핵심 요소로, 특정 코드 블록에서 예외가 발생할 경우 이를 포착하고 처리하는 역할을 합니다. `try` 블록 내에서 발생한 예외는 `catch` 블록에서 처리할 수 있으며, 필요에 따라 `finally` 블록을 통해 후속 작업을 수행할 수 있습니다.

### 사용 목적
- 코드의 안정성 향상: 예외 발생 시 프로그램이 종료되지 않도록 함.
- 오류에 대한 적절한 대응: 발생한 오류에 대한 정보를 제공하고, 이를 기반으로 적절한 조치를 취할 수 있음.

### 사용법
```csharp
try
{
    // 예외가 발생할 수 있는 코드
}
catch (ExceptionType ex)
{
    // 예외 처리 코드
}
finally
{
    // 항상 실행되는 코드 (선택 사항)
}
```

## 예제
### 기본 사용 예제
```csharp
using System;

class Program
{
    static void Main()
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]); // 예외 발생
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine("인덱스 범위를 초과했습니다: " + ex.Message);
        }
        finally
        {
            Console.WriteLine("예외 처리 완료.");
        }
    }
}
```

### 다중 catch 블록 예제
```csharp
try
{
    // 코드 블록
}
catch (FormatException ex)
{
    Console.WriteLine("형식 예외 발생: " + ex.Message);
}
catch (OverflowException ex)
{
    Console.WriteLine("오버플로우 예외 발생: " + ex.Message);
}
```

## 설명
`try` 블록 내에서 발생하는 예외는 반드시 `catch` 블록에서 처리해야 합니다. 예외를 처리하지 않으면 프로그램이 비정상적으로 종료될 수 있습니다. 또한, `finally` 블록은 예외 발생 여부와 관계없이 항상 실행되므로, 리소스 정리 작업이나 로그 기록 등 필수적인 작업을 수행하는 데 유용합니다.

### 일반적인 함정
- **catch 블록의 범위**: 특정 예외를 처리하기 위해 올바른 예외 유형을 지정해야 합니다. 일반적인 `Exception` 클래스를 사용할 경우, 모든 예외를 포착하지만, 세부적인 처리는 어려울 수 있습니다.
- **finally 블록의 남용**: `finally` 블록은 반드시 필요한 경우에만 사용해야 하며, 여기서 예외를 발생시키면 예기치 않은 결과를 초래할 수 있습니다.
  
## 한 줄 요약
CSharp의 `try` 문은 예외를 안전하게 처리하고 프로그램의 안정성을 높이기 위한 필수적인 구조입니다.