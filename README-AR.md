# تطبيق اكسس باي (أندرويد)

تطبيق أندرويد بيفتح https://treee.ink/acc/ جوه التطبيق (WebView) مع:
- أيقونة وألوان الموقع (#0E7A45)، ودعم كامل للعربي و RTL
- زر الرجوع بيرجع صفحة في الموقع، وسحب للتحديث
- شريط تحميل، وصفحة "مفيش اتصال" لما النت يقطع
- الروابط الخارجية (واتساب، اتصال، إيميل، مواقع تانية) بتتفتح برا التطبيق
- دعم رفع الملفات والصور من داخل الموقع
- الكوكيز محفوظة فتسجيل الدخول بيفضل شغال

## أسهل طريقة تطلّع APK (من غير ما تثبّت حاجة)

1. اعمل حساب على GitHub وأنشئ Repository جديد (Private عادي).
2. ارفع كل محتويات الفولدر ده فيه (Upload files).
3. افتح تبويب **Actions** وستلاقي "Build APK" بيشتغل لوحده (أو اضغط Run workflow).
4. بعد ما يخلص (حوالي 3–5 دقايق) افتح التشغيل ونزّل **AccessPay-apk** من Artifacts.
5. فك الضغط وهتلاقي `app-release.apk`، انقله للموبايل وثبّته.

## الطريقة التانية: Android Studio

1. افتح Android Studio ← Open ← اختار الفولدر ده.
2. استنى الـ Sync يخلص.
3. من القايمة: Build ← Build APK(s).
4. الملف هيبقى في `app/build/outputs/apk/`.

لو Android Studio طلب نسخة Gradle اختار 8.9 أو أحدث.

## تعديلات سريعة

- رابط الموقع: `START_URL` و `APP_HOST` في `MainActivity.java`
- اسم التطبيق: `res/values/strings.xml`
- اللون: `res/values/colors.xml`
- الأيقونة: `res/drawable/ic_launcher_foreground.xml`

## للنشر على Google Play

الـ APK ده موقّع بمفتاح debug عشان يتثبّت مباشرة على الموبايلات. للنشر على Play Store لازم:
1. تعمل مفتاح توقيع خاص بيك (keystore) وتحتفظ بيه.
2. تضبط `signingConfigs.release` في `app/build.gradle`.
3. تبني AAB من Android Studio: Build ← Generate Signed Bundle.
4. تغيّر `applicationId` لو عايز اسم حزمة مختلف عن `com.accesspay.app`.
