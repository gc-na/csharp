<!--
Meta Description: # Từ khóa "out" trong C#: Cách sử dụng và ứng dụng ## Tóm tắt Từ khóa "out" trong C# cho phép bạn truyền tham số theo cách mà phương thức có thể gán g...
Meta Keywords: out, giá, trị, dụng, phương
-->

# Từ khóa "out" trong C#: Cách sử dụng và ứng dụng

## Tóm tắt
Từ khóa "out" trong C# cho phép bạn truyền tham số theo cách mà phương thức có thể gán giá trị cho nó và trả về nhiều giá trị từ một phương thức.

## Tài liệu
Từ khóa `out` được sử dụng trong C# để chỉ định rằng một tham số sẽ được truyền vào phương thức mà không cần khởi tạo trước giá trị. Tham số được đánh dấu bằng từ khóa `out` phải được gán giá trị bên trong phương thức trước khi nó được sử dụng. Điều này cho phép trả về nhiều giá trị từ một phương thức mà không cần phải sử dụng các kiểu dữ liệu phức tạp hoặc cấu trúc dữ liệu.

### Cú pháp
```csharp
void MethodName(out Type parameterName)
```

### Mục đích
- Trả về nhiều giá trị từ một phương thức.
- Giúp tối ưu hóa bộ nhớ khi không cần tạo đối tượng mới cho các giá trị trả về.

### Sử dụng
Khi sử dụng từ khóa `out`, bạn cần đảm bảo rằng tham số sẽ luôn được gán giá trị bên trong phương thức. Đây là một ví dụ đơn giản về cách sử dụng `out` trong C#:

```csharp
public void GetValues(out int a, out int b)
{
    a = 5; // Gán giá trị cho a
    b = 10; // Gán giá trị cho b
}
```

## Ví dụ
Dưới đây là một ví dụ cụ thể về cách sử dụng từ khóa `out`:

```csharp
using System;

class Program
{
    static void Main()
    {
        int x, y;
        GetValues(out x, out y);
        Console.WriteLine($"Giá trị x: {x}, Giá trị y: {y}");
    }

    static void GetValues(out int a, out int b)
    {
        a = 5;
        b = 10;
    }
}
```

Kết quả đầu ra sẽ là:
```
Giá trị x: 5, Giá trị y: 10
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng từ khóa `out`:
- Bạn không cần khởi tạo giá trị cho tham số `out` trước khi truyền vào phương thức, nhưng bạn phải gán giá trị cho nó bên trong phương thức.
- Nếu phương thức không gán giá trị cho tham số `out`, trình biên dịch sẽ báo lỗi.
- Từ khóa `out` có thể được sử dụng với bất kỳ kiểu dữ liệu nào, bao gồm kiểu dữ liệu cơ bản và kiểu dữ liệu do người dùng định nghĩa.

## Tóm tắt ngắn gọn
Từ khóa `out` trong C# cho phép phương thức trả về nhiều giá trị bằng cách truyền tham số mà không cần khởi tạo trước.