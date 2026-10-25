# Run Log


## סביבה
מערכת הפעלה: Windows
טרמינל: PowerShell בתוך VS Code
תיקיית הפרויקט: C:\Users\User\Desktop\הנדסאים\שנה ב\System Design\event-photo-capstone
---


## 1. node --version
**מה הפקודה עושה:** מציגה את גרסת Node.js המותקנת במחשב.
**תוצאה:** v26.8.1
**עבד?** כן
**אומת:** הגרסה עומדת בדרישת ה-README (Node.js 20 ומעלה).
## 2. npm install
**מה הפקודה עושה:** מתקינה את כל החבילות שמוגדרות ב-package.json לתוך התיקייה node_modules.
**תוצאה:** added 160 packages, audited 161 packages in 19s
**עבד?** כן
**אזהרות שהופיעו:**
  - דווחו 4 פגיעויות אבטחה בחבילות (1 moderate, 1 high, 2 critical). לא הרצתי npm audit fix ולא בדקתי את הפרטים.
  - אזהרה שלחבילה esbuild@0.28.2 יש סקריפט התקנה (postinstall) שלא אושר. בפועל זה לא מנע מהבדיקות ומהשרת לרוץ.
  - הודעה על גרסה חדשה של npm (11.19.0 → 12.2.1). לא עדכנתי.
**מה היה צריך לתקן:** לא נדרש תיקון כדי שהפרויקט ירוץ.
## 3. npm test
**מה הפקודה עושה:** מריצה vitest run, את הבדיקות האוטומטיות של הפרויקט.
**תוצאה:** קובץ בדיקות אחד (tests/event-api.test.ts), 5 בדיקות, כולן עברו.
  - requires a demo photographer identity
  - lists only events belonging to the requested photographer
  - does not return another photographer's event
  - allows a client to submit a selection for their own gallery
  - does not let a client access a different client's gallery
**עבד?** כן
**אומת:** הבדיקות הקיימות בודקות בעיקר הפרדה בין צלמים ובין לקוחות (הרשאות גישה). לא נמצאה בדיקה שקשורה לשינוי שם אירוע.
## 4. npm run typecheck
**מה הפקודה עושה:** מריצה tsc --noEmit. בודקת שאין שגיאות טיפוסים ב-TypeScript, בלי ליצור קבצים ובלי להריץ את הקוד.
**תוצאה:** הפקודה הסתיימה ללא פלט, כלומר לא נמצאו שגיאות טיפוסים.
**עבד?** כן
## 5. npm run dev
**מה הפקודה עושה:** מריצה tsx watch src/server.ts. מעלה את השרת במצב פיתוח, שמתאתחל אוטומטית כשמשנים קוד.
**תוצאה:** Event Photo API listening on http://localhost:3000
**עבד?** כן
**הערה:** עצרתי את השרת עם Ctrl+C.
---


## בעיות ותיקונים
נתיב הפרויקט מכיל תיקיות בשמות עבריים, וזה גרם לקושי במעבר לתיקייה בטרמינל. פתרתי את זה כך: (להשלים)
בסופו של דבר כל הפקודות רצו בהצלחה גם מהנתיב העברי.
## מה אומת ומה לא
**אומת:**
  - גרסת Node מתאימה לדרישות.
  - ההתקנה הצליחה.
  - כל 5 הבדיקות עוברות.
  - אין שגיאות טיפוסים.
  - השרת עולה על פורט 3000.
**לא אומת:**
  - לא פתחתי את השרת בדפדפן ולא שלחתי אליו בקשות.
  - לא בדקתי את פרטי פגיעויות האבטחה.
  - לא בדקתי את המשמעות של אזהרת esbuild.