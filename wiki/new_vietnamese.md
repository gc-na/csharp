<!--
Meta Description: # Từ Khóa "new" trong C# - Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "new" trong C# được sử dụng để tạo ra các đối tượng mới và để ẩn các thành viên ...
Meta Keywords: lớp, new, thành, viên, khóa
-->

# Từ Khóa "new" trong C# - Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "new" trong C# được sử dụng để tạo ra các đối tượng mới và để ẩn các thành viên của lớp cơ sở trong lớp dẫn xuất, giúp quản lý bộ nhớ và tối ưu hóa mã hiệu quả hơn.

## Tài Liệu
Từ khóa "new" có hai mục đích chính trong C#:

1. **Khởi Tạo Đối Tượng**: Khi bạn muốn tạo một thể hiện mới của một lớp, bạn sử dụng từ khóa "new" để gọi đến hàm khởi tạo của lớp đó.
   
   Cú pháp: 
   ```csharp
   TênLớp tênBiến = new TênLớp();
   ```

2. **Ẩn Thành Viên Lớp**: Khi bạn định nghĩa một thành viên trong lớp dẫn xuất có cùng tên với thành viên trong lớp cơ sở, bạn có thể dùng từ khóa "new" để ẩn thành viên của lớp cơ sở.

   Cú pháp:
   ```csharp
   public new TênKiểu TênHàm() { ... }
   ```

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng từ khóa "new":

### 1. Khởi Tạo Đối Tượng
```csharp
class Dog
{
    public void Bark()
    {
        Console.WriteLine("Woof!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Dog myDog = new Dog();
        myDog.Bark(); // Kết quả: Woof!
    }
}
```

### 2. Ẩn Thành Viên Lớp
```csharp
class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal sound");
    }
}

class Dog : Animal
{
    public new void Speak()
    {
        Console.WriteLine("Woof!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal myAnimal = new Animal();
        myAnimal.Speak(); // Kết quả: Animal sound

        Dog myDog = new Dog();
        myDog.Speak(); // Kết quả: Woof!
    }
}
```

## Giải Thích
Một số điểm cần lưu ý khi sử dụng từ khóa "new":

- **Khởi Tạo Đối Tượng**: Khi bạn tạo một đối tượng mới, bộ nhớ cho đối tượng đó sẽ được cấp phát. Đảm bảo bạn giải phóng bộ nhớ khi không còn sử dụng.
  
- **Ẩn Thành Viên**: Việc ẩn một thành viên của lớp cơ sở có thể dẫn đến sự nhầm lẫn nếu không được quản lý tốt. Khi gọi hàm từ một biến lớp cơ sở, hàm của lớp cơ sở sẽ được thực thi thay vì hàm của lớp dẫn xuất.

- **Không phải là Đóng Gói**: Từ khóa "new" không phải là phương thức đóng gói (overriding) và không thể thay thế các thành viên đã được định nghĩa trong lớp cơ sở.

## Tóm Tắt Một Dòng
Từ khóa "new" trong C# được sử dụng để khởi tạo đối tượng mới và ẩn các thành viên của lớp cơ sở trong lớp dẫn xuất.