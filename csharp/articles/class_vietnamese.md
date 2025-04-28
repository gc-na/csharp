<!--
Meta Description: # Lớp (Class) trong CSharp: Hướng Dẫn Toàn Diện ## Tóm tắt Lớp (Class) trong CSharp là một khái niệm cơ bản trong lập trình hướng đối tượng, cho phép ...
Meta Keywords: lớp, public, csharp, trong, class
-->

# Lớp (Class) trong CSharp: Hướng Dẫn Toàn Diện

## Tóm tắt
Lớp (Class) trong CSharp là một khái niệm cơ bản trong lập trình hướng đối tượng, cho phép người lập trình định nghĩa các đối tượng với thuộc tính và phương thức riêng, từ đó tạo ra mã nguồn dễ quản lý và mở rộng.

## Tài liệu
### Mục đích
Lớp (Class) được sử dụng để tạo ra các kiểu dữ liệu tùy chỉnh trong CSharp. Nó cho phép tổ chức mã nguồn theo cách trực quan và dễ hiểu hơn, giúp cho việc phát triển và bảo trì ứng dụng trở nên đơn giản hơn.

### Cách sử dụng
Cú pháp cơ bản để định nghĩa một lớp trong CSharp như sau:

```csharp
class ClassName
{
    // Thuộc tính
    public int Property { get; set; }

    // Phương thức
    public void Method()
    {
        // Thực hiện một số tác vụ
    }
}
```

- **ClassName**: Tên của lớp, thường đặt theo quy tắc PascalCase.
- **Thuộc tính**: Các biến lưu trữ trạng thái của đối tượng.
- **Phương thức**: Các hành vi mà đối tượng có thể thực hiện.

### Chi tiết
Lớp có thể chứa nhiều loại thành phần, bao gồm:
- **Thuộc tính**: Chứa dữ liệu của lớp.
- **Phương thức**: Chứa logic mà đối tượng thực hiện.
- **Constructor**: Một phương thức đặc biệt được gọi khi một đối tượng được tạo ra từ lớp.
- **Kế thừa**: CSharp hỗ trợ kế thừa, cho phép một lớp kế thừa thuộc tính và phương thức từ lớp khác.

## Ví dụ
### Ví dụ cơ bản về lớp

```csharp
public class Car
{
    public string Model { get; set; }
    public int Year { get; set; }

    public void DisplayInfo()
    {
        Console.WriteLine($"Model: {Model}, Year: {Year}");
    }
}

// Sử dụng lớp
Car myCar = new Car();
myCar.Model = "Toyota";
myCar.Year = 2023;
myCar.DisplayInfo();
```

### Ví dụ về kế thừa

```csharp
public class Vehicle
{
    public int Speed { get; set; }

    public void Move()
    {
        Console.WriteLine("Vehicle is moving");
    }
}

public class Bike : Vehicle
{
    public void RingBell()
    {
        Console.WriteLine("Bike bell rings!");
    }
}

// Sử dụng lớp kế thừa
Bike myBike = new Bike();
myBike.Speed = 15;
myBike.Move();
myBike.RingBell();
```

## Giải thích
Khi làm việc với lớp trong CSharp, có một số điểm cần lưu ý:
- **Tên lớp** nên ngắn gọn và có ý nghĩa, phản ánh rõ ràng chức năng của lớp.
- **Tính đóng gói**: Sử dụng mức truy cập (public, private, protected) để bảo vệ dữ liệu bên trong lớp.
- **Kế thừa**: Cần cẩn trọng khi sử dụng kế thừa, vì có thể dẫn đến các vấn đề như lạm dụng tính kế thừa hoặc tạo ra các mối quan hệ phức tạp giữa các lớp.

## Tóm tắt một dòng
Lớp (Class) trong CSharp là cấu trúc chính để định nghĩa các đối tượng với thuộc tính và phương thức, giúp tổ chức mã nguồn hiệu quả trong lập trình hướng đối tượng.