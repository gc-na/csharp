<!--
Meta Description: # Cấu Trúc Lệnh "if" trong CSharp: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm tắt Lệnh "if" trong CSharp là một cấu trúc điều kiện cho phép lập trình viên thự...
Meta Keywords: điều, kiện, lệnh, else, trong
-->

# Cấu Trúc Lệnh "if" trong CSharp: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm tắt
Lệnh "if" trong CSharp là một cấu trúc điều kiện cho phép lập trình viên thực hiện các khối mã dựa trên việc đánh giá điều kiện đúng hay sai.

## Tài liệu
Lệnh "if" trong CSharp được sử dụng để kiểm tra một điều kiện, nếu điều kiện đó đúng (true), thì khối mã bên trong lệnh "if" sẽ được thực thi. Đây là một trong những cấu trúc điều kiện cơ bản và quan trọng nhất trong lập trình.

### Cú pháp
Cú pháp cơ bản của lệnh "if" như sau:

```csharp
if (điều_kiện)
{
    // Khối mã thực thi nếu điều kiện đúng
}
```

### Lệnh "if" đơn giản
Trong trường hợp chỉ có một khối mã cần thực thi khi điều kiện đúng, cú pháp có thể được viết ngắn gọn hơn:

```csharp
if (điều_kiện) 
    // Khối mã thực thi
```

### Lệnh "if-else"
Để xử lý trường hợp khi điều kiện không đúng, lập trình viên có thể sử dụng lệnh "else":

```csharp
if (điều_kiện)
{
    // Khối mã thực thi nếu điều kiện đúng
}
else
{
    // Khối mã thực thi nếu điều kiện sai
}
```

### Lệnh "if-else if-else"
Khi cần kiểm tra nhiều điều kiện, lệnh "else if" có thể được sử dụng:

```csharp
if (điều_kiện1)
{
    // Khối mã thực thi nếu điều kiện1 đúng
}
else if (điều_kiện2)
{
    // Khối mã thực thi nếu điều kiện2 đúng
}
else
{
    // Khối mã thực thi nếu tất cả các điều kiện đều sai
}
```

## Ví dụ
### Ví dụ 1: Lệnh "if" đơn giản
```csharp
int a = 10;
if (a > 5)
{
    Console.WriteLine("a lớn hơn 5");
}
```

### Ví dụ 2: Lệnh "if-else"
```csharp
int b = 3;
if (b % 2 == 0)
{
    Console.WriteLine("b là số chẵn");
}
else
{
    Console.WriteLine("b là số lẻ");
}
```

### Ví dụ 3: Lệnh "if-else if-else"
```csharp
int c = 75;
if (c >= 90)
{
    Console.WriteLine("Điểm A");
}
else if (c >= 80)
{
    Console.WriteLine("Điểm B");
}
else if (c >= 70)
{
    Console.WriteLine("Điểm C");
}
else
{
    Console.WriteLine("Điểm D");
}
```

## Giải thích
- **Nằm trong dấu ngoặc**: Điều kiện trong lệnh "if" phải được đặt trong dấu ngoặc đơn. Nếu không, trình biên dịch sẽ báo lỗi.
- **Kiểu dữ liệu**: Điều kiện có thể là bất kỳ biểu thức nào trả về giá trị boolean (true/false).
- **Khối mã rỗng**: Bạn có thể có một lệnh "if" mà không cần khối mã bên trong. Tuy nhiên, điều này có thể gây nhầm lẫn và không được khuyến khích.

### Những điều cần lưu ý
- **Thứ tự kiểm tra**: Trong lệnh "if-else if-else", thứ tự của các điều kiện rất quan trọng. Nếu điều kiện trước đó đúng, các điều kiện tiếp theo sẽ không được kiểm tra.
- **Biến không được khởi tạo**: Đảm bảo rằng các biến được sử dụng trong điều kiện đã được khởi tạo; không khởi tạo có thể dẫn đến lỗi runtime.

## Tóm tắt một dòng
Lệnh "if" trong CSharp cho phép lập trình viên thực hiện các khối mã khác nhau dựa trên việc kiểm tra điều kiện đúng hay sai.