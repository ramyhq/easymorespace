# 🛠️ Easy More Space — Troubleshooting Guide
## دليل حل المشاكل — ويندوز وماك

---

## ويندوز (Windows)

### ❌ التطبيق مش بيفتح / "Windows protected your PC"

**السبب:** Windows SmartScreen بيمنع التطبيقات غير الموقعة.

**الحل:**
```
١- اضغط "More info"
٢- اضغط "Run anyway"
```

**للنشر (للمطور):** اشترِ شهادة Code Signing (EV Certificate) ووقّع الـ `.exe`.

---

### ❌ "Python is not installed"

**السبب:** بتحاول تشغّل `app.pyw` مباشرة بدل الـ `.exe`.

**الحل:** التطبيق `.exe` قائم بذاته — مش محتاج بايثون متثبت. شغّله من الملف:
```
dist\EasyMoreSpace_v9.1.exe
```

---

### ❌ "VCRUNTIME140.dll was not found"

**السبب:** Microsoft Visual C++ Redistributable مش مثبت.

**الحل:** حمّل من مايكروسوفت:
- [VC++ Redistributable x64](https://aka.ms/vs/17/release/vc_redist.x64.exe)
- ثبت واعمل Restart للجهاز.

---

### ❌ الصوت مش شغال بعد الضغط

**السبب:** الصوت مكتوم (Mute) من جوه التطبيق.

**الحل:** اضغط على زر 🔊/🔇 (فوق على اليمين) لتشغيل الصوت.

---

### ❌ "Another instance is already running"

**السبب:** التطبيق شغال بالفعل في الخلفية. نظام القفل بيمنع تشغيل نسختين.

**الحل:**
- افتح Task Manager (`Ctrl + Shift + Esc`)
- دور على `EasyMoreSpace_v9.1.exe`
- اعمل End Task
- أو اعمل Restart للجهاز

---

### ❌ الإعلانات مش بتظهر / خطأ في الاتصال

**السبب:** مفيش اتصال إنترنت.

**الحل:**
- تأكد من اتصالك بالإنترنت
- لو النت شغال: جرب تشغل التطبيق كـ Administrator (كليك يمين → Run as administrator)
- التطبيق بيستخدم إعلانات محلية لو النت مش متوفر

---

## ماك (macOS)

### ❌ "can't be opened because it may be damaged or incomplete"

**السبب:** macOS Gatekeeper بيمنع التطبيقات غير الموقعة (quarantine).

**الحل — الطريقة الأولى (الأسهل):**
```
افتح Terminal واكتب:
xattr -cr /path/to/EasyMoreSpace_v9.1.app
```
(اسحب ملف `.app` وأفلته في الـ Terminal بعد `xattr -cr` عشان يكتب المسار تلقائي)

**الحل — الطريقة الثانية (يدوي):**
```
System Settings → Privacy & Security → اضغط "Open Anyway"
```

---

### ❌ "App is damaged and should be moved to Trash"

**السبب:** مشكلة في التوقيع الرقمي أو نقل التطبيق من جهاز تاني.

**الحل — نفّذ الأمر ده في Terminal:**
```bash
xattr -cr /path/to/EasyMoreSpace_v9.1.app
codesign --force --deep --sign - /path/to/EasyMoreSpace_v9.1.app
```

---

### ❌ التطبيق مش بيظهر في Launchpad / Dock

**السبب:** التطبيق مش منسوخ لمجلد `Applications`.

**الحل:** اسحب `EasyMoreSpace_v9.1.app` إلى مجلد `/Applications`.

---

### ❌ أيقونة التطبيق شكلها مش مضبوط

**السبب:** macOS بيطبّق rounding تلقائي على الأيقونات، لكن لو الأيقونة الأصلية مش متصممة بشكل صحيح ممكن يظهر شكل مش حلو.

**الحل (للمطور):** صمّم أيقونة PNG بحجم 1024×1024 مع:
- خلفية شفافة (Transparent)
- زوايا دائرية (Rounded corners) بنسبة ~20%
- أو استخدم أداة "Apple Icon Image" لتصميم أيقونة بمواصفات الماك

---

### ❌ الصوت مش شغال

**السبب:** الصوت مكتوم (Mute) من جوه التطبيق.

**الحل:** اضغط على زر 🔊/🔇 (فوق على اليمين) لتشغيل الصوت.

---

### ❌ "Another instance is already running"

**السبب:** التطبيق شغال بالفعل في الخلفية.

**الحل:**
```
افتح Terminal واكتب:
pkill -f EasyMoreSpace
```
أو اعمل Log out وLog in من جديد.

---

## عام (ويندوز وماك)

### ❌ الصور المضغوطة حجمها كبير / مش فارقة

**السبب:** إعدادات الضغط منخفضة.

**الحل:**
- حرك شريط **الجودة (Quality)** إلى اليسار (مثلاً 60-70%)
- حرك شريط **الحجم (Size)** إلى اليسار (مثلاً 40-50%)
- جرّب صيغة **WebP** أو **AVIF** — بتدي حجم أصغر بنفس الجودة

---

### ❌ الصور المضغوطة مشوهة / جودتها سيئة

**السبب:** إعدادات الضغط عالية جداً.

**الحل:**
- حرك شريط **الجودة (Quality)** إلى اليمين (80-100%)
- حرك شريط **الحجم (Size)** إلى اليمين (80-100%)
- لو بتستخدم WebP/AVIF، جرّب JPG

---

### ❌ مش عارف أوصل للملفات المضغوطة

**السبب:** الملفات المضغوطة بتتحط في مجلد `اسم_المجلد_compressed` جوه مجلد المصدر.

**الحل:**
- بعد الضغط، اضغط زر **"Open Folder"** الأزرق — هيفتحلك المجلد مباشرة
- أو افتح المجلد اللي فيه الصور الأصلية، هتلاقي مجلد `_compressed` جواه

---

### ❌ زر Compress / Rename مش شغال

**السبب (١):** مختارش مجلد مصدر أو ملفات.

**الحل:** اختر مجلد (Folder Mode) أو ملفات (Files Mode) الأول.

**السبب (٢):** مكتوب خيار "Rename only" ومش محتاج تضغط.

**الحل:** تأكد إنك عاوز تضغط ولا تسمي فقط (Rename only).

---

### ❌ التطبيق بطيء / بيهنج

**السبب (١):** عدد صور كبير جداً (أكتر من ١٠٠٠ صورة).

**الحل:** قسم الصور على دفعات أصغر.

**السبب (٢):** صور بحجم كبير جداً (RAW, TIFF ضخمة).

**الحل:** استخدم صيغة JPG أو WebP output.

---

### ❌ الترجمة مش متوفرة بلغتي

**السبب:** التطبيق بيدعم ٣ لغات: English, العربية, Français.

**الحل:** اضغط على زر اللغة (أعلى اليمين) لتغيير اللغة.

---

## 🧹 مسح القفل (Single Instance Lock)

لو التطبيق مش عاوز يشتغل وبيقفل على طول بسبب "Another instance":

**ويندوز:**
```
احذف الملف: %TEMP%\.easymorespace.lock
```
(انسخ المسار ده والصقه في File Explorer)

**ماك:**
```bash
rm ~/.easymorespace.lock
```

---

## 📞 للدعم

لو المشكلة لسه موجودة:
- **Website:** [dev.ifeps.net](https://dev.ifeps.net)
- **Support:** [ko-fi.com/ramydmk](https://ko-fi.com/ramydmk)

---

> **Developer:** Ramy Wahid  
> **Version:** 9.1  
> **Platform:** Windows 10/11 · macOS 12+
