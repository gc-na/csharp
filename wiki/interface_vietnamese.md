<!--
Meta Description: # Giao Diện (Interface) trong CSharp: Lập Trình Hướng Đối Tượng ## Tóm Tắt Giao diện (Interface) trong CSharp là một loại kiểu dữ liệu đặc biệt cho ph...
Meta Keywords: diện, giao, các, lớp, public
-->

# Giao Diện (Interface) trong CSharp: Lập Trình Hướng Đối Tượng

## Tóm Tắt
Giao diện (Interface) trong CSharp là một loại kiểu dữ liệu đặc biệt cho phép định nghĩa một tập hợp các phương thức và thuộc tính mà các lớp con phải thực hiện, giúp tạo ra mã nguồn linh hoạt và dễ bảo trì.

## Tài Liệu
Giao diện trong CSharp được sử dụng để xác định các phương thức mà một lớp cần phải triển khai mà không cung cấp chi tiết thực thi. Giao diện không chứa bất kỳ mã thực thi nào; thay vào đó, nó chỉ định nghĩa cấu trúc mà các lớp thực hiện phải tuân theo. 

### Mục Đích
- **Tính kế thừa đa hình:** Giao diện cho phép một lớp thực hiện nhiều giao diện, giúp giảm thiểu ràng buộc giữa các lớp.
- **Tách biệt các yếu tố:** Giao diện giúp phân tách các yếu tố khác nhau trong mã nguồn, cải thiện khả năng bảo trì và đọc hiểu.
- **Thúc đẩy sự trừu tượng:** Giao diện cho phép tập trung vào những gì cần làm thay vì cách thực hiện.

### Cú Pháp
```csharp
public interface IGiaoDien
{
    void PhuongThuc1();
    int PhuongThuc2(string thamSo);
}
```

## Ví Dụ
Dưới đây là một số ví dụ minh họa về cách sử dụng giao diện trong CSharp:

### Ví dụ 1: Định nghĩa và triển khai giao diện
```csharp
public interface IShape
{
    double Area();
}

public class HinhTron : IShape
{
    public double Radius { get; set; }
    
    public double Area()
    {
        return Math.PI * Radius * Radius;
    }
}

public class HinhVuong : IShape
{
    public double Side { get; set; }
    
    public double Area()
    {
        return Side * Side;
    }
}
```

### Ví dụ 2: Sử dụng giao diện
```csharp
IShape hinhTron = new HinhTron { Radius = 5 };
IShape hinhVuong = new HinhVuong { Side = 4 };

Console.WriteLine($"Diện tích hình tròn: {hinhTron.Area()}");
Console.WriteLine($"Diện tích hình vuông: {hinhVuong.Area()}");
```

## Giải Thích
### Những điểm cần lưu ý
- **Tính kế thừa:** Một lớp có thể thực hiện nhiều giao diện, nhưng giao diện không thể kế thừa từ lớp.
- **Cấu trúc giao diện:** Tất cả các phương thức trong giao diện đều tự động là `public` và không có thân phương thức.
- **Không chứa thuộc tính:** Giao diện không thể chứa bất kỳ thuộc tính nào có giá trị. Từ C# 8.0, giao diện có thể chứa các phương thức mặc định, nhưng các phương thức này vẫn không thể chứa bất kỳ trạng thái.

### Một số lỗi thường gặp
- Không triển khai tất cả các phương thức của giao diện trong lớp con sẽ gây ra lỗi biên dịch.
- Quên khai báo lớp thực hiện giao diện là `public` có thể dẫn đến sự cố truy cập.

## Tóm Tắt Một Dòng
Giao diện trong CSharp là công cụ mạnh mẽ giúp định nghĩa các phương thức mà các lớp cần triển khai, thúc đẩy tính linh hoạt và bảo trì cho mã nguồn.