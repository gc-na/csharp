<!--
Meta Description: # Từ Khóa "readonly" trong CSharp: Hiểu Biết Cơ Bản và Cách Sử Dụng ## Tóm Tắt Từ khóa `readonly` trong CSharp được sử dụng để xác định các trường mà ...
Meta Keywords: readonly, trường, trong, giá, trị
-->

# Từ Khóa "readonly" trong CSharp: Hiểu Biết Cơ Bản và Cách Sử Dụng

## Tóm Tắt
Từ khóa `readonly` trong CSharp được sử dụng để xác định các trường mà giá trị của chúng chỉ có thể được gán trong quá trình khởi tạo hoặc trong một constructor. Điều này giúp bảo vệ dữ liệu và đảm bảo tính toàn vẹn của các đối tượng trong lập trình hướng đối tượng.

## Tài Liệu
### Mục Đích
Từ khóa `readonly` được sử dụng để ngăn chặn việc thay đổi giá trị của một trường sau khi nó đã được gán. Điều này rất hữu ích khi bạn cần đảm bảo rằng một số thuộc tính của đối tượng không bị thay đổi sau khi đối tượng đã được khởi tạo.

### Cách Sử Dụng
Bạn có thể khai báo một trường là `readonly` bằng cách thêm từ khóa này trước kiểu dữ liệu của trường. Trường `readonly` có thể được gán giá trị trong khối khởi tạo hoặc trong một constructor, nhưng không thể được gán giá trị sau đó.

#### Cú Pháp
```csharp
readonly T fieldName;
```

### Chi Tiết
- **Trường `readonly`** chỉ có thể được gán một lần, và việc gán này phải xảy ra trong khối khởi tạo hoặc constructor.
- Các trường `readonly` có thể được sử dụng với các kiểu giá trị và kiểu tham chiếu.
- `readonly` có thể giúp cải thiện độ an toàn của mã nguồn bằng cách ngăn chặn việc thay đổi không mong muốn.

## Ví Dụ
### Ví dụ 1: Khai báo và sử dụng trường `readonly`
```csharp
public class Example
{
    public readonly int ReadOnlyField;

    public Example(int value)
    {
        ReadOnlyField = value; // Gán giá trị cho trường readonly
    }
}
```

### Ví dụ 2: Sử dụng `readonly` với kiểu tham chiếu
```csharp
public class Person
{
    public readonly string Name;

    public Person(string name)
    {
        Name = name; // Gán giá trị cho trường readonly
    }
}
```

### Ví dụ 3: Cố gắng thay đổi giá trị của trường `readonly`
```csharp
public class Test
{
    public readonly int Number;

    public Test(int number)
    {
        Number = number;
    }

    public void ChangeNumber(int newNumber)
    {
        // Sẽ gây lỗi biên dịch nếu cố gắng gán giá trị mới cho Number
        // Number = newNumber; // Lỗi biên dịch
    }
}
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Gán Giá Trị Sau Khi Khởi Tạo:** Nếu cố gắng gán giá trị cho trường `readonly` sau khi nó đã được khởi tạo, bạn sẽ gặp lỗi biên dịch.
- **Sử Dụng Trong Các Lớp Kế Thừa:** Khi kế thừa, bạn không thể thay đổi giá trị của trường `readonly` trong lớp con sau khi nó đã được thiết lập trong lớp cha.

### Lưu Ý Thêm
- Trường `readonly` không giống như trường `const`; trường `const` phải được gán một giá trị tĩnh tại thời điểm biên dịch, trong khi trường `readonly` có thể được gán một giá trị tại thời điểm chạy.
- Nếu muốn sử dụng một trường có thể thay đổi trong lớp con, hãy xem xét việc sử dụng thuộc tính với getter và setter thay vì `readonly`.

## Tóm Tắt Một Câu
Từ khóa `readonly` trong CSharp cho phép bạn xác định các trường mà giá trị của chúng không thể thay đổi sau khi đã được khởi tạo, giúp bảo vệ tính toàn vẹn của dữ liệu trong lập trình hướng đối tượng.