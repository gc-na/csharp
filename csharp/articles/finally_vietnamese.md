<!--
Meta Description: # CSharp: Từ Khóa "finally" trong Xử Lý Ngoại Lệ ## Tóm Tắt Từ khóa `finally` trong C# được sử dụng trong cấu trúc xử lý ngoại lệ để đảm bảo rằng một ...
Meta Keywords: finally, trong, khối, được, ngoại
-->

# CSharp: Từ Khóa "finally" trong Xử Lý Ngoại Lệ

## Tóm Tắt
Từ khóa `finally` trong C# được sử dụng trong cấu trúc xử lý ngoại lệ để đảm bảo rằng một khối mã sẽ được thực hiện sau khi khối `try` và `catch` kết thúc, bất kể có xảy ra ngoại lệ hay không.

## Tài Liệu
Từ khóa `finally` là một phần quan trọng trong việc quản lý ngoại lệ trong C#. Nó được sử dụng trong một khối `try-catch` để đảm bảo rằng mã bên trong khối `finally` sẽ luôn được thực hiện, cho dù có xảy ra lỗi hay không. Điều này rất hữu ích cho các tác vụ dọn dẹp, như đóng kết nối cơ sở dữ liệu hoặc giải phóng tài nguyên.

### Cú Pháp
```csharp
try
{
    // Khối mã có thể gây ra ngoại lệ
}
catch (Exception ex)
{
    // Xử lý ngoại lệ
}
finally
{
    // Khối mã luôn được thực hiện
}
```

### Mục Đích
- Đảm bảo mã trong khối `finally` luôn được thực thi.
- Giúp dọn dẹp tài nguyên hoặc thực hiện các hành động cần thiết sau khi hoàn tất xử lý ngoại lệ.

## Ví Dụ
### Ví Dụ Cơ Bản
```csharp
using System;

class Program
{
    static void Main()
    {
        try
        {
            Console.WriteLine("Nhập số nguyên:");
            int number = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Số bạn đã nhập là: " + number);
        }
        catch (FormatException)
        {
            Console.WriteLine("Đã xảy ra lỗi: Vui lòng nhập một số nguyên.");
        }
        finally
        {
            Console.WriteLine("Khối finally đã được thực hiện.");
        }
    }
}
```

### Ví Dụ Với Tài Nguyên
```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        FileStream fileStream = null;
        try
        {
            fileStream = new FileStream("example.txt", FileMode.Open);
            // Đọc dữ liệu từ file
        }
        catch (FileNotFoundException)
        {
            Console.WriteLine("File không tồn tại.");
        }
        finally
        {
            if (fileStream != null)
            {
                fileStream.Close();
                Console.WriteLine("File đã được đóng.");
            }
        }
    }
}
```

## Giải Thích
Một số điểm cần lưu ý khi sử dụng `finally`:
- Khối `finally` sẽ được thực hiện ngay cả khi có một lệnh `return` trong khối `try` hoặc `catch`.
- Nếu có một ngoại lệ không được xử lý trong khối `try`, khối `finally` vẫn sẽ được thực thi.
- Tránh đặt mã có thể phát sinh ngoại lệ trong khối `finally`, vì điều này có thể dẫn đến khó khăn trong việc phát hiện và xử lý ngoại lệ.

## Tóm Tắt Một Dòng
Từ khóa `finally` trong C# đảm bảo rằng mã dọn dẹp sẽ luôn được thực thi sau khi hoàn thành xử lý ngoại lệ, bất kể có xảy ra lỗi hay không.