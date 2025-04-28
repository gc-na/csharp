<!--
Meta Description: # CSharp의 "protected" 접근 수정자 ## 개요 CSharp의 `protected` 접근 수정자는 클래스의 멤버(필드, 메서드, 속성 등)에 대한 접근을 제어하는 데 사용됩니다. 이 수정자는 해당 멤버가 선언된 클래스와 그 클래스를 상속받은 파생 클래스에...
Meta Keywords: protected, public, dog, 클래스의, animal
-->

# CSharp의 "protected" 접근 수정자

## 개요
CSharp의 `protected` 접근 수정자는 클래스의 멤버(필드, 메서드, 속성 등)에 대한 접근을 제어하는 데 사용됩니다. 이 수정자는 해당 멤버가 선언된 클래스와 그 클래스를 상속받은 파생 클래스에서만 접근할 수 있도록 합니다.

## 문서화
`protected` 접근 수정자는 객체 지향 프로그래밍에서 중요한 역할을 하며, 데이터 캡슐화와 상속을 통해 코드의 유연성을 증가시킵니다. 주로 다음과 같은 목적으로 사용됩니다:

1. **상속을 통한 접근 제어**: `protected` 멤버는 클래스의 외부에서는 접근할 수 없지만, 해당 클래스를 상속받은 클래스에서는 접근 가능하므로, 상속 관계에서의 유용성을 제공합니다.
2. **기능 확장**: 상속을 통해 기본 클래스의 기능을 확장할 수 있으며, 기본 클래스의 내부 상태를 유지하면서도 서브 클래스에서 이를 조작할 수 있습니다.

### 사용법
`protected` 키워드는 클래스 멤버를 정의할 때 사용되며, 다음과 같은 형태로 나타냅니다:

```csharp
public class BaseClass
{
    protected int protectedField;

    protected void ProtectedMethod()
    {
        // 메서드 구현
    }
}

public class DerivedClass : BaseClass
{
    public void AccessProtectedMembers()
    {
        protectedField = 10; // 접근 가능
        ProtectedMethod();    // 접근 가능
    }
}
```

## 예제
아래는 `protected` 접근 수정자의 기본 사용 예제입니다:

```csharp
public class Animal
{
    protected string name;

    protected void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public void Bark()
    {
        name = "Dog";
        Speak(); // Animal 클래스의 protected 메서드 호출
        Console.WriteLine($"{name} barks");
    }
}

// 사용 예
Dog dog = new Dog();
dog.Bark(); // 출력: Animal speaks
           // 출력: Dog barks
```

## 설명
`protected` 접근 수정자를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **다중 상속**: CSharp은 다중 상속을 지원하지 않기 때문에, `protected` 멤버가 여러 클래스에서 상속될 경우 상속 계층 구조를 명확히 이해하고 있어야 합니다.
- **접근 제한**: `protected` 멤버는 같은 클래스의 인스턴스나 비상속 클래스에서 접근할 수 없습니다. 따라서, 외부 클래스에서의 접근이 필요할 경우 `public` 또는 `internal` 접근 수정자를 고려해야 합니다.
- **상속의 깊이**: 다수의 파생 클래스가 있을 경우, `protected` 멤버에 대한 접근이 복잡해질 수 있으므로, 코드의 가독성에 영향을 미칠 수 있습니다.

## 한 줄 요약
CSharp의 `protected` 접근 수정자는 클래스와 그 파생 클래스에서만 접근할 수 있는 멤버를 정의하는 데 사용됩니다.