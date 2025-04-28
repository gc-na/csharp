<!--
Meta Description: # Kiểu Dữ Liệu int trong C# - Hướng Dẫn Chi Tiết ## Tóm Tắt Kiểu dữ liệu `int` trong C# là một trong những kiểu dữ liệu cơ bản, dùng để lưu trữ các số...
Meta Keywords: int, kiểu, liệu, các, trong
-->

# Kiểu Dữ Liệu int trong C# - Hướng Dẫn Chi Tiết

## Tóm Tắt
Kiểu dữ liệu `int` trong C# là một trong những kiểu dữ liệu cơ bản, dùng để lưu trữ các số nguyên với phạm vi từ -2,147,483,648 đến 2,147,483,647. Đây là kiểu dữ liệu phổ biến trong lập trình, thường được sử dụng để thực hiện các phép toán số học.

## Tài Liệu
Kiểu dữ liệu `int` trong C# là một kiểu dữ liệu nguyên 32-bit có dấu. `int` được sử dụng rộng rãi trong lập trình để lưu trữ các giá trị số nguyên, từ các chỉ số trong mảng đến các biến kiểm soát vòng lặp và nhiều hơn nữa. Để khai báo một biến kiểu `int`, bạn có thể sử dụng cú pháp sau:

```csharp
int tenBien;
```

### Đặc Điểm
- **Phạm Vi Giá Trị**: Từ -2,147,483,648 đến 2,147,483,647.
- **Kích Thước**: 4 byte (32 bit).
- **Sử Dụng**: Thích hợp cho các phép toán số học, so sánh, và các tác vụ liên quan đến số nguyên.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về việc sử dụng kiểu dữ liệu `int`:

### Ví Dụ 1: Khai Báo và Gán Giá Trị
```csharp
int soNguyen = 10;
Console.WriteLine(soNguyen); // Kết quả: 10
```

### Ví Dụ 2: Phép Toán Số Học
```csharp
int a = 5;
int b = 3;
int tong = a + b;
Console.WriteLine(tong); // Kết quả: 8
```

### Ví Dụ 3: Vòng Lặp Sử Dụng int
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i); // Kết quả: 0 1 2 3 4
}
```

## Giải Thích
Khi làm việc với kiểu dữ liệu `int`, có một số điều cần lưu ý:

- **Tràn Số**: Khi giá trị vượt quá phạm vi cho phép, sẽ xảy ra hiện tượng tràn số, có thể gây ra lỗi hoặc kết quả không mong muốn.
- **Chuyển Đổi Kiểu**: Nếu bạn cần lưu trữ các số lớn hơn, bạn có thể xem xét các kiểu dữ liệu khác như `long` hoặc `decimal`.
- **Khởi Tạo**: Biến `int` có thể được khởi tạo với giá trị mặc định là 0 nếu không được gán giá trị cụ thể.

## Tóm Tắt Một Câu
Kiểu dữ liệu `int` trong C# là kiểu dữ liệu cơ bản dùng để lưu trữ và xử lý các số nguyên với phạm vi từ -2,147,483,648 đến 2,147,483,647.