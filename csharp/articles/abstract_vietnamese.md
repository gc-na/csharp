<!--
Meta Description: # Từ Khóa "abstract" trong C#: Định Nghĩa và Cách Sử Dụng ## Tóm tắt Từ khóa `abstract` trong C# được sử dụng để định nghĩa các lớp và phương thức trừ...
Meta Keywords: lớp, các, tượng, trừu, abstract
-->

# Từ Khóa "abstract" trong C#: Định Nghĩa và Cách Sử Dụng

## Tóm tắt
Từ khóa `abstract` trong C# được sử dụng để định nghĩa các lớp và phương thức trừu tượng, cho phép lập trình viên tạo ra các kiểu đối tượng có thể mở rộng mà không cần cung cấp toàn bộ triển khai ngay lập tức.

## Tài liệu

### Mục đích
Từ khóa `abstract` giúp người lập trình định nghĩa các lớp cha (superclass) có thể chứa các phương thức trừu tượng. Một lớp trừu tượng không thể được khởi tạo, nhưng nó có thể chứa các phương thức và thuộc tính mà các lớp con (subclass) phải cài đặt.

### Cách sử dụng
- **Lớp Trừu Tượng**: Khi một lớp được đánh dấu là `abstract`, nó không thể được khởi tạo và có thể chứa các phương thức trừu tượng.
- **Phương Thức Trừu Tượng**: Được khai báo trong một lớp trừu tượng mà không có phần thân, buộc các lớp con phải cung cấp một phần cài đặt.

### Chi tiết
Khi sử dụng `abstract`, bạn cần lưu ý rằng:
- Một lớp trừu tượng có thể chứa cả các phương thức trừu tượng và các phương thức đã cài đặt.
- Các lớp con phải cài đặt tất cả các phương thức trừu tượng, nếu không, chúng cũng phải được đánh dấu là `abstract`.

```csharp
abstract class HinhHoc
{
    public abstract double DienTich();
}

class HinhChuNhat : HinhHoc
{
    private double _chieuDai;
    private double _chieuRong;

    public HinhChuNhat(double chieuDai, double chieuRong)
    {
        _chieuDai = chieuDai;
        _chieuRong = chieuRong;
    }

    public override double DienTich()
    {
        return _chieuDai * _chieuRong;
    }
}
```

## Ví dụ
### Ví dụ 1: Lớp Trừu Tượng
```csharp
abstract class DongVat
{
    public abstract void Keu();
}

class Cho : DongVat
{
    public override void Keu()
    {
        Console.WriteLine("Gâu gâu");
    }
}
```

### Ví dụ 2: Phương Thức Trừu Tượng
```csharp
abstract class PhuongTrinh
{
    public abstract double Giai();
}

class PhuongTrinhBacNhat : PhuongTrinh
{
    private double _a;
    private double _b;

    public PhuongTrinhBacNhat(double a, double b)
    {
        _a = a;
        _b = b;
    }

    public override double Giai()
    {
        return -_b / _a;
    }
}
```

## Giải thích
- **Những cạm bẫy phổ biến**: Một lỗi thường gặp là quên cài đặt các phương thức trừu tượng trong lớp con. Điều này sẽ dẫn đến lỗi biên dịch.
- **Lớp con cũng có thể có phương thức riêng**: Lớp con có thể có thêm các phương thức riêng mà không bị giới hạn bởi lớp cha.
- **Không thể khởi tạo lớp trừu tượng**: Bất kỳ cố gắng nào để tạo một đối tượng từ lớp trừu tượng sẽ dẫn đến lỗi biên dịch.

## Tóm tắt một dòng
Từ khóa `abstract` trong C# cho phép tạo ra các lớp và phương thức trừu tượng, buộc các lớp con phải cài đặt các thành phần đó, nhằm giúp xây dựng các cấu trúc lập trình linh hoạt và dễ mở rộng.