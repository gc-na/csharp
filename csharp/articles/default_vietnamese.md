<!--
Meta Description: # Từ Khóa "default" trong C#: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `default` trong C# được sử dụng để khởi tạo giá trị mặc định cho một kiểu dữ ...
Meta Keywords: kiểu, default, liệu, dụng, giá
-->

# Từ Khóa "default" trong C#: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `default` trong C# được sử dụng để khởi tạo giá trị mặc định cho một kiểu dữ liệu, đặc biệt hữu ích trong các cấu trúc dữ liệu như mảng, danh sách hoặc khi sử dụng generic.

## Tài Liệu
Từ khóa `default` trong C# được dùng để lấy giá trị mặc định của một kiểu dữ liệu. Nó có thể được sử dụng với tất cả các kiểu dữ liệu, bao gồm cả kiểu giá trị và kiểu tham chiếu. Giá trị mặc định cho các kiểu dữ liệu như sau:

- Đối với kiểu giá trị (như `int`, `float`, `bool`), giá trị mặc định là 0, 0.0, và false tương ứng.
- Đối với kiểu tham chiếu (như `string`, `class`), giá trị mặc định là `null`.
- Đối với các kiểu dữ liệu tùy chỉnh (class), giá trị mặc định là một thể hiện mới của class đó với tất cả các trường được khởi tạo tới giá trị mặc định của chúng.

Cú pháp sử dụng `default` như sau:

```csharp
T value = default(T);
```

Trong đó `T` là kiểu dữ liệu. 

## Ví Dụ
### Ví dụ 1: Sử dụng với kiểu giá trị
```csharp
int defaultValue = default(int); // defaultValue sẽ là 0
```

### Ví dụ 2: Sử dụng với kiểu tham chiếu
```csharp
string defaultString = default(string); // defaultString sẽ là null
```

### Ví dụ 3: Sử dụng với kiểu dữ liệu tùy chỉnh
```csharp
public class Person
{
    public string Name;
    public int Age;
}

Person defaultPerson = default(Person); // defaultPerson sẽ là null
```

### Ví dụ 4: Sử dụng trong Generic
```csharp
public T GetDefaultValue<T>()
{
    return default(T);
}

// Sử dụng
int value = GetDefaultValue<int>(); // value sẽ là 0
string text = GetDefaultValue<string>(); // text sẽ là null
```

## Giải Thích
Khi sử dụng từ khóa `default`, có một số điểm cần chú ý:

- `default` có thể gây nhầm lẫn nếu không hiểu rõ về kiểu dữ liệu. Chẳng hạn, với kiểu tham chiếu, `default` sẽ trả về `null`, điều này có thể dẫn đến lỗi khi cố gắng truy cập các thuộc tính của đối tượng mà không được kiểm tra.
- Trong trường hợp kiểu dữ liệu là nullable, giá trị mặc định sẽ là `null`, nhưng cần phân biệt giữa `null` và `default(T)` cho các kiểu dữ liệu không nullable.
- Khi sử dụng trong các phương thức generic, `default` trở thành một công cụ mạnh mẽ giúp bạn khởi tạo các biến mà không cần phải biết trước kiểu dữ liệu.

## Tóm Tắt Một Dòng
Từ khóa `default` trong C# cho phép khởi tạo giá trị mặc định cho các kiểu dữ liệu, giúp quản lý và sử dụng hiệu quả các biến trong lập trình.