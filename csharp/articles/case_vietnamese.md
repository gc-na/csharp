<!--
Meta Description: # Từ Khóa "case" trong C#: Hướng Dẫn Chi Tiết và Ví Dụ Sử Dụng ## Tóm tắt Từ khóa "case" trong C# được sử dụng trong cấu trúc điều kiện switch để xác ...
Meta Keywords: case, giá, trị, break, switch
-->

# Từ Khóa "case" trong C#: Hướng Dẫn Chi Tiết và Ví Dụ Sử Dụng

## Tóm tắt
Từ khóa "case" trong C# được sử dụng trong cấu trúc điều kiện switch để xác định các nhánh khác nhau dựa trên giá trị của một biểu thức.

## Tài liệu
Từ khóa "case" là một phần không thể thiếu trong cấu trúc switch của C#, cho phép lập trình viên kiểm tra giá trị của một biến và thực hiện các hành động khác nhau tùy thuộc vào giá trị đó. Cấu trúc này rất hữu ích khi có nhiều điều kiện khác nhau cần được xử lý.

### Cú pháp cơ bản
```csharp
switch (biến)
{
    case giá_trị_1:
        // Thực hiện hành động cho giá trị 1
        break;
    case giá_trị_2:
        // Thực hiện hành động cho giá trị 2
        break;
    default:
        // Hành động cho các trường hợp không khớp
        break;
}
```

### Mục đích
- Tổ chức mã nguồn một cách rõ ràng hơn so với việc sử dụng nhiều câu lệnh if-else.
- Giúp cải thiện hiệu suất khi so sánh nhiều giá trị.

### Sử dụng
Từ khóa "case" được sử dụng bên trong khối switch. Mỗi trường hợp được xác định bằng từ khóa "case", theo sau là giá trị mà biến cần kiểm tra. Sau mỗi trường hợp, bạn có thể thêm mã lệnh để thực hiện.

## Ví dụ
### Ví dụ 1: Cấu trúc switch đơn giản
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
    default:
        Console.WriteLine("Ngày không hợp lệ");
        break;
}
```

### Ví dụ 2: Sử dụng nhiều giá trị trong một case
```csharp
char kyTu = 'A';

switch (kyTu)
{
    case 'A':
    case 'E':
    case 'I':
    case 'O':
    case 'U':
        Console.WriteLine("Đây là nguyên âm");
        break;
    default:
        Console.WriteLine("Đây là phụ âm");
        break;
}
```

## Giải thích
- **Nhầm lẫn với câu lệnh if-else**: Mặc dù cấu trúc switch có thể thay thế cho nhiều câu lệnh if-else, nhưng không phải lúc nào cũng là lựa chọn tốt nhất, đặc biệt nếu điều kiện kiểm tra phức tạp.
- **Quên từ khóa break**: Nếu bạn không sử dụng từ khóa `break`, chương trình sẽ tiếp tục thực hiện các nhánh case tiếp theo, có thể dẫn đến kết quả không mong muốn.
- **Giá trị không khớp**: Nếu không có case nào khớp với giá trị, khối `default` sẽ được thực hiện nếu có.

## Tóm tắt một dòng
Từ khóa "case" trong C# cho phép bạn xác định các nhánh khác nhau trong cấu trúc switch dựa trên giá trị của một biến, giúp mã nguồn trở nên rõ ràng và dễ quản lý hơn.