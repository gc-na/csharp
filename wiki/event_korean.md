<!--
Meta Description: # CSharp 이벤트 (Event) 사용법 및 예제 ## 개요 CSharp에서 이벤트는 객체 간의 통신을 가능하게 하는 중요한 기능으로, 특정 상황이 발생했을 때 다른 객체에게 알리는 방법을 제공합니다. 이벤트는 주로 사용자 인터페이스(UI) 프로그래밍과 비동기 프로...
Meta Keywords: 이벤트, publisher, 이벤트는, 이벤트를, public
-->

# CSharp 이벤트 (Event) 사용법 및 예제

## 개요
CSharp에서 이벤트는 객체 간의 통신을 가능하게 하는 중요한 기능으로, 특정 상황이 발생했을 때 다른 객체에게 알리는 방법을 제공합니다. 이벤트는 주로 사용자 인터페이스(UI) 프로그래밍과 비동기 프로그래밍에서 많이 사용됩니다.

## 문서화
이벤트는 CSharp의 델리게이트(delegate)와 밀접하게 연관되어 있습니다. 이벤트를 정의하기 위해서는 먼저 델리게이트를 선언해야 하며, 이를 통해 이벤트 핸들러를 등록하고 호출할 수 있습니다. CSharp의 이벤트는 주로 `event` 키워드를 사용하여 선언됩니다.

### 목적
이벤트는 객체가 특정 작업을 완료했음을 다른 객체에 알리기 위한 방법으로, 주로 GUI 애플리케이션에서 사용자 행동에 반응하기 위해 사용됩니다.

### 사용법
이벤트는 다음과 같은 단계로 사용됩니다:

1. **델리게이트 정의**: 이벤트에 대한 서명을 정의합니다.
2. **이벤트 선언**: `event` 키워드를 사용하여 델리게이트 타입의 이벤트를 선언합니다.
3. **이벤트 발생**: 특정 조건에서 이벤트를 발생시킵니다.
4. **이벤트 구독**: 다른 객체가 이벤트에 반응할 수 있도록 핸들러를 등록합니다.

### 예제
다음은 기본적인 이벤트 사용 예제입니다.

```csharp
using System;

public class Publisher
{
    // 델리게이트 정의
    public delegate void Notify();  
    // 이벤트 선언
    public event Notify OnNotify;

    public void TriggerEvent()
    {
        // 이벤트 발생
        OnNotify?.Invoke();
    }
}

public class Subscriber
{
    public void Subscribe(Publisher publisher)
    {
        publisher.OnNotify += Respond; // 이벤트 구독
    }

    private void Respond()
    {
        Console.WriteLine("이벤트가 발생했습니다!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Publisher publisher = new Publisher();
        Subscriber subscriber = new Subscriber();
        
        subscriber.Subscribe(publisher);
        publisher.TriggerEvent(); // 이벤트 발생
    }
}
```

## 설명
이벤트 사용 시 주의해야 할 점은 다음과 같습니다:

- **이벤트 구독 해제**: 이벤트를 구독한 후에는 필요에 따라 구독을 해제해야 메모리 누수를 방지할 수 있습니다.
- **Null 체크**: 이벤트를 호출하기 전에 항상 `?.` 연산자를 사용하여 null 체크를 하는 것이 좋습니다.
- **스레드 안전성**: 멀티스레드 환경에서 이벤트를 발생시키는 경우, 스레드 안전성을 고려해야 합니다.

## 한 줄 요약
CSharp의 이벤트는 객체 간의 통신을 지원하며, 특정 작업이 발생했을 때 다른 객체에 알리는 방법을 제공합니다.