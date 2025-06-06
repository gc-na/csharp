# [نظام تشغيل لينكس] C Shell (csh) chage الاستخدام: إدارة معلومات انتهاء صلاحية كلمة المرور

## Overview
أمر `chage` يُستخدم لإدارة معلومات انتهاء صلاحية كلمة المرور للمستخدمين في نظام لينكس. يتيح لك هذا الأمر تعديل إعدادات مثل الحد الأقصى لعدد الأيام التي يمكن أن تمر قبل أن يُطلب من المستخدم تغيير كلمة المرور.

## Usage
الصيغة الأساسية للأمر هي:
```
chage [options] [arguments]
```

## Common Options
- `-l`: عرض معلومات انتهاء صلاحية كلمة المرور للمستخدم.
- `-m`: تحديد الحد الأدنى لعدد الأيام بين تغييرات كلمة المرور.
- `-M`: تحديد الحد الأقصى لعدد الأيام قبل أن يُطلب تغيير كلمة المرور.
- `-I`: تحديد عدد الأيام بعد انتهاء صلاحية كلمة المرور قبل أن يتم تعطيل الحساب.
- `-E`: تحديد تاريخ انتهاء صلاحية الحساب.

## Common Examples
- لعرض معلومات انتهاء صلاحية كلمة المرور لمستخدم معين:
  ```bash
  chage -l username
  ```

- لتحديد الحد الأدنى لعدد الأيام بين تغييرات كلمة المرور إلى 7 أيام:
  ```bash
  chage -m 7 username
  ```

- لتحديد الحد الأقصى لعدد الأيام قبل أن يُطلب تغيير كلمة المرور إلى 90 يومًا:
  ```bash
  chage -M 90 username
  ```

- لتحديد عدد الأيام بعد انتهاء صلاحية كلمة المرور قبل تعطيل الحساب إلى 30 يومًا:
  ```bash
  chage -I 30 username
  ```

- لتحديد تاريخ انتهاء صلاحية الحساب إلى 1 يناير 2024:
  ```bash
  chage -E 2024-01-01 username
  ```

## Tips
- تأكد من مراجعة إعدادات كلمة المرور بانتظام لضمان أمان النظام.
- استخدم الخيار `-l` بشكل دوري للتحقق من حالة كلمات المرور للمستخدمين.
- يُفضل تحديد قيم معقولة للحد الأدنى والحد الأقصى لعدد الأيام لتجنب فقدان الوصول إلى الحسابات.