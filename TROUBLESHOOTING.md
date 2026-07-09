# Troubleshooting Guide — دليل حل المشاكل

## Windows

| Problem | Solution |
|---------|----------|
| "Windows protected your PC" | Click **More info** → **Run anyway** |
| "VCRUNTIME140.dll not found" | Install [VC++ Redistributable x64](https://aka.ms/vs/17/release/vc_redist.x64.exe) and restart |
| "Python is not installed" | You ran `app.pyw` directly. Use the .exe instead: `dist\EasyMoreSpace_v9.1.exe` |
| Sound not working after compression | Sound is muted inside the app — click 🔊/🔇 button (top right) |
| "Another instance is already running" | Open Task Manager (`Ctrl+Shift+Esc`) → find `EasyMoreSpace_v9.1.exe` → End Task |
| Ads not showing / connection error | Check internet connection. Try Run as Administrator. App falls back to local ads offline. |

Delete lock file manually: `%TEMP%\.easymorespace.lock`

## macOS

| Problem | Solution |
|---------|----------|
| "App is damaged / can't be opened" | Run in Terminal: `xattr -cr /path/to/EasyMoreSpace_v9.1.app` |
| "App is damaged and should be moved to Trash" | `xattr -cr /path/to/EasyMoreSpace_v9.1.app` then `codesign --force --deep --sign - /path/to/EasyMoreSpace_v9.1.app` |
| App not in Launchpad / Dock | Drag `.app` to `/Applications` folder |
| App icon looks wrong | Developer: design 1024x1024 PNG with transparent background & ~20% rounded corners |
| Sound not working | Click 🔊/🔇 button inside the app (top right) |
| "Another instance is already running" | Run in Terminal: `pkill -f EasyMoreSpace` |

Delete lock file manually: `rm ~/.easymorespace.lock`

For macOS Gatekeeper bypass without Terminal: **System Settings → Privacy & Security → Open Anyway**

## General — عام

| Problem | Solution |
|---------|----------|
| Compressed images still large | Lower Quality slider (60-70%) and Size slider (40-50%). Try WebP or AVIF output. |
| Compressed images look bad | Raise Quality slider (80-100%) and Size slider (80-100%). Try JPG instead of WebP/AVIF. |
| Can't find compressed files | They're in `sourcefolder_compressed`. Click the blue **Open Folder** button after compression. |
| Compress / Rename button not working | Select a source folder or files first. Check you're not in "Rename Only" mode. |
| App is slow / hangs | Split large folders into smaller batches. Avoid huge RAW/TIFF files — use JPG/WebP output. |
| Language not available | App supports English, العربية, Français. Click language button (top right). |

---

## ويندوز

| المشكلة | الحل |
|---------|------|
| "Windows protected your PC" | اضغط **More info** ثم **Run anyway** |
| "VCRUNTIME140.dll not found" | حمّل [VC++ Redistributable x64](https://aka.ms/vs/17/release/vc_redist.x64.exe) واعمل Restart |
| "Python is not installed" | شغّلت `app.pyw` مباشرة. استخدم الملف `.exe` من `dist\EasyMoreSpace_v9.1.exe` |
| الصوت مش شغال بعد الضغط | الصوت مكتوم — اضغط زر 🔊/🔇 (فوق على اليمين) |
| "Another instance is already running" | افتح Task Manager (`Ctrl+Shift+Esc`) → دور على `EasyMoreSpace_v9.1.exe` → End Task |
| الإعلانات مش بتظهر | تأكد من الإنترنت. جرب Run as Administrator. التطبيق بيستخدم إعلانات محلية بدون نت. |

## ماك

| المشكلة | الحل |
|---------|------|
| "App is damaged / can't be opened" | افتح Terminal واكتب: `xattr -cr /path/to/EasyMoreSpace_v9.1.app` |
| "App is damaged and should be moved to Trash" | `xattr -cr` ثم `codesign --force --deep --sign -` |
| التطبيق مش في Launchpad | اسحب `.app` إلى مجلد `/Applications` |
| أيقونة التطبيق مش مظبوطة | للمطور: صمم PNG 1024×1024 بخلفية شفافة وزوايا دائرية |
| الصوت مش شغال | اضغط زر 🔊/🔇 جوه التطبيق (فوق على اليمين) |
| "Another instance is already running" | افتح Terminal واكتب: `pkill -f EasyMoreSpace` |

## عام

| المشكلة | الحل |
|---------|------|
| الصور المضغوطة حجمها كبير | قلل شريط الجودة (60-70%) والحجم (40-50%). جرب WebP أو AVIF. |
| الصور المضغوطة مشوهة | ارفع شريط الجودة (80-100%) والحجم (80-100%). جرب JPG. |
| مش عارف أوصل للملفات المضغوطة | في مجلد `اسم_المجلد_compressed`. اضغط زر **Open Folder** الأزرق. |
| زر Compress / Rename مش شغال | اختر مجلد أو ملفات الأول. تأكد إنك مش على وضع "Rename Only". |
| التطبيق بطيء | قسم الصور على دفعات أصغر. تجنب RAW/TIFF الضخمة. |
| اللغة مش متوفرة | التطبيق بيدعم English, العربية, Français. اضغط زر اللغة (فوق على اليمين). |

---

> **Developer:** Ramy Waheed · **Version:** 9.1 · **Platform:** Windows 10/11 · macOS 12+
>
> **GitHub:** [github.com/ramyhq/easymorespace](https://github.com/ramyhq/easymorespace)
