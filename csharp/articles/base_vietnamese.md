<!--
Meta Description: # Từ Khóa "base" Trong CSharp: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `base` trong CSharp được sử dụng để truy cập các thành viên (như phương thức...
Meta Keywords: lớp, của, cha, base, dụng
-->

# Từ Khóa "base" Trong CSharp: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `base` trong CSharp được sử dụng để truy cập các thành viên (như phương thức, thuộc tính) của lớp cha từ lớp con, giúp thực hiện việc kế thừa và mở rộng một cách hiệu quả.

## Tài Liệu
Từ khóa `base` cho phép lập trình viên gọi các phương thức hoặc thuộc tính của lớp cơ sở trong ngữ cảnh của lớp kế thừa. Điều này rất hữu ích khi bạn muốn sử dụng hoặc ghi đè một phương thức trong lớp con nhưng vẫn cần giữ lại hành vi của phương thức trong lớp cha.

### Mục Đích
- **Truy cập thành viên của lớp cha**: Khi một lớp kế thừa từ lớp cha, bạn có thể sử dụng `base` để lấy các thuộc tính hoặc phương thức của lớp cha.
- **Gọi phương thức khởi tạo của lớp cha**: Bạn có thể gọi phương thức khởi tạo của lớp cha từ lớp con để đảm bảo rằng lớp cha được khởi tạo đúng cách.

### Cách Sử Dụng
Để sử dụng từ khóa `base`, bạn có thể làm theo cú pháp sau:

```csharp
base.MethodName();
```

Hoặc trong một hàm khởi tạo:

```csharp
public ChildClass() : base(parameter)
{
    // Khởi tạo lớp con
}
```

## Ví Dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng từ khóa `base` trong CSharp:

### Ví dụ 1: Gọi phương thức trong lớp cha
```csharp
class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

class Dog : Animal
{
    public void Speak()
    {
        base.Speak(); // Gọi phương thức Speak của lớp cha
        Console.WriteLine("Dog barks");
    }
}

// Sử dụng
Dog dog = new Dog();
dog.Speak(); // Kết quả: Animal speaks \n Dog barks
```

### Ví dụ 2: Khởi tạo lớp cha
```csharp
class Vehicle
{
    public Vehicle(string type)
    {
        Console.WriteLine("Vehicle type: " + type);
    }
}

class Car : Vehicle
{
    public Car() : base("Car") // Gọi phương thức khởi tạo của lớp cha
    {
        Console.WriteLine("Car created");
    }
}

// Sử dụng
Car car = new Car(); // Kết quả: Vehicle type: Car \n Car created
```

## Giải Thích
Khi sử dụng từ khóa `base`, có một số điều cần lưu ý:
- **Không thể truy cập các thành viên private**: Bạn chỉ có thể sử dụng `base` để truy cập các thành viên có độ truy cập public hoặc protected.
- **Thứ tự khởi tạo**: Khi khởi tạo đối tượng, phương thức khởi tạo của lớp cha sẽ được gọi trước, điều này có thể ảnh hưởng đến trạng thái của đối tượng.
- **Tính đa hình**: Sử dụng `base` trong các phương thức có thể làm cho mã của bạn dễ hiểu hơn khi bạn cần kế thừa và mở rộng chức năng của lớp cha.

## Tóm Tắt Một Dòng
Từ khóa `base` trong CSharp cho phép truy cập và sử dụng các thành viên của lớp cha từ lớp con, hỗ trợ cho việc lập trình hướng đối tượng hiệu quả.