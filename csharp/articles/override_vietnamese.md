<!--
Meta Description: # Override trong C#: Tìm Hiểu và Cách Sử Dụng ## Tóm tắt Từ khóa `override` trong C# cho phép một lớp con cung cấp triển khai riêng của một phương thứ...
Meta Keywords: lớp, dụng, phương, thức, trong
-->

# Override trong C#: Tìm Hiểu và Cách Sử Dụng

## Tóm tắt
Từ khóa `override` trong C# cho phép một lớp con cung cấp triển khai riêng của một phương thức đã được định nghĩa trong lớp cha, giúp tăng cường khả năng tùy biến và mở rộng của mã nguồn.

## Tài liệu
### Mục đích
Từ khóa `override` được sử dụng để ghi đè một phương thức (hoặc thuộc tính) đã được khai báo là `virtual`, `abstract`, hoặc `override` trong lớp cha. Điều này cho phép lớp con thay đổi hành vi của phương thức đó mà không thay đổi lớp cha.

### Cách sử dụng
Để sử dụng `override`, bạn cần phải:
1. Định nghĩa một phương thức trong lớp cha bằng cách sử dụng từ khóa `virtual` hoặc `abstract`.
2. Trong lớp con, sử dụng từ khóa `override` để ghi đè phương thức đó.

### Chi tiết
- **Lớp cha**: Phải có phương thức được đánh dấu là `virtual` hoặc `abstract`.
- **Lớp con**: Phải sử dụng từ khóa `override` trong khai báo của phương thức để thực hiện việc ghi đè.
- **Khi nào sử dụng**: Sử dụng khi bạn muốn thay đổi hoặc mở rộng hành vi của phương thức trong lớp cha mà không cần tái định nghĩa toàn bộ lớp.

## Ví dụ
### Ví dụ 1: Ghi đè phương thức với từ khóa `override`
```csharp
public class DungCu
{
    public virtual void SuDung()
    {
        Console.WriteLine("Sử dụng dụng cụ.");
    }
}

public class DungCuDacBiet : DungCu
{
    public override void SuDung()
    {
        Console.WriteLine("Sử dụng dụng cụ đặc biệt.");
    }
}

// Sử dụng
DungCu dungCu = new DungCuDacBiet();
dungCu.SuDung(); // Kết quả: Sử dụng dụng cụ đặc biệt.
```

### Ví dụ 2: Ghi đè thuộc tính
```csharp
public class Hinh
{
    public virtual double DienTich { get; }
}

public class HinhTron : Hinh
{
    private double _banKinh;

    public HinhTron(double banKinh)
    {
        _banKinh = banKinh;
    }

    public override double DienTich
    {
        get { return Math.PI * _banKinh * _banKinh; }
    }
}

// Sử dụng
Hinh hinh = new HinhTron(5);
Console.WriteLine(hinh.DienTich); // Kết quả: 78.53981633974483
```

## Giải thích
### Những điều cần lưu ý
- Khi ghi đè, phương thức trong lớp con phải có cùng kiểu trả về với phương thức trong lớp cha.
- Nếu lớp cha có phương thức là `abstract`, lớp con bắt buộc phải triển khai phương thức đó.
- Nếu bạn không muốn cho lớp con ghi đè một phương thức, bạn có thể sử dụng từ khóa `sealed` trong lớp con để ngăn chặn việc ghi đè thêm nữa.

### Những lỗi phổ biến
- Quên từ khóa `override`: Khi không sử dụng từ khóa này, trình biên dịch sẽ không nhận ra rằng bạn đang cố gắng ghi đè một phương thức.
- Không phù hợp kiểu trả về: Nếu kiểu trả về không khớp giữa lớp cha và lớp con, trình biên dịch sẽ báo lỗi.

## Tóm tắt một dòng
Từ khóa `override` trong C# cho phép lớp con thay đổi hành vi của phương thức đã định nghĩa trong lớp cha, mang lại tính linh hoạt cho mã nguồn.