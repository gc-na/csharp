# [לינוקס] C Shell (csh) diff שימוש: השוואת קבצים

## Overview
הפקודה `diff` משמשת להשוואת תוכן של שני קבצים או יותר. היא מציגה את ההבדלים בין הקבצים בצורה ברורה, מה שמסייע למשתמשים להבין מה השתנה בין גרסאות שונות של קובץ.

## Usage
הסינטקס הבסיסי של הפקודה הוא:

```
diff [אפשרויות] [ארגומנטים]
```

## Common Options
- `-u`: מציג את ההבדלים בצורה מאוחדת (unified format).
- `-c`: מציג את ההבדלים בצורה קונטקסטואלית (context format).
- `-i`: מתעלם מהבדלים באותיות רישיות.
- `-w`: מתעלם מהבדלים ברווחים.

## Common Examples
1. השוואת שני קבצים פשוטים:
   ```csh
   diff file1.txt file2.txt
   ```

2. השוואת קבצים עם התעלמות מרווחים:
   ```csh
   diff -w file1.txt file2.txt
   ```

3. הצגת הבדלים בצורה מאוחדת:
   ```csh
   diff -u file1.txt file2.txt
   ```

4. הצגת הבדלים בצורה קונטקסטואלית:
   ```csh
   diff -c file1.txt file2.txt
   ```

## Tips
- השתמש באפשרות `-u` כדי לקבל תצוגה נוחה וברורה של ההבדלים.
- אם אתה עובד עם קבצים גדולים, שקול להשתמש בפקודות כמו `less` או `more` כדי לדפדף בתוצאות.
- שמור על גיבויים של הקבצים המקוריים לפני ביצוע שינויים, כדי למנוע אובדן מידע.