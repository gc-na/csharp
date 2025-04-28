<!--
Meta Description: # Từ Khóa "checked" trong C#: Kiểm Soát Tràn Số ## Tóm Tắt Từ khóa `checked` trong C# được sử dụng để kiểm soát việc tràn số trong các phép toán số họ...
Meta Keywords: checked, phép, dụng, các, toán
-->

# Từ Khóa "checked" trong C#: Kiểm Soát Tràn Số

## Tóm Tắt
Từ khóa `checked` trong C# được sử dụng để kiểm soát việc tràn số trong các phép toán số học, giúp lập trình viên nhận diện và xử lý các lỗi phát sinh do tràn số.

## Tài Liệu
Từ khóa `checked` cho phép lập trình viên kiểm tra xem một phép toán số học có gây ra tràn số hay không. Khi sử dụng `checked`, nếu kết quả của phép toán vượt quá giới hạn của kiểu dữ liệu, một ngoại lệ `OverflowException` sẽ được ném ra, giúp người lập trình dễ dàng phát hiện và xử lý lỗi.

### Cú Pháp
```csharp
checked
{
    // Các phép toán số học ở đây
}
```

Hoặc có thể sử dụng `checked` với các phép toán đơn lẻ:
```csharp
int result = checked(a + b);
```

### Mục Đích
`checked` được sử dụng trong các tình huống mà an toàn về số học là rất quan trọng, ví dụ như trong các ứng dụng tài chính hoặc khoa học, nơi mà độ chính xác của phép toán là cần thiết.

## Ví Dụ
### Ví dụ 1: Sử dụng `checked` với khối mã
```csharp
int a = int.MaxValue;
int b = 1;
try
{
    checked
    {
        int result = a + b; // Gây ra OverflowException
    }
}
catch (OverflowException ex)
{
    Console.WriteLine("Tràn số: " + ex.Message);
}
```

### Ví dụ 2: Sử dụng `checked` với phép toán đơn lẻ
```csharp
int a = 1000000000;
int b = 2000000000;
try
{
    int result = checked(a * b); // Gây ra OverflowException
}
catch (OverflowException ex)
{
    Console.WriteLine("Tràn số: " + ex.Message);
}
```

## Giải Thích
Một số điểm cần lưu ý khi sử dụng `checked`:

- **Hiệu suất**: Việc kiểm tra tràn số có thể làm giảm hiệu suất, vì vậy nên sử dụng `checked` chỉ trong những phần mã cần thiết.
- **Phạm vi áp dụng**: `checked` chỉ áp dụng cho các phép toán số học, không áp dụng cho các phép toán khác như phép so sánh hay phép gán.
- **Kết hợp với `unchecked`**: Bạn có thể kết hợp `checked` với `unchecked` để kiểm soát các vùng mã mà bạn muốn kiểm tra hoặc không kiểm tra tràn số.

## Tóm Tắt Một Dòng
Từ khóa `checked` trong C# giúp phát hiện và xử lý các lỗi tràn số trong các phép toán số học để đảm bảo tính chính xác của chương trình.