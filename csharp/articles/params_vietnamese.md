<!--
Meta Description: # Sử Dụng Từ Khóa "params" Trong CSharp: Tối Ưu Hóa Tham Số Trong Phương Thức ## Tóm Tắt Từ khóa `params` trong CSharp cho phép bạn truyền một số lượn...
Meta Keywords: params, tham, một, phương, thức
-->

# Sử Dụng Từ Khóa "params" Trong CSharp: Tối Ưu Hóa Tham Số Trong Phương Thức

## Tóm Tắt
Từ khóa `params` trong CSharp cho phép bạn truyền một số lượng tham số không xác định vào một phương thức. Điều này giúp tăng tính linh hoạt và tiện lợi trong việc xử lý các tham số.

## Tài Liệu
Từ khóa `params` được sử dụng trong CSharp để cho phép một phương thức nhận một danh sách tham số có kích thước thay đổi. Tham số được định nghĩa với từ khóa `params` phải là tham số cuối cùng trong danh sách tham số của phương thức. Điều này có nghĩa là bạn có thể truyền vào một mảng hoặc truyền nhiều giá trị riêng lẻ mà không cần phải tạo một mảng riêng.

**Cú Pháp:**
```csharp
public void PhuongThuc(params int[] giaTri)
{
    // Thao tác với giaTri
}
```

### Mục Đích
Mục đích chính của từ khóa `params` là để đơn giản hóa việc truyền một danh sách tham số vào phương thức mà không cần phải khai báo mảng thủ công. Điều này làm giảm độ phức tạp trong mã nguồn và giúp tăng tính dễ đọc.

### Cách Sử Dụng
- Khi khai báo phương thức, bạn có thể chỉ định một tham số với từ khóa `params` theo sau là kiểu dữ liệu và mảng.
- Bạn có thể gọi phương thức với bất kỳ số lượng tham số nào, bao gồm cả không có tham số nào.

## Ví Dụ
### Ví Dụ Cơ Bản 1: Sử Dụng params Với Số Nguyên
```csharp
public void Tong(params int[] soNguyen)
{
    int tong = 0;
    foreach (var so in soNguyen)
    {
        tong += so;
    }
    Console.WriteLine("Tổng: " + tong);
}

// Gọi phương thức
Tong(1, 2, 3, 4); // Kết quả: Tổng: 10
```

### Ví Dụ Cơ Bản 2: Sử Dụng params Với Chuỗi
```csharp
public void InRa(params string[] chuoi)
{
    foreach (var str in chuoi)
    {
        Console.WriteLine(str);
    }
}

// Gọi phương thức
InRa("Xin chào", "CSharp", "params"); 
// Kết quả:
// Xin chào
// CSharp
// params
```

## Giải Thích
Mặc dù `params` mang lại nhiều lợi ích, nhưng cũng có một số cạm bẫy mà bạn cần lưu ý:

- **Chỉ Định Cuối Cùng**: Tham số `params` phải luôn là tham số cuối cùng trong danh sách tham số của phương thức. Nếu không, biên dịch sẽ báo lỗi.
  
- **Kiểu Dữ Liệu**: Bạn chỉ có thể sử dụng `params` với một loại dữ liệu duy nhất. Nếu bạn cần truyền nhiều kiểu dữ liệu, bạn sẽ cần phải sử dụng một lớp hoặc cấu trúc khác.

- **Mảng Rỗng**: Nếu bạn không truyền bất kỳ tham số nào, phương thức vẫn có thể gọi được nhưng sẽ nhận một mảng rỗng.

## Tóm Tắt Một Dòng
Từ khóa `params` trong CSharp cho phép truyền một danh sách tham số có số lượng linh hoạt vào phương thức, giúp mã nguồn dễ đọc và quản lý hơn.