<!--
Meta Description: # Sử Dụng Lệnh "typeof" Trong CSharp: Hướng Dẫn Chi Tiết ## Tóm tắt Lệnh `typeof` trong CSharp cho phép bạn lấy kiểu dữ liệu của một lớp, cấu trúc, gi...
Meta Keywords: liệu, kiểu, typeof, một, type
-->

# Sử Dụng Lệnh "typeof" Trong CSharp: Hướng Dẫn Chi Tiết

## Tóm tắt
Lệnh `typeof` trong CSharp cho phép bạn lấy kiểu dữ liệu của một lớp, cấu trúc, giao diện hoặc kiểu dữ liệu cơ bản tại thời điểm biên dịch. Đây là một công cụ mạnh mẽ giúp xác định và làm việc với kiểu dữ liệu trong lập trình hướng đối tượng.

## Tài Liệu
Lệnh `typeof` được sử dụng để trả về một đối tượng `Type`, đại diện cho kiểu dữ liệu của một lớp hoặc cấu trúc cụ thể. Điều này rất hữu ích khi bạn cần kiểm tra kiểu dữ liệu hoặc khi làm việc với phản xạ (reflection) trong CSharp.

### Cú pháp
```csharp
Type type = typeof(T);
```
Trong đó `T` là tên kiểu dữ liệu bạn muốn kiểm tra.

### Mục đích
- Xác định kiểu dữ liệu tại thời điểm biên dịch.
- Hỗ trợ trong việc kiểm tra kiểu dữ liệu động.
- Làm việc với phản xạ để truy cập thông tin về kiểu dữ liệu.

### Sử dụng
Khi bạn cần lấy thông tin về một kiểu dữ liệu, bạn có thể sử dụng `typeof` trong nhiều tình huống như:
- Kiểm tra kiểu dữ liệu của biến.
- Tạo các đối tượng dựa trên kiểu dữ liệu.
- Lưu trữ kiểu dữ liệu trong các cấu trúc dữ liệu như dictionary.

## Ví Dụ
### Ví dụ 1: Lấy kiểu dữ liệu của một lớp
```csharp
using System;

class Program
{
    static void Main()
    {
        Type type = typeof(string);
        Console.WriteLine(type); // Kết quả: System.String
    }
}
```

### Ví dụ 2: Sử dụng với các kiểu dữ liệu tùy chỉnh
```csharp
public class Person
{
    public string Name { get; set; }
}

class Program
{
    static void Main()
    {
        Type type = typeof(Person);
        Console.WriteLine(type); // Kết quả: YourNamespace.Person
    }
}
```

### Ví dụ 3: Kiểm tra kiểu dữ liệu tại thời điểm chạy
```csharp
class Program
{
    static void Main()
    {
        object obj = "Hello, World!";
        Type type = obj.GetType();
        Console.WriteLine(type); // Kết quả: System.String
    }
}
```

## Giải Thích
Khi sử dụng `typeof`, một số lưu ý cần nhớ:
- `typeof` chỉ hoạt động với các kiểu dữ liệu đã được xác định tại thời điểm biên dịch và không thể sử dụng với các biến.
- Nếu bạn cần xác định kiểu dữ liệu của một biến tại thời điểm chạy, hãy sử dụng phương thức `GetType()` của đối tượng.
- Tránh nhầm lẫn giữa `typeof` và `is`. `is` được sử dụng để kiểm tra xem một đối tượng có phải là một kiểu dữ liệu cụ thể hay không, trong khi `typeof` trả về kiểu dữ liệu của một loại cụ thể.

## Tóm tắt một dòng
Lệnh `typeof` trong CSharp cho phép bạn lấy kiểu dữ liệu của lớp hoặc cấu trúc tại thời điểm biên dịch, hữu ích cho việc kiểm tra và làm việc với kiểu dữ liệu trong lập trình.