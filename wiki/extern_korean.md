<!--
Meta Description: # CSharp에서 extern 키워드: 외부 함수 호출을 위한 가이드 ## 개요 CSharp에서 `extern` 키워드는 외부 메서드를 선언할 때 사용됩니다. 주로 C/C++로 작성된 네이티브 라이브러리의 기능을 CSharp 코드에서 사용할 수 있도록 해줍니다. ##...
Meta Keywords: extern, 네이티브, 있습니다, 키워드는, dllimport
-->

# CSharp에서 extern 키워드: 외부 함수 호출을 위한 가이드

## 개요
CSharp에서 `extern` 키워드는 외부 메서드를 선언할 때 사용됩니다. 주로 C/C++로 작성된 네이티브 라이브러리의 기능을 CSharp 코드에서 사용할 수 있도록 해줍니다.

## 문서화
`extern` 키워드는 CSharp에서 외부 메서드를 정의할 때 사용됩니다. 이 키워드는 보통 `DllImport` 속성과 함께 사용되어, .NET 애플리케이션이 Windows DLL 또는 다른 네이티브 라이브러리와 상호작용할 수 있도록 합니다. `extern` 키워드를 사용하면, CSharp 코드에서 네이티브 API를 호출할 수 있으며, 이를 통해 성능을 극대화하거나 기존의 네이티브 코드를 재사용할 수 있습니다.

### 사용법
`extern` 키워드는 메서드 선언부에 붙여 사용합니다. 다음은 `DllImport`와 함께 사용하는 기본 형식입니다:

```csharp
using System.Runtime.InteropServices;

public class NativeMethods
{
    [DllImport("user32.dll", CallingConvention = CallingConvention.StdCall)]
    public static extern int MessageBox(IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```

위 예제에서 `MessageBox` 메서드는 Windows API의 MessageBox 함수를 호출하기 위해 `extern`으로 선언되었습니다.

## 예제
### 기본 사용 예제
아래는 `extern` 키워드를 사용하여 기본적인 MessageBox를 호출하는 예제입니다.

```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("user32.dll", CallingConvention = CallingConvention.StdCall)]
    public static extern int MessageBox(IntPtr hWnd, string lpText, string lpCaption, uint uType);

    static void Main()
    {
        MessageBox(IntPtr.Zero, "Hello, World!", "Message", 0);
    }
}
```
위 코드를 실행하면 "Hello, World!"라는 메시지가 포함된 MessageBox가 나타납니다.

## 설명
`extern` 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **호출 규약**: 외부 메서드의 호출 규약은 중요합니다. 잘못된 호출 규약은 프로그램 충돌을 일으킬 수 있습니다. CSharp에서는 `CallingConvention` 속성을 통해 이를 명시할 수 있습니다.

2. **DLL 경로**: `DllImport` 속성에서 지정된 DLL의 경로가 올바른지 확인해야 합니다. DLL이 존재하지 않거나 잘못된 경로를 지정하면 `DllNotFoundException`이 발생합니다.

3. **메모리 관리**: 네이티브 메서드를 호출할 때는 메모리 관리를 신중하게 해야 합니다. CSharp은 가비지 컬렉션을 사용하지만, 네이티브 코드에서는 수동으로 메모리를 관리해야 할 수 있습니다.

4. **보안**: 외부 DLL을 사용하면 보안 문제가 발생할 수 있습니다. 신뢰할 수 있는 소스에서만 DLL을 가져와야 하며, 모호한 API 사용을 피하는 것이 좋습니다.

## 한 줄 요약
CSharp에서 `extern` 키워드는 외부 네이티브 메서드를 선언하여 기존의 C/C++ 코드를 재사용하고, .NET 애플리케이션과의 상호작용을 가능하게 합니다.