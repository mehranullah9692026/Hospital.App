# Hospital Manager — Android starter project (Phase 1)

## اس ZIP میں کیا شامل ہے؟
- Android ایپ کا اصل Kotlin اور Jetpack Compose کوڈ
- مریض، ڈاکٹر اور اپائنٹمنٹ کے بنیادی حصے
- Room مقامی ڈیٹا بیس
- Dashboard اور فون کے Light/Dark تھیم کی سپورٹ
- اردو، عربی اور انگریزی کے متن اور RTL سپورٹ
- Android SDK / compileSdk / targetSdk کی سطح 36
- GitHub Actions کے ذریعے Debug APK اور Release AAB بنانے کا Workflow

## SDK اور API کی وضاحت
- `compileSdk = 36`: ایپ Android SDK 36 کے خلاف compile ہوگی۔
- `targetSdk = 36`: ایپ Android 16 / API 36 کو target کرتی ہے۔
- `minSdk = 24`: کم از کم Android 7.0 (API 24) درکار ہے۔
- اس پروجیکٹ میں ابھی کسی حقیقی آن لائن سرور کی API منسلک نہیں ہے۔ صرف SDK نمبر شامل کرنے سے ڈاکٹرز کی آن لائن فہرست، لاگ اِن یا کلاؤڈ ڈیٹا خود بخود نہیں آتا۔ اس کے لیے آپ کے سرور کا Base URL، API documentation اور authentication طریقہ درکار ہوگا۔

## Android Studio میں APK بنانے کا طریقہ
1. ZIP کو Extract کریں۔
2. Android Studio میں اندر موجود `HospitalApp` فولڈر کھولیں۔
3. JDK 17 اور Android SDK Platform 36 انسٹال رکھیں۔
4. Gradle sync مکمل ہونے دیں؛ انٹرنیٹ سے dependencies ڈاؤن لوڈ ہوں گی۔
5. `Build > Build Bundle(s) / APK(s) > Build APK(s)` منتخب کریں۔

## GitHub سے APK اور AAB بنانے کا طریقہ
1. `HospitalApp` فولڈر کے تمام مواد کو GitHub repository میں push کریں۔
2. GitHub میں Actions کھولیں اور `Android build` workflow چلائیں (یا `main` / `master` پر push کریں)۔
3. کامیاب build کے بعد `HospitalApp-builds` artifact ڈاؤن لوڈ کریں۔ اس میں Debug APK اور unsigned Release AAB ہوگا۔

## Google Play کے لیے ضروری باتیں
یہ ZIP خودبخود Play Store پر منظور شدہ نہیں ہے۔ Play Console پر بھیجنے سے پہلے Release AAB کو اپنی محفوظ signing key سے sign کرنا، privacy policy، Data safety، app access، store listing، screenshots، content rating اور متعلقہ Play policies مکمل کرنا ضروری ہے۔ `targetSdk 36` ایک SDK configuration ہے، منظوری کی ضمانت نہیں۔

## ابھی شامل نہیں
- حقیقی ہسپتالوں یا ڈاکٹروں کا آن لائن ڈیٹا/فون نمبر
- Backend server، API endpoint، API key یا cloud sync
- صارفین کا login اور مختلف staff roles
- فارمیسی، لیبارٹری، بلنگ، نسخے، بلڈ بینک اور مریض portal
- Release signing key

**اہم:** اپنی API key یا keystore password کو ZIP، GitHub repository یا عام source code میں نہ ڈالیں۔ حقیقی API جوڑنے کے لیے backend کی تفصیلات درکار ہیں۔

## Build verification
اس ماحول میں Android SDK اور Gradle نصب نہ ہونے کی وجہ سے یہاں APK/AAB compile کرکے کامیابی کی تصدیق نہیں کی جا سکی۔ GitHub Actions workflow اصل build چلائے گا؛ کامیاب workflow مکمل ہونے کے بعد ہی build کو verified سمجھیں۔
