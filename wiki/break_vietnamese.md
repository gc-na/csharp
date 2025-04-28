<!--
Meta Description: # Lệnh "break" trong C#: Cách sử dụng và ví dụ ## Tóm tắt Lệnh "break" trong ngôn ngữ lập trình C# được sử dụng để thoát khỏi một vòng lặp hoặc một kh...
Meta Keywords: break, dụng, vòng, lặp, trong
-->

# Lệnh "break" trong C#: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh "break" trong ngôn ngữ lập trình C# được sử dụng để thoát khỏi một vòng lặp hoặc một khối lệnh switch, giúp điều khiển luồng thực thi của chương trình một cách linh hoạt.

## Tài liệu
Lệnh "break" là một phần quan trọng trong C# cho phép lập trình viên kết thúc một vòng lặp (như `for`, `while`, hoặc `do-while`) hoặc một khối lệnh `switch`. Khi "break" được thực thi, chương trình sẽ ngay lập tức thoát khỏi vòng lặp hoặc khối lệnh mà nó đang thực thi, tiếp tục với câu lệnh ngay sau đó. Việc sử dụng "break" giúp tạo ra các ứng dụng linh hoạt và cải thiện khả năng kiểm soát luồng thực thi.

### Cách sử dụng
- **Trong vòng lặp**: Khi điều kiện nhất định được thoả mãn, "break" sẽ chấm dứt vòng lặp.
- **Trong switch**: "Break" giúp ngăn chặn việc thực thi tiếp theo của các case khác sau khi một case đã được thực hiện.

### Cú pháp
```csharp
break;
```

## Ví dụ

### Ví dụ 1: Sử dụng trong vòng lặp for
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // Thoát khỏi vòng lặp khi i bằng 5
    }
    Console.WriteLine(i);
}
// Kết quả: 0 1 2 3 4
```

### Ví dụ 2: Sử dụng trong switch
```csharp
int day = 3;
switch (day)
{
    case 1:
        Console.WriteLine("Thứ Hai");
        break;
    case 2:
        Console.WriteLine("Thứ Ba");
        break;
    case 3:
        Console.WriteLine("Thứ Tư");
        break;
    default:
        Console.WriteLine("Ngày không hợp lệ");
        break;
}
// Kết quả: Thứ Tư
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng lệnh "break":
- **Vòng lặp lồng ghép**: Khi sử dụng "break" trong vòng lặp lồng ghép, chỉ vòng lặp gần nhất sẽ bị thoát. Điều này có thể gây nhầm lẫn nếu bạn không chú ý đến cấu trúc của vòng lặp.
- **Không sử dụng "break" trong khối lệnh không hợp lệ**: "Break" chỉ có thể sử dụng trong vòng lặp hoặc switch. Sử dụng nó ở nơi khác sẽ gây lỗi biên dịch.
- **Thói quen lập trình**: Tránh lạm dụng "break" trong nhiều nơi, vì điều này có thể làm cho mã nguồn trở nên khó đọc và bảo trì.

## Tóm tắt một câu
Lệnh "break" trong C# cho phép lập trình viên thoát khỏi vòng lặp hoặc khối lệnh switch, giúp kiểm soát luồng thực thi của chương trình một cách hiệu quả.