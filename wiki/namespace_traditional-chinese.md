<!--
Meta Description: # C# 命名空間（namespace）詳細介紹 ## 簡介 在 C# 程式設計中，命名空間（namespace）是一種用來組織和管理類別、結構和其他類型的方式。透過命名空間，開發者可以避免命名衝突，並提高程式碼的可讀性和可維護性。 ## 文檔 ### 目的 命名空間的主要目的是將程式中的類別和其他...
Meta Keywords: namespace, class, csharp, using, static
-->

# C# 命名空間（namespace）詳細介紹

## 簡介
在 C# 程式設計中，命名空間（namespace）是一種用來組織和管理類別、結構和其他類型的方式。透過命名空間，開發者可以避免命名衝突，並提高程式碼的可讀性和可維護性。

## 文檔
### 目的
命名空間的主要目的是將程式中的類別和其他型別進行分組，使其在邏輯上更具組織性。這對於大型應用程式特別重要，因為它們通常會包含大量的類別和功能。

### 使用方式
命名空間是透過 `namespace` 關鍵字來定義的。其基本語法如下：

```csharp
namespace NamespaceName
{
    // 類別定義
    class ClassName
    {
        // 成員定義
    }
}
```

在程式碼中使用命名空間需要透過 `using` 指令來導入，例如：

```csharp
using NamespaceName;

class Program
{
    static void Main(string[] args)
    {
        ClassName instance = new ClassName();
    }
}
```

### 詳細說明
1. **嵌套命名空間**：C# 允許命名空間的嵌套，這樣可以進一步細分類別。例如：
    ```csharp
    namespace OuterNamespace
    {
        namespace InnerNamespace
        {
            class InnerClass
            {
            }
        }
    }
    ```

2. **全域命名空間**：如果沒有指定命名空間，則類別會自動放置於全域命名空間中。

3. **命名衝突**：在不同的命名空間中可以有相同名稱的類別，這樣可以避免命名衝突。例如：
    ```csharp
    namespace NamespaceA
    {
        class SampleClass
        {
        }
    }

    namespace NamespaceB
    {
        class SampleClass
        {
        }
    }
    ```

## 範例
以下是使用命名空間的基本範例：

```csharp
namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }

    class Helper
    {
        public static void Greet()
        {
            Console.WriteLine("Greetings from Helper!");
        }
    }
}
```

在使用時，可以這樣導入：

```csharp
using MyApplication;

class Test
{
    static void Main()
    {
        Helper.Greet();
    }
}
```

## 說明
- **常見陷阱**：開發者在使用命名空間時，容易忽略 `using` 指令的順序，這可能導致找不到類別或命名衝突。
- **命名慣例**：建議使用公司名稱或專案名稱作為命名空間的前綴，以避免日後的衝突。
- **可讀性**：合理使用命名空間可以提高程式碼的可讀性，使其他開發者更容易理解程式的結構。

## 一句話總結
C# 的命名空間是一種組織程式碼的工具，可以有效避免命名衝突並提高可讀性。