# نظام الاستعلام عن لجان الطلاب

صفحة ثابتة باللغة العربية للاستعلام عن بيانات لجنة الطالب، مع صفحة إدارة محمية عبر Firebase Authentication وFirestore.

## الملفات

- `index.html`: صفحة الاستعلام برقم الهوية.
- `admin.html`: صفحة إدارة بيانات الطلاب، ولا تعمل إلا بتسجيل دخول حساب الإدارة.
- `firestore.rules`: قواعد حماية Firestore الجاهزة للنسخ إلى Firebase.

## إعداد Firebase المطلوب

1. فعّل `Authentication > Email/Password`.
2. أنشئ مستخدم إدارة بالبريد:
   `abbadschooll@gmail.com`
3. أنشئ `Firestore Database` بوضع `Production mode`.
4. انسخ محتوى `firestore.rules` إلى:
   `Firestore Database > Rules`
5. اضغط `Publish`.

## طريقة الاستخدام

1. افتح `admin.html`.
2. سجل الدخول ببريد الإدارة وكلمة المرور التي أنشأتها في Firebase.
3. ارفع ملف بيانات الطلاب بصيغة `XLSM` أو `XLSX` أو `CSV` أو `JSON`.
4. افتح `index.html` للاستعلام برقم الهوية.

## أعمدة البيانات المدعومة

يمكن أن يحتوي ملف البيانات على أسماء أعمدة عربية أو إنجليزية مثل:

- رقم الهوية: `id`, `studentId`, `nationalId`, `رقم الهوية`, `الهوية`, `السجل المدني`
- اسم الطالب: `name`, `studentName`, `اسم الطالب`, `الاسم`
- رقم الجلوس: `seat`, `seatNumber`, `رقم الجلوس`
- اللجنة: `committee`, `committeeName`, `اللجنة`
- القاعة: `room`, `hall`, `classroom`, `القاعة`, `الفصل`
- الصف: `grade`, `class`, `الصف`
- مقر اللجنة: `location`, `place`, `مقر اللجنة`, `المقر`

## ملاحظة أمنية

مفتاح Firebase الموجود داخل ملفات HTML ليس كلمة مرور، وهو يظهر عادة في تطبيقات الويب. الحماية الفعلية هنا من `Authentication` و`Firestore Rules`.
