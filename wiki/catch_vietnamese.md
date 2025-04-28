<!--
Meta Description: # C# "catch": Cách Xử Lý Ngoại Lệ Trong Lập Trình ## Tóm Tắt Câu lệnh `catch` trong C# được sử dụng để xử lý các ngoại lệ (exceptions) xảy ra trong qu...
Meta Keywords: ngoại, catch, không, trong, dụng
-->

# C# "catch": Cách Xử Lý Ngoại Lệ Trong Lập Trình

## Tóm Tắt
Câu lệnh `catch` trong C# được sử dụng để xử lý các ngoại lệ (exceptions) xảy ra trong quá trình thực thi chương trình, giúp lập trình viên kiểm soát và quản lý lỗi một cách hiệu quả.

## Tài Liệu
Câu lệnh `catch` thường được sử dụng trong một khối `try-catch`, cho phép lập trình viên bắt và xử lý các ngoại lệ mà không làm gián đoạn quá trình thực thi của ứng dụng. Cấu trúc cơ bản của `try-catch` như sau:

```csharp
try
{
    // Mã lệnh có thể gây ra ngoại lệ
}
catch (ExceptionType e)
{
    // Xử lý ngoại lệ
}
```

### Mục Đích
Mục đích chính của `catch` là để bắt các ngoại lệ và thực hiện các hành động cần thiết, như ghi log, thông báo cho người dùng, hoặc thực hiện các thao tác phục hồi.

### Cách Sử Dụng
- Đặt mã lệnh có thể gây ra ngoại lệ trong khối `try`.
- Sử dụng một hoặc nhiều khối `catch` để xử lý các loại ngoại lệ khác nhau.
- Có thể sử dụng khối `finally` để thực hiện các thao tác dọn dẹp, như giải phóng tài nguyên, bất kể có xảy ra ngoại lệ hay không.

## Ví Dụ
### Ví dụ 1: Bắt Ngoại Lệ Chung
```csharp
try
{
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers[5]); // Gây ra ngoại lệ IndexOutOfRangeException
}
catch (IndexOutOfRangeException e)
{
    Console.WriteLine("Ngoại lệ: " + e.Message);
}
```

### Ví dụ 2: Nhiều Khối `catch`
```csharp
try
{
    int result = 10 / int.Parse("0"); // Gây ra ngoại lệ DivideByZeroException
}
catch (DivideByZeroException e)
{
    Console.WriteLine("Không thể chia cho 0: " + e.Message);
}
catch (FormatException e)
{
    Console.WriteLine("Giá trị không hợp lệ: " + e.Message);
}
```

### Ví dụ 3: Sử Dụng Khối `finally`
```csharp
try
{
    // Mã có thể gây ra ngoại lệ
    using (StreamReader sr = new StreamReader("file.txt"))
    {
        // Đọc nội dung file
    }
}
catch (FileNotFoundException e)
{
    Console.WriteLine("File không tồn tại: " + e.Message);
}
finally
{
    Console.WriteLine("Đã thực hiện xong khối try-catch.");
}
```

## Giải Thích
### Các Lỗi Thường Gặp
- **Không bắt ngoại lệ cụ thể**: Khi sử dụng `catch (Exception e)`, có thể bắt tất cả các ngoại lệ, nhưng nên xác định rõ loại ngoại lệ để xử lý chính xác hơn.
- **Bỏ qua ngoại lệ**: Không thực hiện hành động nào trong khối `catch` có thể dẫn đến khó khăn trong việc xác định nguyên nhân lỗi.
- **Chạy mã không an toàn**: Đảm bảo rằng mã trong khối `try` là an toàn và được kiểm tra, tránh gây ra ngoại lệ không mong muốn.

## Tóm Tắt Một Dòng
Câu lệnh `catch` trong C# giúp lập trình viên xử lý ngoại lệ một cách hiệu quả, bảo đảm rằng ứng dụng không bị gián đoạn bởi lỗi runtime.