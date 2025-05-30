# [لينكس] C Shell (csh) tcpdump الاستخدام: التقاط وتحليل حزم الشبكة

## Overview
يعتبر أمر tcpdump أداة قوية لالتقاط وتحليل حزم الشبكة. يستخدم بشكل شائع لمراقبة حركة المرور على الشبكة، مما يساعد في تشخيص المشكلات وفهم سلوك الشبكات.

## Usage
الصيغة الأساسية للأمر هي:
```bash
tcpdump [options] [arguments]
```

## Common Options
- `-i`: تحديد واجهة الشبكة التي سيتم التقاط الحزم منها.
- `-n`: عدم تحويل عناوين IP إلى أسماء مضيفين.
- `-v`: عرض معلومات تفصيلية عن الحزم.
- `-c`: تحديد عدد الحزم التي سيتم التقاطها.
- `-w`: كتابة الحزم الملتقطة إلى ملف.

## Common Examples
- لالتقاط الحزم على واجهة الشبكة الافتراضية:
```bash
tcpdump -i eth0
```

- لالتقاط 10 حزم فقط:
```bash
tcpdump -c 10 -i eth0
```

- لالتقاط الحزم مع عدم تحويل عناوين IP:
```bash
tcpdump -n -i eth0
```

- لكتابة الحزم الملتقطة إلى ملف:
```bash
tcpdump -i eth0 -w capture.pcap
```

- لعرض الحزم بتفاصيل إضافية:
```bash
tcpdump -v -i eth0
```

## Tips
- تأكد من تشغيل tcpdump كجذر أو باستخدام صلاحيات كافية لالتقاط الحزم.
- استخدم الخيار `-w` لحفظ الحزم الملتقطة لتحليلها لاحقًا باستخدام أدوات مثل Wireshark.
- كن حذرًا عند التقاط الحزم على الشبكات العامة، حيث يمكن أن تحتوي على معلومات حساسة.