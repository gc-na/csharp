<!--
Meta Description: # C#에서 "continue" 문 사용법 및 설명 ## 개요 C# 프로그래밍 언어에서 "continue" 문은 반복문 내에서 사용되며, 현재 반복의 나머지 코드를 건너뛰고 다음 반복으로 넘어가도록 지시합니다. 이 문은 주로 특정 조건이 충족될 때 반복문에서의 실행 흐...
Meta Keywords: continue, while, 반복을, 반복문, 내에서
-->

# C#에서 "continue" 문 사용법 및 설명

## 개요
C# 프로그래밍 언어에서 "continue" 문은 반복문 내에서 사용되며, 현재 반복의 나머지 코드를 건너뛰고 다음 반복으로 넘어가도록 지시합니다. 이 문은 주로 특정 조건이 충족될 때 반복문에서의 실행 흐름을 제어하는 데 유용합니다.

## 문서화

### 목적
"continue" 문은 반복문(예: for, while, foreach) 내에서 특정 조건이 참일 때, 현재 반복을 종료하고 다음 반복을 시작하도록 합니다. 이를 통해 불필요한 코드 실행을 피하고 코드의 가독성을 높일 수 있습니다.

### 사용법
"continue" 문은 반복문의 블록 내에서 조건문과 함께 사용됩니다. 조건이 참일 경우, "continue" 문이 실행되어 반복문의 다음 반복으로 넘겨집니다. 일반적인 구조는 다음과 같습니다.

```csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0) // 짝수일 때
    {
        continue; // 현재 반복을 건너뛰고 다음 반복으로 이동
    }
    Console.WriteLine(i); // 홀수일 때만 출력
}
```

### 세부사항
- "continue" 문은 `for`, `while`, `do-while`, `foreach`와 같은 반복문에서 사용할 수 있습니다.
- "continue" 문은 주로 조건문과 함께 사용되어 특정 조건에서 반복을 건너뛰는 데 활용됩니다.
- "continue" 문은 블록 내의 나머지 코드를 실행하지 않으므로, 코드의 흐름을 간단하게 제어할 수 있습니다.

## 예제

### 기본 사용 예제
다음은 "continue" 문을 사용하여 짝수를 건너뛰고 홀수만 출력하는 예제입니다.

```csharp
using System;

class Program
{
    static void Main()
    {
        for (int i = 0; i < 10; i++)
        {
            if (i % 2 == 0)
            {
                continue; // 짝수는 건너뛰기
            }
            Console.WriteLine(i); // 홀수 출력
        }
    }
}
```

### while 반복문에서의 사용 예제
```csharp
using System;

class Program
{
    static void Main()
    {
        int i = 0;
        while (i < 10)
        {
            i++;
            if (i % 2 == 0)
            {
                continue; // 짝수는 건너뛰기
            }
            Console.WriteLine(i); // 홀수 출력
        }
    }
}
```

## 설명
- "continue" 문을 사용할 때 주의할 점은 조건이 항상 참일 경우, 반복문이 무한 루프에 빠질 수 있다는 것입니다. 따라서 조건을 적절히 설정해야 합니다.
- "continue" 문은 반복문 안에서만 사용할 수 있으며, 사용할 때는 항상 반복문의 흐름을 고려해야 합니다.

## 한 줄 요약
C#에서 "continue" 문은 반복문 내에서 특정 조건을 만족할 때 현재 반복을 건너뛰고 다음 반복으로 넘어가게 하는 명령어입니다.