<!--
Meta Description: # Lệnh "goto" trong C#: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm tắt Lệnh "goto" trong C# cho phép lập trình viên chuyển hướng dòng thực thi đến một nhãn cụ...
Meta Keywords: goto, dụng, trong, thể, một
-->

# Lệnh "goto" trong C#: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm tắt
Lệnh "goto" trong C# cho phép lập trình viên chuyển hướng dòng thực thi đến một nhãn cụ thể trong mã nguồn, giúp điều khiển luồng chương trình một cách trực tiếp.

## Tài liệu
Lệnh "goto" trong C# được sử dụng để chuyển hướng dòng thực thi đến một nhãn (label) đã được định nghĩa trước trong mã. Mặc dù lệnh này có thể hữu ích trong một số trường hợp nhất định, việc sử dụng nó thường bị hạn chế vì có thể làm cho mã trở nên khó đọc và khó bảo trì. 

### Cú pháp:
```csharp
goto <label>;
```

### Định nghĩa nhãn:
Nhãn được định nghĩa bằng cách sử dụng tên nhãn theo sau là dấu hai chấm. Ví dụ:
```csharp
labelName:
```

### Mục đích:
- Điều khiển luồng chương trình theo cách không tuần tự.
- Sử dụng trong các cấu trúc lặp hoặc điều kiện khi cần thiết.

## Ví dụ
### Ví dụ 1: Sử dụng đơn giản
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Bắt đầu chương trình.");
        
        goto Skip; // Chuyển hướng đến nhãn Skip
        
        Console.WriteLine("Dòng này sẽ không được thực hiện.");
        
    Skip:
        Console.WriteLine("Đã bỏ qua dòng trước.");
    }
}
```

### Ví dụ 2: Kết hợp với vòng lặp
```csharp
using System;

class Program
{
    static void Main()
    {
        for (int i = 0; i < 5; i++)
        {
            if (i == 2)
            {
                goto EndLoop; // Nhảy tới nhãn EndLoop khi i == 2
            }
            Console.WriteLine(i);
        }

    EndLoop:
        Console.WriteLine("Đã kết thúc vòng lặp.");
    }
}
```

## Giải thích
Mặc dù lệnh "goto" có thể giúp đơn giản hóa một số tình huống, nhưng việc sử dụng nó quá mức có thể dẫn đến mã lộn xộn, khó theo dõi, và có thể tạo ra các vấn đề về bảo trì. Dưới đây là một số lưu ý:

- **Khó đọc**: Mã sử dụng "goto" có thể khó hiểu nếu không có chú thích rõ ràng.
- **Lỗi logic**: Nếu không cẩn thận, việc sử dụng "goto" có thể dẫn đến vòng lặp vô hạn hoặc nhảy đến các phần không mong muốn trong mã.
- **Thay thế**: Cân nhắc sử dụng các cấu trúc điều khiển khác như if, switch, hoặc vòng lặp (for, while) để tăng tính rõ ràng và bảo trì cho mã.

## Tóm tắt một dòng
Lệnh "goto" trong C# cho phép lập trình viên điều khiển luồng thực thi đến một nhãn cụ thể, mặc dù nên được sử dụng cẩn thận để tránh làm giảm tính rõ ràng của mã.