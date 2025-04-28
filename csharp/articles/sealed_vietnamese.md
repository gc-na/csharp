<!--
Meta Description: # Từ Khóa "sealed" Trong C#: Tính Năng Đóng Gói Lớp ## Tóm Tắt Từ khóa `sealed` trong C# được sử dụng để ngăn chặn lớp kế thừa từ các lớp khác, đảm bả...
Meta Keywords: lớp, sealed, được, các, dụng
-->

# Từ Khóa "sealed" Trong C#: Tính Năng Đóng Gói Lớp

## Tóm Tắt
Từ khóa `sealed` trong C# được sử dụng để ngăn chặn lớp kế thừa từ các lớp khác, đảm bảo rằng lớp đó không thể được mở rộng. Điều này giúp bảo vệ mã nguồn và đảm bảo tính toàn vẹn của các lớp đã được định nghĩa.

## Tài Liệu
### Mục Đích
Từ khóa `sealed` được sử dụng trong C# nhằm mục đích ngăn chặn các lớp con kế thừa từ một lớp cha đã được đánh dấu là sealed. Điều này hữu ích trong các trường hợp mà bạn muốn ngăn chặn việc mở rộng một lớp, bảo vệ hành vi của nó và đảm bảo tính chính xác trong ứng dụng.

### Cách Sử Dụng
Khi bạn đánh dấu một lớp là sealed, bất kỳ lớp nào khác cố gắng kế thừa từ lớp đó sẽ gây ra lỗi biên dịch. Từ khóa `sealed` thường được sử dụng trong các lớp không cần phải mở rộng thêm, chẳng hạn như các lớp chứa các phương thức tĩnh hoặc các lớp mô hình dữ liệu.

Cú pháp cơ bản như sau:

```csharp
sealed class ClassName
{
    // Định nghĩa thuộc tính và phương thức
}
```

## Ví Dụ
### Ví dụ 1: Định nghĩa lớp sealed
```csharp
sealed class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}
```

### Ví dụ 2: Cố gắng kế thừa từ lớp sealed
```csharp
// Lớp này sẽ gây lỗi biên dịch
class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog barks");
    }
}
```
Khi bạn cố gắng biên dịch đoạn mã trên, bạn sẽ nhận được thông báo lỗi cho biết rằng lớp `Dog` không thể kế thừa từ lớp `Animal` vì lớp này đã được đánh dấu là sealed.

## Giải Thích
Một số điều cần lưu ý khi sử dụng từ khóa `sealed`:
- **Ngăn Chặn Kế Thừa**: Khi một lớp được đánh dấu là sealed, bạn không thể tạo lớp con từ lớp đó. Điều này có thể hạn chế việc mở rộng một số lớp, nhưng cũng bảo vệ tính toàn vẹn của chúng.
- **Hiệu Suất**: Sử dụng sealed có thể cải thiện hiệu suất trong một số trường hợp, vì nó cho phép trình biên dịch tối ưu hóa mã.
- **Tương Thích**: `sealed` chỉ có thể được sử dụng cho các lớp, không thể áp dụng cho các interface hoặc lớp trừu tượng.

## Tóm Tắt Một Dòng
Từ khóa `sealed` trong C# ngăn chặn việc kế thừa từ một lớp, bảo vệ tính toàn vẹn và tối ưu hóa hiệu suất cho mã nguồn.