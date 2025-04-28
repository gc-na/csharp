<!--
Meta Description: # Từ Khóa "extern" trong C#: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `extern` trong C# được sử dụng để khai báo rằng một phương thức hoặc một biến ...
Meta Keywords: extern, dụng, các, trong, khóa
-->

# Từ Khóa "extern" trong C#: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `extern` trong C# được sử dụng để khai báo rằng một phương thức hoặc một biến được định nghĩa trong một ngôn ngữ khác (thường là C hoặc C++), cho phép tích hợp mã không phải C# vào trong ứng dụng C#.

## Tài Liệu

### Mục Đích
Từ khóa `extern` cho phép lập trình viên C# gọi các hàm hoặc sử dụng các biến được định nghĩa bên ngoài mã C#. Điều này thường hữu ích trong việc làm việc với thư viện DLL hoặc khi tương tác với mã gốc.

### Cách Sử Dụng
- Khai báo phương thức:
  ```csharp
  [DllImport("user32.dll")]
  public static extern int MessageBox(int hWnd, String text, String caption, uint type);
  ```

- Khai báo biến:
  ```csharp
  extern int myVariable;
  ```

Lưu ý rằng khi khai báo biến với từ khóa `extern`, bạn cần có định nghĩa cho biến đó ở một nơi khác.

### Chi Tiết
- Khi sử dụng từ khóa `extern`, bạn cần chú ý đến cách biên dịch và liên kết với các thư viện bên ngoài.
- Từ khóa `extern` chỉ có thể được sử dụng trong các phương thức tĩnh.
- C# không hỗ trợ nạp chồng (overloading) cho các phương thức extern. Điều này có nghĩa là bạn không thể có hai phương thức `extern` cùng tên với các tham số khác nhau.

## Ví Dụ

### Ví Dụ 1: Gọi Hàm từ Thư Viện DLL
```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("user32.dll")]
    public static extern int MessageBox(int hWnd, String text, String caption, uint type);

    static void Main()
    {
        MessageBox(0, "Hello, World!", "My Message Box", 0);
    }
}
```

### Ví Dụ 2: Khai Báo Biến extern
```csharp
class Example
{
    extern int myVariable;
    
    public void ShowVariable()
    {
        Console.WriteLine(myVariable);
    }
}
```

## Giải Thích
- **Điểm Cần Lưu Ý**: Việc gọi các hàm từ thư viện bên ngoài có thể gây ra lỗi nếu không đúng tham số hoặc không kiểm soát bộ nhớ tốt.
- **Khi Sử Dụng extern**: Luôn đảm bảo rằng bạn có quyền truy cập vào thư viện mà bạn đang gọi và kiểm tra kỹ các kiểu dữ liệu để tránh lỗi runtime.

## Tóm Tắt Một Dòng
Từ khóa `extern` trong C# cho phép gọi các phương thức và biến được định nghĩa trong ngôn ngữ khác, hỗ trợ tích hợp mã gốc vào ứng dụng C#.