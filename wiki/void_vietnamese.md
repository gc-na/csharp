<!--
Meta Description: # Hiểu Về Từ Khóa "void" Trong Ngôn Ngữ Lập Trình C# ## Tóm Tắt Từ khóa "void" trong ngôn ngữ lập trình C# được sử dụng để chỉ định rằng một phương th...
Meta Keywords: void, thức, không, phương, trong
-->

# Hiểu Về Từ Khóa "void" Trong Ngôn Ngữ Lập Trình C#

## Tóm Tắt
Từ khóa "void" trong ngôn ngữ lập trình C# được sử dụng để chỉ định rằng một phương thức không trả về giá trị nào. Điều này cho phép lập trình viên tạo ra các phương thức thực hiện các tác vụ mà không cần cung cấp giá trị đầu ra.

## Tài Liệu
Từ khóa "void" được sử dụng trong định nghĩa phương thức để chỉ rõ rằng phương thức đó không trả về giá trị nào. Khi bạn định nghĩa một phương thức với từ khóa "void", bạn có thể thực hiện các thao tác như in ra màn hình, thay đổi trạng thái của đối tượng mà không cần trả về kết quả.

### Cú Pháp
```csharp
void MethodName()
{
    // Thao tác thực hiện
}
```

### Mục Đích
- **Thực hiện tác vụ**: Phương thức void thường được sử dụng để thực hiện các tác vụ, chẳng hạn như cập nhật giao diện người dùng hoặc xử lý sự kiện.
- **Tiết kiệm tài nguyên**: Không cần lưu trữ giá trị trả về giúp tiết kiệm bộ nhớ và tài nguyên.

## Ví Dụ
### Ví dụ Cơ Bản
```csharp
using System;

class Program
{
    static void Main()
    {
        PrintMessage();
    }

    static void PrintMessage()
    {
        Console.WriteLine("Hello, World!");
    }
}
```
Trong ví dụ trên, phương thức `PrintMessage` không trả về giá trị nào, mà chỉ in ra màn hình thông điệp "Hello, World!".

### Ví dụ Sử Dụng Trong Lớp
```csharp
class Calculator
{
    public void Add(int a, int b)
    {
        int sum = a + b;
        Console.WriteLine("Tổng: " + sum);
    }
}

class Program
{
    static void Main()
    {
        Calculator calc = new Calculator();
        calc.Add(5, 10);
    }
}
```
Phương thức `Add` trong lớp `Calculator` tính tổng của hai số và in ra kết quả mà không trả về giá trị.

## Giải Thích
Khi sử dụng từ khóa "void", có một số điểm cần lưu ý:
- **Không thể sử dụng trong biểu thức**: Phương thức void không thể được sử dụng trong các biểu thức so sánh hoặc gán do không có giá trị trả về.
- **Giới hạn trong việc trả về**: Nếu bạn cần một phương thức trả về giá trị, bạn phải chỉ định kiểu dữ liệu thay vì "void".

## Tóm Tắt Một Dòng
Từ khóa "void" trong C# được sử dụng để chỉ định rằng một phương thức không trả về giá trị nào, cho phép thực hiện các tác vụ mà không cần cung cấp giá trị đầu ra.