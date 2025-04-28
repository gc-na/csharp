<!--
Meta Description: # Lệnh "return" trong C#: Cách sử dụng và ý nghĩa ## Tóm tắt Lệnh `return` trong C# được sử dụng để kết thúc một phương thức và trả về giá trị cho ngư...
Meta Keywords: phương, thức, return, lệnh, một
-->

# Lệnh "return" trong C#: Cách sử dụng và ý nghĩa

## Tóm tắt
Lệnh `return` trong C# được sử dụng để kết thúc một phương thức và trả về giá trị cho người gọi. Đây là một phần quan trọng trong việc xây dựng các phương thức trong lập trình hướng đối tượng.

## Tài liệu
Lệnh `return` có vai trò quan trọng trong C#. Khi một phương thức được gọi, nó có thể thực hiện một số thao tác và cuối cùng trả về một giá trị. Cú pháp của lệnh `return` đơn giản, nhưng việc sử dụng đúng cách rất cần thiết để đảm bảo rằng mã của bạn hoạt động như mong đợi.

### Mục đích
- Kết thúc thực thi của một phương thức.
- Trả về giá trị cho phần gọi phương thức.

### Cách sử dụng
Lệnh `return` có thể được sử dụng trong các phương thức có kiểu trả về khác nhau, bao gồm `int`, `string`, `bool`, và nhiều kiểu dữ liệu khác. Đối với các phương thức không trả về giá trị (void), lệnh `return` có thể được sử dụng mà không có giá trị để kết thúc phương thức.

### Chi tiết
- Nếu phương thức có kiểu trả về, bạn phải sử dụng lệnh `return` để trả về một giá trị tương ứng với kiểu đó.
- Nếu phương thức có kiểu `void`, bạn có thể sử dụng lệnh `return` mà không cần giá trị để thoát khỏi phương thức.

## Ví dụ
### Ví dụ 1: Phương thức trả về giá trị
```csharp
public int TinhTong(int a, int b)
{
    return a + b;
}
```

### Ví dụ 2: Phương thức không trả về giá trị
```csharp
public void InRaThongDiep(string thongDiep)
{
    Console.WriteLine(thongDiep);
    return; // Không cần thiết nhưng có thể sử dụng
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng lệnh `return`:
- **Kiểu dữ liệu**: Đảm bảo giá trị trả về phù hợp với kiểu dữ liệu mà phương thức khai báo.
- **Nhiều lệnh return**: Bạn có thể có nhiều lệnh `return` trong một phương thức, nhưng chỉ một trong số đó sẽ được thực thi trong mỗi lần gọi.
- **Thực thi**: Khi gặp lệnh `return`, các dòng mã phía sau nó trong phương thức sẽ không được thực thi.

## Tóm tắt một dòng
Lệnh `return` trong C# dùng để kết thúc một phương thức và trả về giá trị cho phần gọi phương thức.