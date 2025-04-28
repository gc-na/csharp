<!--
Meta Description: # C#의 문자열(String) - 모든 것을 알아보자 ## 개요 C#에서 문자열(String)은 문자들의 집합으로, 텍스트 데이터를 저장하고 조작하는 데 사용됩니다. 문자열은 불변(immutable) 타입으로, 한 번 생성된 문자열은 변경할 수 없습니다. 이 문서에서...
Meta Keywords: string, 문자열은, 문자열을, 문자열, 안녕하세요
-->

# C#의 문자열(String) - 모든 것을 알아보자

## 개요
C#에서 문자열(String)은 문자들의 집합으로, 텍스트 데이터를 저장하고 조작하는 데 사용됩니다. 문자열은 불변(immutable) 타입으로, 한 번 생성된 문자열은 변경할 수 없습니다. 이 문서에서는 C#의 문자열의 목적, 사용법, 예제 및 중요한 사항들에 대해 설명합니다.

## 문서화
### 목적
C#의 문자열은 다양한 응용 프로그램에서 중요한 역할을 합니다. 문자열을 사용하면 사용자 입력, 데이터베이스 쿼리, 파일 읽기 및 쓰기 등 다양한 작업을 수행할 수 있습니다. 문자열은 문자(char) 타입 배열로 구현되어 있으며, 다양한 메서드를 통해 문자열을 쉽게 조작할 수 있습니다.

### 사용법
C#에서 문자열은 `string` 키워드를 사용하여 선언합니다. 문자열은 큰따옴표(`"`)로 감싸서 정의하며, 여러 가지 문자열 조작 메서드와 속성을 제공합니다.

```csharp
string greeting = "안녕하세요!";
```

### 주요 메서드
- `Length`: 문자열의 길이를 반환합니다.
- `ToUpper()`: 문자열을 대문자로 변환합니다.
- `ToLower()`: 문자열을 소문자로 변환합니다.
- `Substring(int startIndex, int length)`: 특정 인덱스부터 지정된 길이만큼의 부분 문자열을 반환합니다.
- `IndexOf(string value)`: 특정 문자열이 처음 나타나는 인덱스를 반환합니다.
- `Replace(string oldValue, string newValue)`: 특정 문자열을 다른 문자열로 교체합니다.

## 예제
### 기본 사용 예제
```csharp
using System;

class Program
{
    static void Main()
    {
        string message = "안녕하세요, C#!";
        Console.WriteLine("문자열 길이: " + message.Length); // 문자열 길이: 17
        
        string upperMessage = message.ToUpper();
        Console.WriteLine(upperMessage); // 안녕하세요, C#! -> 안녕하세요, C#!
        
        string subMessage = message.Substring(0, 5);
        Console.WriteLine(subMessage); // 안녕하세요
    }
}
```

## 설명
C#의 문자열은 불변(immutable) 타입이므로, 문자열을 조작할 때마다 새로운 문자열이 생성됩니다. 이는 성능에 영향을 미칠 수 있으므로, 많은 문자열 조작이 필요한 경우 `StringBuilder` 클래스를 사용하는 것이 좋습니다. 또한, 문자열에서 인덱스를 사용할 때 범위를 벗어나는 경우 예외가 발생할 수 있으므로 주의해야 합니다.

### 일반적인 함정 및 주의 사항
- **불변성**: 문자열은 변경 불가능하므로, 문자열을 수정할 때는 항상 새로운 문자열이 생성됩니다.
- **인덱스 오류**: 문자열 인덱스는 0부터 시작하므로, 인덱스를 잘못 계산하면 `IndexOutOfRangeException`이 발생할 수 있습니다.
- **성능**: 자주 변경되는 문자열을 사용할 때는 `StringBuilder`를 고려하세요.

## 한 줄 요약
C#의 문자열은 텍스트 데이터를 저장하고 조작하는 데 사용되는 불변 타입으로, 다양한 메서드를 통해 쉽게 다룰 수 있습니다.