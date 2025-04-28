<!--
Meta Description: # sbyte trong C#: Kiểu dữ liệu số nguyên 8-bit ## Tóm tắt `sbyte` là một kiểu dữ liệu trong C# dùng để lưu trữ các giá trị số nguyên với kích thước 8-...
Meta Keywords: sbyte, các, kiểu, giá, trị
-->

# sbyte trong C#: Kiểu dữ liệu số nguyên 8-bit

## Tóm tắt
`sbyte` là một kiểu dữ liệu trong C# dùng để lưu trữ các giá trị số nguyên với kích thước 8-bit và có thể biểu diễn các số âm. Kiểu dữ liệu này rất hữu ích khi bạn cần một kiểu số nguyên nhỏ gọn hơn và không cần lưu trữ giá trị lớn.

## Tài liệu
`Sbyte` là viết tắt của "signed byte", cho phép bạn lưu trữ các giá trị từ -128 đến 127. Kiểu dữ liệu này thường được sử dụng trong các tình huống mà bộ nhớ là một yếu tố quan trọng, hoặc khi bạn muốn đảm bảo rằng chỉ có các giá trị nhỏ được xử lý. 

### Cách sử dụng
Để khai báo một biến kiểu `sbyte`, bạn có thể sử dụng cú pháp sau:
```csharp
sbyte myValue = -128; // Khai báo biến sbyte với giá trị -128
```

### Chi tiết
- **Kích thước**: 1 byte (8 bits).
- **Giá trị**: Từ -128 đến 127.
- **Tính năng**: `sbyte` hỗ trợ các phép toán số học, so sánh và các thao tác khác như các kiểu số nguyên khác.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng `sbyte` trong C#:

### Ví dụ 1: Khai báo và khởi tạo
```csharp
sbyte a = 100;
sbyte b = -50;
sbyte sum = (sbyte)(a + b); // Kết quả là 50
```

### Ví dụ 2: Sử dụng với điều kiện
```csharp
sbyte temperature = -5;
if (temperature < 0)
{
    Console.WriteLine("Nhiệt độ dưới 0 độ C");
}
```

### Ví dụ 3: Phép toán
```csharp
sbyte x = 10;
sbyte y = 20;
sbyte result = (sbyte)(x * y); // Kết quả là 200
```

## Giải thích
Khi sử dụng `sbyte`, có một số điều cần lưu ý:
- **Tràn số**: Nếu kết quả của phép toán vượt quá giá trị có thể biểu diễn của `sbyte`, nó có thể gây ra tràn số (overflow). Bạn cần xử lý tình huống này để tránh lỗi.
- **Khả năng chuyển đổi**: Khi chuyển đổi giữa các kiểu dữ liệu khác nhau, hãy cẩn thận để đảm bảo rằng các giá trị không bị mất mát thông tin.
- **Hiệu suất**: Mặc dù `sbyte` có thể tiết kiệm bộ nhớ, nhưng hiệu suất có thể không khác biệt nhiều so với các kiểu dữ liệu số nguyên lớn hơn trong nhiều trường hợp.

## Tóm tắt một dòng
`sbyte` trong C# là kiểu dữ liệu số nguyên 8-bit cho phép lưu trữ các giá trị từ -128 đến 127, hữu ích trong việc tiết kiệm bộ nhớ và xử lý các giá trị nhỏ.