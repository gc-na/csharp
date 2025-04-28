<!--
Meta Description: # C# Switch: Cấu Trúc Điều Kiện Linh Hoạt trong Lập Trình ## Tóm Tắt Cấu trúc `switch` trong C# là một công cụ mạnh mẽ cho phép lập trình viên thực hi...
Meta Keywords: break, case, không, console, writeline
-->

# C# Switch: Cấu Trúc Điều Kiện Linh Hoạt trong Lập Trình

## Tóm Tắt
Cấu trúc `switch` trong C# là một công cụ mạnh mẽ cho phép lập trình viên thực hiện các lựa chọn điều kiện dựa trên giá trị của một biểu thức. Nó giúp làm cho mã nguồn trở nên rõ ràng và dễ bảo trì hơn so với việc sử dụng nhiều câu lệnh `if`.

## Tài liệu
Cấu trúc `switch` trong C# được sử dụng để chọn một khối mã để thực thi dựa trên giá trị của một biến. Cú pháp tổng quát của nó như sau:

```csharp
switch (biến)
{
    case giá_trị1:
        // Khối lệnh cho giá trị1
        break;
    case giá_trị2:
        // Khối lệnh cho giá trị2
        break;
    default:
        // Khối lệnh nếu không khớp với bất kỳ giá trị nào
        break;
}
```

### Mục Đích
Mục đích của `switch` là để thay thế cho các câu lệnh `if-else` phức tạp, giúp cho mã nguồn dễ đọc hơn khi có nhiều điều kiện cần kiểm tra.

### Cách Sử Dụng
- **Biến**: Biến được kiểm tra có thể là một số nguyên, ký tự, chuỗi hoặc bất kỳ kiểu dữ liệu nào có thể so sánh.
- **Các case**: Mỗi `case` đại diện cho một giá trị cụ thể mà biến có thể nhận. Nếu khớp với giá trị, khối lệnh tương ứng sẽ được thực thi.
- **default**: Tùy chọn này cho phép bạn chỉ định khối lệnh sẽ được thực thi nếu không có trường hợp nào khớp.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng `switch` trong C#:

### Ví Dụ 1: Kiểm Tra Ngày Trong Tuần
```csharp
int ngay = 3;
switch (ngay)
{
    case 1:
        Console.WriteLine("Thứ Hai");
        break;
    case 2:
        Console.WriteLine("Thứ Ba");
        break;
    case 3:
        Console.WriteLine("Thứ Tư");
        break;
    case 4:
        Console.WriteLine("Thứ Năm");
        break;
    case 5:
        Console.WriteLine("Thứ Sáu");
        break;
    case 6:
        Console.WriteLine("Thứ Bảy");
        break;
    case 7:
        Console.WriteLine("Chủ Nhật");
        break;
    default:
        Console.WriteLine("Không hợp lệ");
        break;
}
```

### Ví Dụ 2: Sử Dụng Chuỗi
```csharp
string thang = "Tháng Mười";
switch (thang)
{
    case "Tháng Một":
        Console.WriteLine("Đầu năm");
        break;
    case "Tháng Mười":
        Console.WriteLine("Giữa năm");
        break;
    default:
        Console.WriteLine("Tháng không xác định");
        break;
}
```

## Giải Thích
### Cạm Bẫy Thường Gặp
1. **Quên `break`**: Nếu bạn quên lệnh `break`, chương trình sẽ tiếp tục thực thi các case phía dưới, điều này có thể dẫn đến kết quả không mong muốn.
2. **Không sử dụng `default`**: Khi không có `default`, nếu không có trường hợp nào khớp, không có hành động nào được thực hiện, có thể gây khó khăn trong việc xử lý lỗi.
3. **Kiểu dữ liệu không tương thích**: Mỗi `case` cần phải tương thích với kiểu dữ liệu của biến đang kiểm tra. Nếu không, bạn sẽ gặp lỗi biên dịch.

## Tóm Tắt Một Dòng
Cấu trúc `switch` trong C# cho phép lập trình viên thực hiện lựa chọn điều kiện một cách linh hoạt và rõ ràng dựa trên giá trị của biến.