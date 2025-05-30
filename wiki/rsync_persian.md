# [سیستم‌عامل] C Shell (csh) rsync استفاده: همگام‌سازی فایل‌ها و دایرکتوری‌ها

## Overview
دستور `rsync` ابزاری قدرتمند برای همگام‌سازی و انتقال فایل‌ها و دایرکتوری‌ها بین سیستم‌های مختلف است. این دستور به‌ویژه برای انتقال فایل‌ها به صورت محلی یا از راه دور و همچنین برای پشتیبان‌گیری از داده‌ها کاربرد دارد.

## Usage
سینتکس پایه‌ی دستور `rsync` به صورت زیر است:

```bash
rsync [options] [arguments]
```

## Common Options
- `-a`: حالت آرشیو، شامل تمام ویژگی‌های فایل (مانند مجوزها و زمان‌ها).
- `-v`: نمایش اطلاعات بیشتر در حین اجرا (verbose).
- `-z`: فشرده‌سازی داده‌ها در حین انتقال.
- `-r`: انتقال دایرکتوری‌ها به صورت بازگشتی.
- `--delete`: حذف فایل‌های مقصد که در مبدا وجود ندارند.

## Common Examples
### مثال 1: همگام‌سازی یک دایرکتوری محلی
برای همگام‌سازی دایرکتوری `source` با دایرکتوری `destination`:

```bash
rsync -av source/ destination/
```

### مثال 2: همگام‌سازی با سرور از راه دور
برای همگام‌سازی دایرکتوری محلی با یک سرور از راه دور:

```bash
rsync -avz source/ user@remote_host:/path/to/destination/
```

### مثال 3: همگام‌سازی و حذف فایل‌های اضافی
برای همگام‌سازی و حذف فایل‌هایی که در مبدا وجود ندارند:

```bash
rsync -av --delete source/ destination/
```

## Tips
- همواره از گزینه `-n` (dry run) استفاده کنید تا قبل از اجرای واقعی، تغییرات را مشاهده کنید.
- برای انتقال فایل‌های بزرگ، گزینه `-z` را فراموش نکنید تا سرعت انتقال افزایش یابد.
- از `rsync` برای ایجاد نسخه‌های پشتیبان منظم استفاده کنید تا از داده‌های خود محافظت کنید.