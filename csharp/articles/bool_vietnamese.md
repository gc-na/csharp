<!--
Meta Description: # Từ Khóa "bool" trong CSharp: Khám Phá Kiểu Dữ Liệu Boolean ## Tóm Tắt Trong ngôn ngữ lập trình CSharp, `bool` là kiểu dữ liệu dùng để đại diện cho g...
Meta Keywords: trong, bool, các, logic, dụng
-->

# Từ Khóa "bool" trong CSharp: Khám Phá Kiểu Dữ Liệu Boolean

## Tóm Tắt
Trong ngôn ngữ lập trình CSharp, `bool` là kiểu dữ liệu dùng để đại diện cho giá trị logic, có thể là `true` (đúng) hoặc `false` (sai). Kiểu dữ liệu này thường được sử dụng trong các điều kiện kiểm tra và biểu thức logic.

## Tài Liệu
### Mục Đích
Kiểu dữ liệu `bool` trong CSharp được thiết kế để lưu trữ các giá trị logic, cho phép lập trình viên thực hiện các phép so sánh và điều kiện trong chương trình.

### Cách Sử Dụng
`bool` có thể được khai báo và sử dụng trong nhiều ngữ cảnh khác nhau, bao gồm:
- Khai báo biến.
- Sử dụng trong các câu lệnh điều kiện như `if`, `while`, và `for`.
- Trả về từ các hàm kiểm tra giá trị logic.

### Chi Tiết
- **Khai báo**: Bạn có thể khai báo biến kiểu `bool` như sau:
  ```csharp
  bool isActive = true;
  ```
- **Sử dụng trong điều kiện**:
  ```csharp
  if (isActive)
  {
      Console.WriteLine("Đang hoạt động.");
  }
  ```
- **Phép so sánh**: Các phép so sánh như `==`, `!=`, `>`, `<`, `>=`, và `<=` đều trả về giá trị `bool`.

## Ví Dụ
### Ví Dụ 1: Khai Báo và Sử Dụng
```csharp
bool isRaining = false;

if (isRaining)
{
    Console.WriteLine("Mưa rồi, mang ô nhé!");
}
else
{
    Console.WriteLine("Thời tiết đẹp, đi ra ngoài nào!");
}
```

### Ví Dụ 2: Sử Dụng trong Vòng Lặp
```csharp
bool keepRunning = true;
int count = 0;

while (keepRunning)
{
    Console.WriteLine("Đếm: " + count);
    count++;
    if (count >= 5)
    {
        keepRunning = false;
    }
}
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Không khởi tạo biến**: Nếu bạn không khởi tạo biến `bool`, nó sẽ có giá trị mặc định là `false`.
- **Sử dụng sai kiểu**: Đảm bảo bạn chỉ so sánh các giá trị logic với nhau, tránh so sánh giữa các kiểu dữ liệu khác.
- **Phép toán logic**: Khi sử dụng các toán tử logic (`&&`, `||`, `!`), cần phải chú ý đến thứ tự thực hiện để tránh lỗi logic trong chương trình.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `bool` trong CSharp dùng để đại diện cho giá trị logic, cho phép thực hiện các phép so sánh và điều kiện trong lập trình.