<!--
Meta Description: # Cấu Trúc Lặp "for" trong CSharp: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Cấu trúc lặp "for" trong CSharp cho phép lập trình viên tạo ra các vòng lặp ...
Meta Keywords: lặp, vòng, một, điều, thực
-->

# Cấu Trúc Lặp "for" trong CSharp: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Cấu trúc lặp "for" trong CSharp cho phép lập trình viên tạo ra các vòng lặp với một số lượng lặp xác định, giúp tự động hóa các tác vụ lặp đi lặp lại một cách hiệu quả.

## Tài Liệu
Cấu trúc lặp "for" là một trong những lệnh điều khiển dòng chảy cơ bản trong ngôn ngữ lập trình C#. Nó cho phép thực hiện một đoạn mã nhiều lần cho đến khi một điều kiện nhất định không còn đúng. Cú pháp cơ bản của vòng lặp "for" như sau:

```csharp
for (khởi_tạo; điều_kiện; bước_thực_hiện)
{
    // Đoạn mã sẽ được thực thi
}
```

### Các Thành Phần:
- **khởi_tạo**: Được thực thi một lần trước khi vòng lặp bắt đầu. Thường được sử dụng để khai báo và khởi tạo biến điều khiển vòng lặp.
- **điều_kiện**: Được kiểm tra trước mỗi lần lặp. Nếu điều kiện này đúng, vòng lặp sẽ tiếp tục thực hiện. Nếu sai, vòng lặp sẽ dừng lại.
- **bước_thực_hiện**: Được thực thi sau mỗi lần lặp. Thường được sử dụng để thay đổi giá trị của biến điều khiển vòng lặp.

## Ví Dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng vòng lặp "for":

### Ví dụ 1: Lặp qua các số từ 1 đến 5
```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```
**Kết quả:**
```
1
2
3
4
5
```

### Ví dụ 2: Tính tổng các số từ 1 đến 10
```csharp
int sum = 0;
for (int i = 1; i <= 10; i++)
{
    sum += i;
}
Console.WriteLine("Tổng là: " + sum);
```
**Kết quả:**
```
Tổng là: 55
```

## Giải Thích
Khi làm việc với vòng lặp "for", có một số điều cần lưu ý:
- **Biến điều khiển**: Đảm bảo rằng biến điều khiển không bị thay đổi bên ngoài vòng lặp, điều này có thể dẫn đến vòng lặp vô hạn.
- **Điều kiện**: Luôn chắc chắn rằng điều kiện sẽ trở thành sai tại một thời điểm nào đó để tránh việc vòng lặp chạy mãi mãi.
- **Bước thực hiện**: Nếu quên không cập nhật biến điều khiển trong bước thực hiện, vòng lặp sẽ không bao giờ kết thúc.

## Tóm Tắt Một Dòng
Cấu trúc lặp "for" trong CSharp là một công cụ mạnh mẽ cho phép lập trình viên thực hiện các tác vụ lặp đi lặp lại một cách có kiểm soát và hiệu quả.