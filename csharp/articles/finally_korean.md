<!--
Meta Description: # C#의 finally 구문: 예외 처리의 핵심 ## 개요 C#의 `finally` 구문은 예외 처리에서 중요한 역할을 하며, try-catch 블록과 함께 사용되어 코드 실행 후 반드시 수행되어야 하는 작업을 정의하는 데 사용됩니다. 이 구문은 예외 발생 여부와 관...
Meta Keywords: finally, try, catch, filestream, 구문은
-->

# C#의 finally 구문: 예외 처리의 핵심

## 개요
C#의 `finally` 구문은 예외 처리에서 중요한 역할을 하며, try-catch 블록과 함께 사용되어 코드 실행 후 반드시 수행되어야 하는 작업을 정의하는 데 사용됩니다. 이 구문은 예외 발생 여부와 관계없이 항상 실행되는 코드를 작성할 수 있도록 도와줍니다.

## 문서화
`finally` 구문은 C#의 예외 처리 메커니즘의 일부로, `try` 블록에서 발생한 예외를 처리하기 위해 `catch` 블록과 함께 사용됩니다. `finally` 블록에 포함된 코드는 예외가 발생하든 않든 항상 실행됩니다. 따라서 리소스 해제, 파일 닫기, 네트워크 연결 종료 등의 작업을 수행하는 데 유용합니다.

### 사용법
```csharp
try
{
    // 예외가 발생할 수 있는 코드
}
catch (Exception ex)
{
    // 예외를 처리하는 코드
}
finally
{
    // 항상 실행되는 코드
}
```

## 예제
다음은 `finally` 구문의 기본적인 사용 예제입니다.

```csharp
using System;

class Program
{
    static void Main()
    {
        FileStream fileStream = null;
        try
        {
            fileStream = new FileStream("example.txt", FileMode.Open);
            // 파일 작업 수행
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine("파일을 찾을 수 없습니다: " + ex.Message);
        }
        finally
        {
            if (fileStream != null)
            {
                fileStream.Close(); // 파일 스트림을 닫기
                Console.WriteLine("파일 스트림이 닫혔습니다.");
            }
        }
    }
}
```

이 예제에서는 파일을 열고 작업을 수행하며, 예외 발생 시 파일 스트림을 안전하게 닫기 위해 `finally` 블록을 사용합니다.

## 설명
- `finally` 블록은 `try` 블록과 `catch` 블록 후에 위치합니다.
- `finally` 블록 내의 코드는 `try` 블록에서 예외가 발생하든 발생하지 않든 항상 실행됩니다.
- `finally` 구문은 리소스 관리를 위한 중요한 도구로, 예외가 발생하더라도 리소스가 적절히 해제되도록 보장합니다.
- `finally` 블록은 `try`와 `catch` 없이 단독으로 사용할 수 없습니다.

### 일반적인 함정
- `finally` 블록 내에서 발생한 예외는 `try` 블록의 예외를 덮어쓸 수 있습니다. 따라서 `finally` 블록 내의 코드에서는 예외 처리를 신중하게 해야 합니다.
- `return` 문이 `try` 블록 또는 `catch` 블록에 있을 경우, `finally` 블록은 여전히 실행됩니다. 이는 코드 흐름의 예측 가능성을 감소시킬 수 있으므로 주의해야 합니다.

## 한 줄 요약
C#의 `finally` 구문은 예외 처리에서 항상 실행되는 코드를 정의하여 리소스 관리를 용이하게 합니다.