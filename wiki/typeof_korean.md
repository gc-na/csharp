<!--
Meta Description: # CSharp의 typeof: 데이터 타입 정보를 얻는 방법 ## 요약 CSharp에서 `typeof`는 특정 타입의 Type 객체를 반환하는 연산자로, 런타임에 타입 정보를 확인할 때 유용하게 사용됩니다. ## 문서 `typeof`는 CSharp에서 특정 데이터 타...
Meta Keywords: typeof, type, system, 정보를, 타입의
-->

# CSharp의 typeof: 데이터 타입 정보를 얻는 방법

## 요약
CSharp에서 `typeof`는 특정 타입의 Type 객체를 반환하는 연산자로, 런타임에 타입 정보를 확인할 때 유용하게 사용됩니다.

## 문서
`typeof`는 CSharp에서 특정 데이터 타입에 대한 메타 정보를 제공하는 연산자입니다. 이 연산자는 컴파일 타임에 타입을 확인하고, 해당 타입의 정보를 포함하는 Type 객체를 생성합니다. 이를 통해 Reflection을 사용하여 타입의 속성이나 메서드, 이벤트 등을 조회할 수 있습니다.

### 사용 목적
- 타입 정보 확인: 특정 클래스, 인터페이스, 구조체 등의 타입 정보를 얻을 수 있습니다.
- Reflection: 런타임에 타입의 메타데이터를 활용하여 동적으로 작업을 수행할 수 있습니다.

### 사용법
```csharp
Type typeInfo = typeof(YourClass);
```
위의 코드에서 `YourClass`는 확인하고자 하는 데이터 타입입니다. `typeInfo` 변수에는 해당 타입의 Type 객체가 저장됩니다.

## 예제
### 기본 사용 예제
```csharp
using System;

class Program
{
    static void Main()
    {
        Type intType = typeof(int);
        Console.WriteLine(intType); // 출력: System.Int32

        Type stringType = typeof(string);
        Console.WriteLine(stringType); // 출력: System.String

        Type listType = typeof(System.Collections.Generic.List<int>);
        Console.WriteLine(listType); // 출력: System.Collections.Generic.List`1[System.Int32]
    }
}
```

### Reflection과 함께 사용 예제
```csharp
using System;
using System.Reflection;

class Sample
{
    public void MyMethod() {}
}

class Program
{
    static void Main()
    {
        Type sampleType = typeof(Sample);
        MethodInfo[] methods = sampleType.GetMethods();
        
        foreach (var method in methods)
        {
            Console.WriteLine(method.Name); // MyMethod
        }
    }
}
```

## 설명
`typeof`를 사용할 때 주의해야 할 점은, 이 연산자는 타입 이름을 문자열로 전달하는 것이 아니라, 직접 타입 자체를 사용해야 한다는 것입니다. 예를 들어, `typeof("string")`와 같은 형태는 유효하지 않습니다. 또한, generics를 사용할 경우 타입 인자는 구체적인 타입을 명시해야 하며, 이를 통해 Type 객체를 생성할 수 있습니다.

### 일반적인 실수
- 문자열로 타입을 전달하려고 시도하는 것.
- 지원되지 않는 타입에 대한 사용.
- generic 타입을 사용할 때, 구체적인 타입을 명시하지 않는 것.

## 한 줄 요약
CSharp의 `typeof` 연산자는 특정 타입의 Type 객체를 반환하여 런타임 시 타입 정보를 확인할 수 있게 해줍니다.