<!--
Meta Description: # CSharp에서의 static 키워드: 개념과 활용 ## 개요 CSharp에서 `static` 키워드는 클래스, 메서드, 속성 등에서 인스턴스가 아닌 클래스 자체에 속하는 멤버를 정의하는 데 사용됩니다. 이 키워드는 메모리 효율성을 높이고, 전역 상태를 관리하는 데...
Meta Keywords: static, 클래스, public, 클래스의, 인스턴스
-->

# CSharp에서의 static 키워드: 개념과 활용

## 개요
CSharp에서 `static` 키워드는 클래스, 메서드, 속성 등에서 인스턴스가 아닌 클래스 자체에 속하는 멤버를 정의하는 데 사용됩니다. 이 키워드는 메모리 효율성을 높이고, 전역 상태를 관리하는 데 유용합니다.

## 문서화

### 목적
`static` 키워드는 클래스의 인스턴스 없이 직접 접근할 수 있는 멤버를 정의합니다. 이는 객체 지향 프로그래밍에서 객체의 상태를 관리하는 대신 클래스 수준에서 상태를 유지하게 해줍니다.

### 사용법
- **Static 멤버**: `static`으로 선언된 필드, 메서드, 속성은 클래스의 모든 인스턴스에서 공유됩니다.
- **Static 클래스**: `static`으로 선언된 클래스는 인스턴스를 생성할 수 없으며, 모든 멤버가 `static`이어야 합니다.
- **Static 생성자**: 클래스가 처음 사용될 때 실행되는 생성자로, `static` 멤버를 초기화하는 데 사용됩니다.

### 세부사항
- `static` 멤버는 클래스 이름을 통해 접근할 수 있습니다.
- `static` 메서드는 인스턴스 메서드를 호출할 수 없으며, 인스턴스 상태에 접근할 수 없습니다.
- `static` 클래스는 상속할 수 없으며, 다른 클래스의 멤버로 포함될 수 없습니다.

## 예제

### Static 필드와 메서드 예제
```csharp
public class MathUtility
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}

// 사용 예
int result = MathUtility.Add(5, 10);
Console.WriteLine(result); // 출력: 15
```

### Static 클래스 예제
```csharp
public static class Constants
{
    public const double Pi = 3.14;
}

// 사용 예
Console.WriteLine(Constants.Pi); // 출력: 3.14
```

### Static 생성자 예제
```csharp
public class Configuration
{
    public static string DatabaseConnectionString;

    static Configuration()
    {
        DatabaseConnectionString = "DefaultConnectionString";
    }
}

// 사용 예
Console.WriteLine(Configuration.DatabaseConnectionString); // 출력: DefaultConnectionString
```

## 설명
- **공통적인 실수**: `static` 메서드 내에서 인스턴스 필드에 접근하려고 할 때 오류가 발생할 수 있습니다. `static` 멤버는 클래스의 인스턴스와 독립적이기 때문입니다.
- **정적 클래스의 제한**: `static` 클래스를 상속하려고 하거나 인스턴스를 만들려고 하면 컴파일 오류가 발생합니다.
- **정적 생성자의 사용**: 정적 생성자는 클래스가 처음 사용될 때 한 번만 실행되며, 인스턴스 생성 이전에 초기화를 수행해야 할 때 유용합니다.

## 한 줄 요약
CSharp의 `static` 키워드는 클래스 수준에서 공유되는 멤버를 정의하여 메모리 효율성을 높이고 전역 상태를 관리하는 데 사용됩니다.