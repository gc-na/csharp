<!--
Meta Description: # C# foreach: Câu lệnh lặp cho mảng và danh sách ## Tóm tắt Câu lệnh `foreach` trong C# cho phép lập trình viên duyệt qua từng phần tử trong một tập h...
Meta Keywords: hợp, foreach, trong, tập, lặp
-->

# C# foreach: Câu lệnh lặp cho mảng và danh sách

## Tóm tắt
Câu lệnh `foreach` trong C# cho phép lập trình viên duyệt qua từng phần tử trong một tập hợp như mảng, danh sách, hoặc các cấu trúc dữ liệu khác một cách dễ dàng và hiệu quả.

## Tài liệu
Câu lệnh `foreach` là một trong những cấu trúc điều khiển lặp trong C#. Mục đích chính của `foreach` là để lặp qua các phần tử của một tập hợp mà không cần phải quản lý chỉ số như trong các vòng lặp truyền thống như `for`. Cấu trúc của câu lệnh `foreach` giúp mã nguồn trở nên sạch hơn, dễ đọc hơn và giảm thiểu nguy cơ phát sinh lỗi khi xử lý các phần tử trong tập hợp.

### Cú pháp
```csharp
foreach (var item in collection)
{
    // Thao tác với item
}
```

- `item`: Biến đại diện cho từng phần tử trong tập hợp.
- `collection`: Tập hợp mà bạn muốn lặp qua (có thể là mảng, danh sách, hoặc bất kỳ loại tập hợp nào có khả năng truy cập từng phần tử).

## Ví dụ
### Ví dụ 1: Lặp qua một mảng
```csharp
string[] fruits = { "Táo", "Chuối", "Cam" };
foreach (var fruit in fruits)
{
    Console.WriteLine(fruit);
}
```

### Ví dụ 2: Lặp qua một danh sách
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
foreach (var number in numbers)
{
    Console.WriteLine(number);
}
```

### Ví dụ 3: Lặp qua một từ điển
```csharp
Dictionary<string, string> capitals = new Dictionary<string, string>
{
    { "Việt Nam", "Hà Nội" },
    { "Nhật Bản", "Tokyo" },
    { "Hoa Kỳ", "Washington D.C." }
};

foreach (var kvp in capitals)
{
    Console.WriteLine($"Quốc gia: {kvp.Key}, Thủ đô: {kvp.Value}");
}
```

## Giải thích
Khi sử dụng `foreach`, có một số điều cần lưu ý:

1. **Không thể thay đổi kích thước của tập hợp**: Trong khi lặp qua tập hợp, bạn không thể thêm hoặc xóa phần tử khỏi tập hợp đó, nếu không sẽ gây ra ngoại lệ `InvalidOperationException`.

2. **Kiểu của biến**: Nếu bạn không chắc chắn về kiểu dữ liệu của các phần tử trong tập hợp, bạn có thể sử dụng từ khóa `var`, nhưng hãy đảm bảo rằng tập hợp có kiểu dữ liệu đồng nhất.

3. **Sự hiệu quả**: Trong một số trường hợp, `foreach` có thể không hiệu quả như vòng lặp `for` truyền thống, đặc biệt trong các tập hợp lớn hoặc khi cần truy cập theo chỉ số. Tuy nhiên, `foreach` thường được ưa chuộng vì tính đơn giản và dễ đọc.

## Tóm tắt
Câu lệnh `foreach` trong C# cung cấp một cách đơn giản và hiệu quả để lặp qua các phần tử trong tập hợp mà không cần quản lý chỉ số, giúp mã nguồn trở nên rõ ràng hơn.