<!--
Meta Description: # Câu lệnh "else" trong CSharp: Hướng dẫn sử dụng chi tiết ## Tóm tắt Câu lệnh "else" trong CSharp là một phần quan trọng của cấu trúc điều kiện, cho ...
Meta Keywords: else, câu, lệnh, trong, điều
-->

# Câu lệnh "else" trong CSharp: Hướng dẫn sử dụng chi tiết

## Tóm tắt
Câu lệnh "else" trong CSharp là một phần quan trọng của cấu trúc điều kiện, cho phép lập trình viên xác định các hành động thay thế khi điều kiện trong câu lệnh "if" không được thỏa mãn.

## Tài liệu
Câu lệnh "else" được sử dụng trong CSharp để mở rộng cấu trúc điều kiện. Khi kiểm tra một điều kiện với câu lệnh "if", nếu điều kiện đó trả về giá trị false, chương trình sẽ thực hiện khối mã trong câu lệnh "else". Câu lệnh "else" giúp tăng tính linh hoạt và quản lý luồng chương trình một cách hiệu quả.

### Cú pháp
```csharp
if (điều_kiện)
{
    // mã sẽ được thực hiện nếu điều_kiện là true
}
else
{
    // mã sẽ được thực hiện nếu điều_kiện là false
}
```

### Sử dụng
- Câu lệnh "else" thường được sử dụng để xử lý các tình huống khác nhau trong quá trình kiểm tra điều kiện.
- Có thể kết hợp câu lệnh "else" với "if" và "else if" để tạo ra các điều kiện phức tạp hơn.

## Ví dụ
### Ví dụ cơ bản
```csharp
int a = 10;

if (a > 5)
{
    Console.WriteLine("a lớn hơn 5");
}
else
{
    Console.WriteLine("a không lớn hơn 5");
}
```

### Ví dụ với "else if"
```csharp
int a = 10;

if (a > 10)
{
    Console.WriteLine("a lớn hơn 10");
}
else if (a == 10)
{
    Console.WriteLine("a bằng 10");
}
else
{
    Console.WriteLine("a nhỏ hơn 10");
}
```

## Giải thích
- **Cảnh giác với điều kiện logic**: Đảm bảo rằng điều kiện trong câu lệnh "if" được xác định rõ ràng để tránh nhầm lẫn trong luồng thực thi.
- **Chú ý đến khối mã**: Cần chú ý rằng khối mã trong câu lệnh "else" chỉ được thực hiện khi tất cả các điều kiện trước đó đều không thỏa mãn.
- **Nesting**: Câu lệnh "else" có thể được lồng ghép trong các câu lệnh "if", nhưng cần cẩn thận để không làm cho mã trở nên khó đọc.

## Tóm tắt một dòng
Câu lệnh "else" trong CSharp cho phép lập trình viên xác định hành động thay thế khi điều kiện trong câu lệnh "if" không được thỏa mãn.