<!--
Meta Description: # C# Fixed: Khóa Địa Chỉ Bộ Nhớ Trong Ngôn Ngữ Lập Trình C# ## Tóm tắt Từ khóa `fixed` trong C# cho phép lập trình viên khóa một vùng bộ nhớ để đảm bả...
Meta Keywords: khóa, trong, fixed, không, dụng
-->

# C# Fixed: Khóa Địa Chỉ Bộ Nhớ Trong Ngôn Ngữ Lập Trình C#

## Tóm tắt
Từ khóa `fixed` trong C# cho phép lập trình viên khóa một vùng bộ nhớ để đảm bảo rằng địa chỉ của nó không thay đổi trong quá trình thực thi, đặc biệt hữu ích khi làm việc với các kiểu dữ liệu không quản lý hoặc khi sử dụng các API yêu cầu con trỏ.

## Tài liệu
Từ khóa `fixed` được sử dụng trong C# để khóa các mảng hoặc các cấu trúc dữ liệu không quản lý (unmanaged) trong bộ nhớ. Khi một vùng bộ nhớ bị khóa bằng `fixed`, trình biên dịch sẽ không di chuyển các đối tượng này trong quá trình thu gom rác (garbage collection). Điều này cực kỳ quan trọng khi bạn cần làm việc với con trỏ hoặc khi tương tác với mã không quản lý.

### Mục đích
- Đảm bảo rằng địa chỉ bộ nhớ của một đối tượng không thay đổi trong suốt thời gian mà bạn đang sử dụng nó.
- Giúp lập trình viên giao tiếp dễ dàng với mã không quản lý, đặc biệt là khi sử dụng các API từ thư viện ngoài.

### Cách sử dụng
Cú pháp cơ bản của từ khóa `fixed` như sau:

```csharp
fixed (type* ptr = &variable)
{
    // Thao tác với con trỏ
}
```

### Chi tiết
- **type**: Kiểu dữ liệu của biến mà bạn muốn khóa.
- **ptr**: Tên con trỏ mà bạn sẽ sử dụng để truy cập vào vùng bộ nhớ đã khóa.
- **variable**: Biến mà bạn muốn khóa (thường là mảng hoặc cấu trúc).

Khi sử dụng `fixed`, cần lưu ý rằng nó chỉ có thể được sử dụng trong khối mã `unsafe`, vì bạn đang làm việc với các con trỏ và các thao tác không an toàn.

## Ví dụ
### Ví dụ 1: Khóa một mảng
```csharp
unsafe
{
    int[] numbers = { 1, 2, 3, 4, 5 };
    fixed (int* p = numbers)
    {
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine(*(p + i));
        }
    }
}
```

### Ví dụ 2: Khóa một cấu trúc
```csharp
unsafe
{
    MyStruct myStruct;
    fixed (MyStruct* p = &myStruct)
    {
        // Thao tác với p
    }
}
```

## Giải thích
- **Cảnh báo**: Việc sử dụng `fixed` trong mã không an toàn có thể dẫn đến lỗi nếu bạn không kiểm soát tốt vùng bộ nhớ. Hãy chắc chắn rằng bạn hiểu rõ cách hoạt động của thu gom rác trong C#.
- **Thời gian khóa**: Cần lưu ý rằng vùng bộ nhớ sẽ chỉ bị khóa trong thời gian thực thi của khối mã `fixed`. Sau khi thoát khỏi khối này, bộ nhớ sẽ trở lại trạng thái có thể bị di chuyển.
- **Phải sử dụng trong khối `unsafe`**: Để sử dụng `fixed`, bạn cần phải khai báo phương thức hoặc khối mã là `unsafe`, điều này có thể yêu cầu thay đổi cài đặt dự án của bạn.

## Tóm tắt một dòng
Từ khóa `fixed` trong C# cho phép lập trình viên khóa vùng bộ nhớ nhằm đảm bảo địa chỉ của nó không thay đổi trong quá trình thực thi, đặc biệt khi làm việc với các con trỏ và mã không quản lý.