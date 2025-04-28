<!--
Meta Description: # Enum trong C#: Khái niệm và Cách Sử Dụng ## Tóm tắt Enum (liệt kê) trong C# là một kiểu dữ liệu cho phép bạn định nghĩa một tập hợp các hằng số có t...
Meta Keywords: enum, một, giá, trị, liệu
-->

# Enum trong C#: Khái niệm và Cách Sử Dụng

## Tóm tắt
Enum (liệt kê) trong C# là một kiểu dữ liệu cho phép bạn định nghĩa một tập hợp các hằng số có tên, giúp mã của bạn trở nên rõ ràng và dễ hiểu hơn.

## Tài liệu
Enum là một kiểu dữ liệu đặc biệt trong ngôn ngữ lập trình C# cho phép nhà phát triển định nghĩa một tập hợp các giá trị hằng số. Enum giúp cải thiện tính đọc hiểu của mã và giảm thiểu lỗi khi làm việc với các giá trị cố định. Khi bạn khai báo một enum, bạn đang tạo ra một loại dữ liệu mới mà có thể được sử dụng giống như một kiểu dữ liệu cơ bản. 

### Cú pháp
```csharp
enum EnumName
{
    Value1,
    Value2,
    Value3
}
```

### Mục đích
- **Tăng tính đọc hiểu**: Sử dụng enum giúp mã của bạn dễ đọc hơn thay vì sử dụng các giá trị hằng số.
- **Bảo vệ tính toàn vẹn dữ liệu**: Enum giúp giới hạn giá trị mà một biến có thể nhận, giảm thiểu lỗi trong quá trình lập trình.

### Cách sử dụng
Để sử dụng enum, bạn cần khai báo nó và sau đó có thể sử dụng các giá trị của nó trong mã của bạn. Dưới đây là một ví dụ:

```csharp
enum DaysOfWeek
{
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}
```

## Ví dụ
### Ví dụ 1: Khai báo Enum cơ bản
```csharp
enum TrafficLight
{
    Red,
    Yellow,
    Green
}

TrafficLight light = TrafficLight.Red;
```

### Ví dụ 2: Gán giá trị tùy chọn cho Enum
```csharp
enum ErrorCode
{
    NotFound = 404,
    ServerError = 500,
    BadRequest = 400
}

ErrorCode error = ErrorCode.NotFound;
```

### Ví dụ 3: Sử dụng Enum trong switch-case
```csharp
void CheckLight(TrafficLight light)
{
    switch (light)
    {
        case TrafficLight.Red:
            Console.WriteLine("Dừng lại!");
            break;
        case TrafficLight.Yellow:
            Console.WriteLine("Chuẩn bị!");
            break;
        case TrafficLight.Green:
            Console.WriteLine("Đi!");
            break;
    }
}
```

## Giải thích
Khi làm việc với enum, có một số điều cần lưu ý:
- **Giá trị mặc định**: Nếu bạn không chỉ định giá trị cho một hằng số trong enum, C# sẽ tự động gán giá trị bắt đầu từ 0 cho hằng số đầu tiên, sau đó tăng dần cho các hằng số tiếp theo.
- **Kiểu dữ liệu cơ sở**: Mặc định, kiểu dữ liệu cơ sở cho enum là `int`, nhưng bạn có thể chỉ định kiểu dữ liệu khác như `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, hoặc `ulong`.
- **Sử dụng sai**: Tránh việc so sánh enum với giá trị số, vì điều này có thể dẫn đến lỗi không thể nhận biết.

## Tóm tắt một dòng
Enum trong C# là một công cụ hữu ích giúp định nghĩa các giá trị hằng số có tên, cải thiện tính đọc hiểu và bảo vệ tính toàn vẹn dữ liệu trong mã nguồn.