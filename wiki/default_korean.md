<!--
Meta Description: # CSharp의 "default" 키워드: 기본값을 설정하는 방법 ## 개요 CSharp에서 "default" 키워드는 제네릭 타입이나 열거형(enum) 타입의 기본값을 얻거나, 조건부 연산에서 사용되는 중요한 기능입니다. 이 키워드는 코드의 가독성을 높이고, 타입 ...
Meta Keywords: default, 제네릭, 기본값을, 키워드는, 열거형
-->

# CSharp의 "default" 키워드: 기본값을 설정하는 방법

## 개요
CSharp에서 "default" 키워드는 제네릭 타입이나 열거형(enum) 타입의 기본값을 얻거나, 조건부 연산에서 사용되는 중요한 기능입니다. 이 키워드는 코드의 가독성을 높이고, 타입 안전성을 보장하는 데 기여합니다.

## 문서
"Default" 키워드는 주로 두 가지 주요 용도로 사용됩니다. 첫 번째는 제네릭 타입의 기본값을 반환하는 것이고, 두 번째는 열거형(enum)의 기본값을 설정하는 것입니다. 

### 목적
- 제네릭 타입의 기본값을 가져올 수 있습니다.
- 열거형 타입의 초기 값을 설정하는 데 유용합니다.

### 사용법
"Default" 키워드는 다음과 같이 사용됩니다:

- 제네릭 타입에서 기본값을 얻기:
  ```csharp
  T defaultValue = default(T);
  ```

- 열거형 타입에서의 기본값:
  ```csharp
  enum Color { Red, Green, Blue }
  Color defaultColor = default(Color);
  ```

### 세부 사항
- "default" 키워드는 값 형식(Value Type)과 참조 형식(Reference Type) 모두에 대해 사용될 수 있습니다. 값 형식의 경우 기본값은 해당 형식의 "0" 값이며, 참조 형식의 경우 null입니다.
- 열거형의 경우, "default"는 해당 열거형의 첫 번째 값으로 초기화됩니다.

## 예제
### 제네릭 타입에서 기본값 사용하기
```csharp
public T GetDefaultValue<T>()
{
    return default(T);
}

// 사용 예
int defaultInt = GetDefaultValue<int>(); // 결과: 0
string defaultString = GetDefaultValue<string>(); // 결과: null
```

### 열거형의 기본값 설정
```csharp
enum Status { Active, Inactive, Pending }
Status currentStatus = default(Status); // 결과: Active
```

## 설명
"Default" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 값 형식의 경우, 기본값이 "0"으로 설정되므로, 해당 값이 의미하는 바를 항상 고려해야 합니다.
- "default"를 사용할 때, 타입이 명확히 지정되어야 하며, 그렇지 않을 경우 컴파일 오류가 발생할 수 있습니다.
- 제네릭 메서드나 제네릭 클래스에서 사용할 때, 잘못된 타입을 전달하면 예외가 발생할 수 있습니다.

## 한 줄 요약
CSharp의 "default" 키워드는 제네릭 및 열거형 타입의 기본값을 안전하게 얻기 위해 사용되는 키워드입니다.