<!--
Meta Description: # "this" trong C#: Cách sử dụng và ý nghĩa ## Tóm tắt Từ khóa "this" trong C# được sử dụng để tham chiếu đến đối tượng hiện tại của một lớp. Nó giúp p...
Meta Keywords: trong, phương, thức, dụng, các
-->

# "this" trong C#: Cách sử dụng và ý nghĩa

## Tóm tắt
Từ khóa "this" trong C# được sử dụng để tham chiếu đến đối tượng hiện tại của một lớp. Nó giúp phân biệt giữa các biến thành viên của lớp và các tham số của phương thức có cùng tên.

## Tài liệu
### Mục đích
Từ khóa "this" cho phép lập trình viên truy cập và thao tác với các thành viên của đối tượng trong các phương thức và khối khởi tạo. Nó đặc biệt hữu ích khi tên của các tham số phương thức trùng với tên của các biến thành viên.

### Cách sử dụng
- **Tham chiếu đến biến thành viên**: Khi bạn cần truy cập một biến thành viên của lớp từ bên trong một phương thức hoặc khối khởi tạo.
- **Gọi phương thức khác trong cùng một lớp**: Khi cần gọi một phương thức khác của lớp hiện tại mà không cần chỉ định rõ tên lớp.
- **Truyền đối tượng hiện tại**: Trong một số trường hợp, bạn có thể muốn truyền đối tượng hiện tại đến một phương thức khác.

### Chi tiết
Từ khóa "this" có thể được sử dụng trong các phương thức, thuộc tính, và khối khởi tạo. Nó giúp làm rõ ngữ cảnh và tăng khả năng đọc hiểu của mã nguồn. Ngoài ra, "this" cũng có thể được sử dụng để tạo các phương thức mở rộng.

## Ví dụ
```csharp
public class HinhTron
{
    private double banKinh;

    public HinhTron(double banKinh)
    {
        this.banKinh = banKinh; // Sử dụng 'this' để phân biệt với tham số
    }

    public double DienTich()
    {
        return Math.PI * this.banKinh * this.banKinh; // 'this' có thể bỏ qua
    }

    public void InThongTin()
    {
        Console.WriteLine("Bán kính: " + this.banKinh);
    }
}
```

## Giải thích
- **Nhầm lẫn giữa tham số và biến thành viên**: Khi tên tham số trùng với tên biến thành viên, việc không sử dụng "this" có thể gây nhầm lẫn.
- **Không cần thiết trong một số trường hợp**: Nếu không có sự trùng lặp tên, bạn có thể không cần sử dụng "this".
- **Sử dụng trong phương thức tĩnh**: Từ khóa "this" không thể được sử dụng trong các phương thức tĩnh, vì không có đối tượng hiện tại trong ngữ cảnh này.

## Tóm tắt một dòng
Từ khóa "this" trong C# cho phép tham chiếu đến đối tượng hiện tại, giúp phân biệt giữa các biến thành viên và tham số phương thức.