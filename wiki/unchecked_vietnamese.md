<!--
Meta Description: # Từ khóa "unchecked" trong C#: Tìm hiểu về Kiểm soát Tràn số ## Tóm tắt Từ khóa `unchecked` trong C# được sử dụng để chỉ định rằng các phép toán số h...
Meta Keywords: unchecked, trong, phép, int, kiểm
-->

# Từ khóa "unchecked" trong C#: Tìm hiểu về Kiểm soát Tràn số

## Tóm tắt
Từ khóa `unchecked` trong C# được sử dụng để chỉ định rằng các phép toán số học có thể xảy ra tràn số mà không cần kiểm tra lỗi. Điều này giúp tăng hiệu suất cho các phép toán, nhưng cũng tiềm ẩn rủi ro khi không kiểm soát được giá trị vượt quá giới hạn của kiểu dữ liệu.

## Tài liệu
### Mục đích
Từ khóa `unchecked` được sử dụng trong C# để thực hiện các phép toán số học mà không kiểm tra khả năng tràn số. Khi một phép toán xảy ra tràn, C# thường sẽ ném ra một ngoại lệ (exception) nếu không được bọc trong khối `unchecked`.

### Cách sử dụng
Bạn có thể sử dụng `unchecked` trong một khối mã hoặc một biểu thức. Ví dụ, khi một phép cộng hoặc phép nhân có thể dẫn đến tràn số, bạn có thể bao bọc phép toán đó bằng `unchecked` để bỏ qua việc kiểm tra.

### Chi tiết
- **Cú pháp**: 
  ```csharp
  unchecked
  {
      // mã thực hiện phép toán
  }
  ```
- Hoặc trong biểu thức:
  ```csharp
  int result = unchecked(a + b);
  ```

## Ví dụ
### Ví dụ 1: Sử dụng `unchecked` trong khối
```csharp
int a = int.MaxValue;
int b = 1;

int result;
unchecked
{
    result = a + b; // Không có kiểm tra tràn, result sẽ có giá trị int.MinValue
}
Console.WriteLine(result); // In ra -2147483648
```

### Ví dụ 2: Sử dụng `unchecked` trong biểu thức
```csharp
int a = int.MaxValue;
int b = 1;

int result = unchecked(a + b); // Không kiểm tra tràn
Console.WriteLine(result); // In ra -2147483648
```

## Giải thích
Khi sử dụng `unchecked`, bạn cần lưu ý rằng việc bỏ qua kiểm tra tràn số có thể dẫn đến kết quả không mong muốn. Điều này có thể gây khó khăn trong việc gỡ lỗi hoặc gây ra lỗi trong chương trình. Nếu không chắc chắn về giá trị của các phép toán, bạn nên xem xét sử dụng `checked` để đảm bảo an toàn.

## Tóm tắt một dòng
Từ khóa `unchecked` trong C# cho phép thực hiện các phép toán số học mà không kiểm tra tràn số, giúp tăng hiệu suất nhưng cũng tiềm ẩn rủi ro cho giá trị kết quả.