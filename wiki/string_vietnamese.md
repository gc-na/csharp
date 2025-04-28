<!--
Meta Description: # Chuỗi (String) trong CSharp: Khám Phá và Ứng Dụng ## Tóm Tắt Trong CSharp, chuỗi (string) là một kiểu dữ liệu quan trọng được sử dụng để lưu trữ và ...
Meta Keywords: chuỗi, string, csharp, trong, dụng
-->

# Chuỗi (String) trong CSharp: Khám Phá và Ứng Dụng

## Tóm Tắt
Trong CSharp, chuỗi (string) là một kiểu dữ liệu quan trọng được sử dụng để lưu trữ và thao tác với các chuỗi ký tự. Chuỗi trong CSharp là các đối tượng không thay đổi, cho phép lập trình viên thực hiện nhiều thao tác khác nhau như nối, cắt, tìm kiếm và định dạng.

## Tài Liệu
### Mục Đích
Chuỗi (string) trong CSharp là kiểu dữ liệu cơ bản dùng để lưu trữ văn bản. Nó cho phép lập trình viên thực hiện các thao tác xử lý văn bản một cách hiệu quả.

### Sử Dụng
Để khai báo một chuỗi trong CSharp, bạn có thể sử dụng cú pháp sau:

```csharp
string myString = "Hello, World!";
```

### Chi Tiết
- **Khai báo chuỗi**: Sử dụng từ khóa `string` để khai báo biến chuỗi.
- **Chuỗi bất biến**: Một khi chuỗi được tạo ra, nó không thể thay đổi. Mọi thao tác thay đổi chuỗi sẽ tạo ra một chuỗi mới.
- **Nối chuỗi**: Bạn có thể nối các chuỗi bằng cách sử dụng toán tử `+` hoặc phương thức `String.Concat()`.
- **Độ dài**: Sử dụng thuộc tính `Length` để lấy số ký tự trong chuỗi.
- **Các phương thức hữu ích**: Một số phương thức phổ biến bao gồm `Contains()`, `StartsWith()`, `EndsWith()`, `Substring()`, và `IndexOf()`.

## Ví Dụ
### Khai báo và in ra chuỗi
```csharp
string greeting = "Xin chào, thế giới!";
Console.WriteLine(greeting);
```

### Nối chuỗi
```csharp
string firstName = "Nguyễn";
string lastName = "Văn A";
string fullName = firstName + " " + lastName;
Console.WriteLine(fullName);
```

### Tìm kiếm trong chuỗi
```csharp
string sentence = "Học lập trình CSharp thật thú vị!";
bool contains = sentence.Contains("CSharp");
Console.WriteLine(contains); // Kết quả: True
```

## Giải Thích
- **Chuỗi bất biến**: Điều này có thể dẫn đến hiệu suất kém nếu thường xuyên thay đổi chuỗi. Sử dụng `StringBuilder` cho các thao tác nối chuỗi nhiều lần.
- **Kiểm tra null**: Trước khi thao tác với chuỗi, nên kiểm tra xem biến chuỗi có phải là `null` hay không để tránh lỗi ngoại lệ.

## Tóm Tắt Một Dòng
Chuỗi (string) trong CSharp là kiểu dữ liệu quan trọng cho việc lưu trữ và thao tác với văn bản, cho phép thực hiện nhiều phương thức xử lý hiệu quả.