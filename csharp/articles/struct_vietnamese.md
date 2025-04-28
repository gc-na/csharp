<!--
Meta Description: # Cấu Trúc (Struct) trong CSharp: Định Nghĩa, Cách Sử Dụng và Ví Dụ ## Tóm Tắt Cấu trúc (struct) trong CSharp là một kiểu dữ liệu giá trị cho phép bạn...
Meta Keywords: một, cấu, trúc, trong, csharp
-->

# Cấu Trúc (Struct) trong CSharp: Định Nghĩa, Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Cấu trúc (struct) trong CSharp là một kiểu dữ liệu giá trị cho phép bạn nhóm nhiều giá trị lại thành một đối tượng duy nhất. Cấu trúc thường được sử dụng để tạo các kiểu dữ liệu nhẹ hơn so với lớp (class).

## Tài Liệu
Cấu trúc (struct) là một kiểu dữ liệu trong ngôn ngữ lập trình CSharp, cho phép lập trình viên định nghĩa các kiểu dữ liệu tùy chỉnh bằng cách nhóm nhiều biến lại với nhau. Khác với lớp, cấu trúc là kiểu dữ liệu giá trị, có nghĩa là khi bạn tạo một đối tượng từ một cấu trúc, một bản sao của nó sẽ được tạo ra. Điều này giúp tiết kiệm bộ nhớ và tăng tốc độ xử lý trong một số tình huống cụ thể.

### Cách Sử Dụng
Để định nghĩa một cấu trúc trong CSharp, bạn sử dụng từ khóa `struct` theo cú pháp sau:

```csharp
struct TenCauTruc
{
    public kiểuDữLiệu TênBiến1;
    public kiểuDữLiệu TênBiến2;
    // Các biến khác
}
```

### Ví dụ
Dưới đây là một ví dụ đơn giản về cách định nghĩa và sử dụng cấu trúc trong CSharp:

```csharp
using System;

struct Diem
{
    public int X;
    public int Y;

    public Diem(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void HienThi()
    {
        Console.WriteLine("Điểm: ({0}, {1})", X, Y);
    }
}

class Program
{
    static void Main()
    {
        Diem diem1 = new Diem(10, 20);
        diem1.HienThi();
    }
}
```

### Giải Thích
Khi sử dụng cấu trúc, có một số điều cần lưu ý:

- **Giá trị và Tham chiếu**: Cấu trúc là kiểu dữ liệu giá trị, do đó, khi bạn truyền một cấu trúc vào phương thức hoặc gán nó cho một biến khác, một bản sao của nó sẽ được tạo ra. Điều này có thể dẫn đến sự nhầm lẫn nếu bạn mong đợi thay đổi của một đối tượng sẽ ảnh hưởng đến đối tượng khác.
  
- **Khởi tạo**: Nếu cấu trúc không được khởi tạo trước khi sử dụng, nó sẽ không tự động có giá trị mặc định. Bạn cần phải khởi tạo tất cả các trường trong cấu trúc trước khi sử dụng chúng.

- **Không thể kế thừa**: Cấu trúc không hỗ trợ kế thừa như lớp, nhưng có thể triển khai các giao diện (interface).

## Tóm Tắt Một Dòng
Cấu trúc (struct) trong CSharp là kiểu dữ liệu giá trị cho phép nhóm nhiều biến lại thành một đối tượng duy nhất, giúp tiết kiệm bộ nhớ và tối ưu hóa hiệu suất.