# حلو الملك — الموقع + لوحة التحكم (Firebase)

الهيكل:
- `index.html` الموقع، و`admin/index.html` لوحة التحكم (على GitHub Pages: `.../admin/`)
- `firebase.js` إعدادات Firebase (مشترك)
- `firestore.rules` و`storage.rules` قواعد الأمان (تتلصق في Firebase Console)
- `images/` صور الموقع الافتراضية (اختياري، بعد ما ترفع صور من اللوحة مش هتحتاجها)

## تجهيز Firebase (مرة واحدة)
1. Authentication ← Sign-in method ← فعّل **Email/Password**.
2. Firestore Database ← Create database ← بعدين تبويب **Rules** والصق `firestore.rules` واضغط Publish.
3. Storage ← Get started ← تبويب **Rules** والصق `storage.rules` واضغط Publish.
   (لو Firebase طلب ترقية لخطة Blaze عشان Storage، قولّي وأحوّل رفع الصور لحل بديل.)
4. Authentication ← Users ← Add user (إيميل وباسورد الأدمن) وانسخ **User UID**.
5. Firestore ← Start collection اسمها `admins` ← Document ID = الـ UID ده (أضف أي حقل، مثلاً `ok: true`).
6. Authentication ← Settings ← Authorized domains: أضف `اسم-حسابك.github.io`.

## الرفع على GitHub Pages
1. ارفع محتويات فولدر `site` كلها على ريبو (الملفات في الجذر).
2. Settings ← Pages ← Branch: `main` / Root ← Save.
3. الموقع: `https://اسم-حسابك.github.io/اسم-الريبو/` واللوحة: `.../admin/`

## أول استخدام
ادخل اللوحة ← **الإعدادات** ← "نقل البيانات الأولية للقاعدة" (مرة واحدة). بعدها كل الأقسام والمنتجات والبانرات بتتعدّل من اللوحة.
