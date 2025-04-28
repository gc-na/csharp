<!--
Meta Description: # CSharp에서 foreach 문: 배열 및 컬렉션 반복을 위한 강력한 도구 ## 개요 CSharp의 `foreach` 문은 배열, 리스트, 또는 기타 컬렉션의 요소를 쉽게 반복(iterate)할 수 있도록 해주는 제어 구조입니다. 이 문을 사용하면 코드가 간결하고...
Meta Keywords: foreach, 컬렉션의, 요소를, 컬렉션, csharp
-->

# CSharp에서 foreach 문: 배열 및 컬렉션 반복을 위한 강력한 도구

## 개요
CSharp의 `foreach` 문은 배열, 리스트, 또는 기타 컬렉션의 요소를 쉽게 반복(iterate)할 수 있도록 해주는 제어 구조입니다. 이 문을 사용하면 코드가 간결하고 읽기 쉽게 유지되며, 다양한 데이터 구조를 효과적으로 처리할 수 있습니다.

## 문서화
`foreach` 문은 CSharp 프로그래밍에서 반복 작업을 수행하는 데 사용됩니다. 이 문은 컬렉션의 각 요소를 하나씩 접근할 수 있게 해주며, 일반적으로 `IEnumerable` 또는 `IEnumerable<T>` 인터페이스를 구현하는 데이터 구조와 함께 사용됩니다.

### 목적
`foreach` 문은 배열이나 리스트 같은 컬렉션의 모든 요소를 순회하면서 각 요소에 대해 특정 작업을 수행할 수 있게 해줍니다. 

### 사용법
`foreach` 문은 다음과 같은 형식으로 사용됩니다:

```csharp
foreach (타입 변수명 in 컬렉션)
{
    // 반복할 코드
}
```

- **타입**: 컬렉션의 요소 타입입니다.
- **변수명**: 현재 반복 중인 요소를 참조하는 변수입니다.
- **컬렉션**: 반복할 데이터 구조입니다.

### 세부 사항
- `foreach` 문은 컬렉션에 대한 읽기 전용 액세스를 제공합니다. 즉, 반복 중에 컬렉션의 요소를 추가하거나 삭제할 수 없습니다.
- 컬렉션의 크기가 변경되면 `InvalidOperationException`이 발생할 수 있습니다.

## 예제
다음은 `foreach` 문을 사용하는 간단한 예제입니다:

### 배열에서의 사용
```csharp
string[] fruits = { "사과", "바나나", "체리" };
foreach (string fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

### 리스트에서의 사용
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```

## 설명
`foreach` 문을 사용할 때 주의할 점은 다음과 같습니다:

- **변경 불가**: 반복 중에 컬렉션을 수정하면 예외가 발생합니다. 이는 `foreach`가 내부적으로 컬렉션의 상태를 추적하기 때문입니다.
- **Nullable 타입**: `foreach` 문은 nullable 타입의 요소를 처리할 수 있지만, null 값이 있을 경우 주의가 필요합니다.
- **제네릭 컬렉션**: `List<T>`, `Dictionary<TKey, TValue>`와 같은 제네릭 컬렉션에서도 사용할 수 있으며, 더 강력한 타입 안전성을 제공합니다.

## 한 줄 요약
CSharp의 `foreach` 문은 배열 및 컬렉션의 요소를 손쉽게 반복할 수 있는 유용한 제어 구조입니다.