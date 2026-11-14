# مزاين الحلال

دليل المرحان وأصناف الأغنام: كل مراح بمالكه وموقعه وأصنافه وأعداده وأسعاره.

## ملفات الموقع

| الملف | وش فيه |
|---|---|
| `index.html` | الموقع كامل |
| `firebase-config.js` | إعدادات Firebase والحساب البنكي وقيمة الاشتراك (الملف الوحيد اللي تعدّله) |
| `logo.png` و `icon.png` | الشعار وأيقونة الموقع |
| `firestore.rules` | قواعد حماية البيانات، تنلصق في Firebase (مو لازم تكون في المستودع) |

## خطوات التشغيل

### 1) رفع الملفات على GitHub
في صفحة المستودع اضغط **uploading an existing file**، واختر الملفات، ثم **Commit changes**.

### 2) تفعيل GitHub Pages
Settings ← Pages ← Source: **Deploy from a branch** ← Branch: **main** و **/(root)** ← Save.
بعد دقيقة يصير الموقع على:
`https://gouid6666-hash.github.io/Mzayinalhalal/`

### 3) إعداد Firebase (بحساب Gmail)
1. console.firebase.google.com ← **Add project** ← سمّه `mazayen-alhalal`.
2. **Build ← Authentication ← Get started ← Google ← Enable**.
3. في Authentication ← **Settings ← Authorized domains ← Add domain**: `gouid6666-hash.github.io`
4. **Build ← Firestore Database ← Create database** (اختر أقرب موقع، وابدأ بـ production mode).
5. في Firestore ← **Rules**: امسح الموجود، والصق محتوى `firestore.rules`، ثم **Publish**.
6. **Project settings ← Your apps ← أيقونة `</>`** ← سجّل تطبيق ويب، وانسخ قيم `firebaseConfig`.

### 4) تعبئة الإعدادات
في المستودع افتح `firebase-config.js` ← أيقونة القلم ✏️ ← الصق القيم مكان الفراغات، وعدّل بيانات البنك ← **Commit changes**.

### 5) تفعيلك كمشرف
1. افتح الموقع ← حسابي ← سجّل دخول بحساب Google.
2. افتح «رقم الحساب (للإدارة)» وانسخه.
3. في Firestore ← **Start collection** ← الاسم `admins` ← Document ID: الرقم اللي نسخته ← أضف حقل `role` = `admin` ← Save.
4. حدّث الموقع، بيطلع لك زر **لوحة الإدارة** في صفحة حسابي.

## كيف يمشي الاشتراك
1. صاحب المراح يسجّل دخول ويعبّي بيانات مراحه.
2. يحوّل الاشتراك ويرفع صورة الإيصال.
3. أنت من لوحة الإدارة تشوف الإيصال وتضغط **تفعيل شهر**.
4. يظهر مراحه في التطبيق ويقدر يضيف حلاله. بعد 30 يوم يختفي تلقائياً إلى أن يجدد.
