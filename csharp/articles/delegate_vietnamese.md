<!--
Meta Description: # Delegate trong C#: Hiểu Biết Căn Bản và Ứng Dụng ## Tóm Tắt Delegate là một loại kiểu dữ liệu trong C# cho phép bạn lưu trữ và gọi các phương thức. ...
Meta Keywords: delegate, int, một, phương, thức
-->

# Delegate trong C#: Hiểu Biết Căn Bản và Ứng Dụng

## Tóm Tắt
Delegate là một loại kiểu dữ liệu trong C# cho phép bạn lưu trữ và gọi các phương thức. Nó hoạt động như một con trỏ đến phương thức, cho phép bạn truyền phương thức như một tham số.

## Tài Liệu
### Mục Đích
Delegate trong C# được sử dụng để tạo ra các loại hàm có thể được truyền qua các phương thức khác. Điều này rất hữu ích trong các tình huống như lập trình sự kiện và callback methods.

### Cách Sử Dụng
Để khai báo một delegate, bạn cần xác định kiểu trả về và danh sách tham số của phương thức mà delegate sẽ đại diện. Sau đó, bạn có thể tạo các thể hiện của delegate và gán cho chúng các phương thức tương ứng.

### Cấu Trúc
```csharp
// Khai báo delegate
public delegate int MyDelegate(int a, int b);

// Sử dụng delegate
public class DelegateExample
{
    public static int Add(int x, int y) => x + y;

    public static void Main()
    {
        // Tạo một thể hiện delegate
        MyDelegate del = new MyDelegate(Add);
        
        // Gọi phương thức thông qua delegate
        int result = del(10, 20);
        Console.WriteLine(result); // Kết quả: 30
    }
}
```

## Ví Dụ
### Ví Dụ 1: Delegate đơn giản
```csharp
public delegate void SimpleDelegate();

public class Program
{
    public static void Hello()
    {
        Console.WriteLine("Hello, World!");
    }

    public static void Main()
    {
        SimpleDelegate del = new SimpleDelegate(Hello);
        del(); // Kết quả: Hello, World!
    }
}
```

### Ví Dụ 2: Delegate với tham số
```csharp
public delegate int MathOperation(int a, int b);

public class Program
{
    public static int Multiply(int x, int y) => x * y;

    public static void Main()
    {
        MathOperation op = new MathOperation(Multiply);
        int result = op(5, 6);
        Console.WriteLine(result); // Kết quả: 30
    }
}
```

## Giải Thích
- **Common Pitfalls**: Một số lập trình viên mới có thể nhầm lẫn delegate với các phương thức thông thường. Delegate không chỉ đơn giản là một phương thức; nó có thể đại diện cho nhiều phương thức cùng loại.
  
- **Đối tượng null**: Khi gọi một delegate, nếu delegate không được gán một phương thức, việc gọi sẽ gây ra một lỗi `NullReferenceException`.

- **Sự kiện**: Delegate là nền tảng cho việc xây dựng các sự kiện trong C#. Mỗi sự kiện thực chất là một delegate.

## Tóm Tắt Một Dòng
Delegate trong C# là một công cụ mạnh mẽ cho phép bạn lưu trữ và gọi các phương thức, hỗ trợ lập trình sự kiện và callback methods.