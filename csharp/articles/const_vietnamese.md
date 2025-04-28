<!--
Meta Description: # Từ Khóa "const" trong C#: Định Nghĩa và Cách Sử Dụng ## Tóm Tắt Từ khóa `const` trong C# được sử dụng để khai báo các hằng số, cho phép người lập tr...
Meta Keywords: const, được, hằng, trong, dụng
-->

# Từ Khóa "const" trong C#: Định Nghĩa và Cách Sử Dụng

## Tóm Tắt
Từ khóa `const` trong C# được sử dụng để khai báo các hằng số, cho phép người lập trình định nghĩa các giá trị không thay đổi trong suốt vòng đời của ứng dụng. Hằng số giúp cải thiện tính khả thi và dễ bảo trì cho mã nguồn.

## Tài Liệu
### Mục Đích
Từ khóa `const` được sử dụng để định nghĩa các biến có giá trị không thay đổi. Khi một biến được khai báo là `const`, giá trị của nó phải được khởi tạo ngay tại thời điểm khai báo và không thể thay đổi trong suốt thời gian thực thi chương trình.

### Cách Sử Dụng
Để sử dụng `const`, bạn chỉ cần khai báo biến với từ khóa này trước kiểu dữ liệu. Dưới đây là cú pháp cơ bản:

```csharp
const <KiểuDữLiệu> <TênBiến> = <GiáTrị>;
```

### Chi tiết
- Biến `const` phải được khởi tạo ngay khi khai báo.
- Giá trị của biến không thể thay đổi sau khi được gán.
- `const` có thể được sử dụng với các loại dữ liệu cơ bản như `int`, `double`, `string`, và các kiểu dữ liệu tùy chỉnh.
- Hằng số có thể được truy cập từ mọi nơi trong mã nguồn, miễn là chúng có phạm vi truy cập thích hợp.

## Ví Dụ
Dưới đây là một số ví dụ minh họa về cách sử dụng từ khóa `const` trong C#:

```csharp
// Khai báo hằng số kiểu int
const int SoNgayTrongTuan = 7;

// Khai báo hằng số kiểu double
const double Pi = 3.14;

// Khai báo hằng số kiểu string
const string TenCongTy = "Công ty ABC";
```

Trong ví dụ trên, các hằng số được định nghĩa và có thể được sử dụng trong toàn bộ chương trình mà không cần lo lắng về việc thay đổi giá trị của chúng.

## Giải Thích
### Cạm Bẫy Thường Gặp
1. **Khởi Tạo Không Đúng**: Hằng số phải được khởi tạo ngay khi khai báo. Nếu không, bạn sẽ gặp lỗi biên dịch.
   
2. **Giá Trị Không Thay Đổi**: Một khi hằng số đã được gán giá trị, bạn không thể thay đổi nó. Cố gắng gán lại giá trị sẽ dẫn đến lỗi biên dịch.

3. **Phạm Vi Truy Cập**: Hằng số có thể có phạm vi truy cập khác nhau (public, private, protected), cần chú ý khi khai báo để tránh vấn đề về truy cập.

### Ghi Chú Bổ Sung
Sử dụng `const` có thể giúp mã nguồn của bạn dễ đọc và dễ bảo trì hơn. Tuy nhiên, nếu bạn cần một hằng số mà giá trị có thể thay đổi trong thời gian chạy, hãy xem xét sử dụng từ khóa `readonly`.

## Tóm Tắt Một Dòng
Từ khóa `const` trong C# cho phép định nghĩa các hằng số không thay đổi giá trị trong suốt vòng đời của chương trình.