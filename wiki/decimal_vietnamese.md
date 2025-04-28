<!--
Meta Description: # Số Thập Phân (Decimal) trong C#: Tất Cả Những Gì Bạn Cần Biết ## Tóm Tắt Số thập phân (decimal) trong C# là một kiểu dữ liệu được sử dụng để lưu trữ...
Meta Keywords: các, decimal, chính, kiểu, toán
-->

# Số Thập Phân (Decimal) trong C#: Tất Cả Những Gì Bạn Cần Biết

## Tóm Tắt
Số thập phân (decimal) trong C# là một kiểu dữ liệu được sử dụng để lưu trữ các giá trị số có độ chính xác cao, thích hợp cho các phép toán tài chính và các ứng dụng cần tính toán chính xác.

## Tài Liệu
Kiểu dữ liệu `decimal` trong C# là một phần của không gian tên `System`. Nó được thiết kế để xử lý các số thập phân với độ chính xác cao hơn so với các kiểu số khác như `float` và `double`. Kiểu dữ liệu này có thể đại diện cho các số với độ chính xác lên đến 28-29 chữ số thập phân, giúp giảm thiểu lỗi trong các phép toán tài chính.

### Mục Đích
- Sử dụng cho các phép toán tài chính và các ứng dụng yêu cầu độ chính xác cao.
- Đảm bảo rằng các phép toán không bị ảnh hưởng bởi các lỗi làm tròn.

### Cách Sử Dụng
Để khai báo một biến kiểu `decimal`, bạn có thể sử dụng cú pháp sau:

```csharp
decimal myDecimal = 10.5m; // Chú ý ký tự 'm' ở cuối
```

Ký tự `m` hoặc `M` phải được thêm vào cuối số thập phân để chỉ định rằng đây là một giá trị kiểu `decimal`.

### Chi Tiết
- **Giá trị tối thiểu và tối đa**: `decimal` có giá trị tối thiểu là `-79,228,162,514,264,337,593,543,950,335` và tối đa là `79,228,162,514,264,337,593,543,950,335`.
- **Số nguyên và số thập phân**: `decimal` có thể được sử dụng để biểu diễn cả số nguyên và số thập phân.
- **Phép toán**: Hỗ trợ các phép toán như cộng, trừ, nhân và chia.

## Ví Dụ
```csharp
using System;

class Program
{
    static void Main()
    {
        decimal price = 19.99m;
        decimal tax = 0.07m;
        decimal total = price + (price * tax);
        
        Console.WriteLine($"Tổng số tiền: {total}");
    }
}
```

### Kết Quả:
```
Tổng số tiền: 21.39
```

## Giải Thích
- **Chú ý về ký tự 'm'**: Nếu bạn quên thêm ký tự `m`, trình biên dịch sẽ báo lỗi vì nó sẽ coi giá trị đó là kiểu dữ liệu khác (thường là `double`).
- **Lỗi làm tròn**: Dù `decimal` có độ chính xác cao, bạn vẫn nên cẩn thận trong các phép toán phức tạp, vì có thể có các trường hợp làm tròn không mong muốn.
- **Hiệu suất**: `decimal` chậm hơn so với các kiểu số khác như `float` và `double`, do đó nên sử dụng khi thực sự cần thiết.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `decimal` trong C# là giải pháp lý tưởng cho các phép toán tài chính với độ chính xác cao, giảm thiểu các lỗi làm tròn.