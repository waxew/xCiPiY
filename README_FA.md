# CiPi Pro - Project Documentation

## هدف پروژه

هدف این پروژه ادامه توسعه و اصلاح CiPi Pro بر اساس APK سالم موجود است، بدون بازسازی کامل پروژه در Android Studio و بدون تغییر معماری اصلی برنامه.

هدف نهایی:

- حفظ نسخه نصب‌شده قبلی
- ساخت نسخه Candidate قابل Update
- حفظ اطلاعات مشتری‌ها، فاکتورها، حساب‌ها، Backup و Schema
- اصلاح فقط مشکلات مشخص‌شده

---

## روش ساخت شناسایی‌شده

CiPi Pro بر اساس ساختار زیر توسعه داده شده است:

```
APK سالم قبلی
        |
        v
Extract APK
        |
        +----------------+
        |                |
        v                v
WebView Asset Layer    Native Wrapper
HTML/JS/CSS            DEX/Manifest/Bridge
        |
        v
اصلاح Asset ها
        |
        v
Repack APK
        |
        v
Sign با Signing Key رسمی
        |
        v
Update روی گوشی
```

---

## معماری برنامه

### WebView Layer

مسئول:

- رابط کاربری
- HTML
- JavaScript
- تولید خروجی‌ها
- Canvas Rendering
- منطق اطلاعیه مشتری
- قالب‌های نمایشی

### Native Wrapper

مسئول:

- Android WebView Host
- JavaScript Bridge
- ذخیره فایل
- Share Intent
- ارتباط با سیستم عامل

---

## بخش بررسی‌شده: اطلاعیه مشتری

مسیر:

```
بیشتر
 ↓
رزرو کار
 ↓
اطلاعیه مشتری
```

### اصلاحات انجام‌شده

- هدر اطلاعیه اصلاح شد
- متن اطلاعیه اصلاح شد
- Date Picker داخلی استفاده شد
- امضای مجری اصلاح شد

### مشکلات باقی‌مانده مورد بررسی

مسیر ذخیره تصویر:

```
JavaScript
 ↓
Canvas Rendering
 ↓
Image Generation
 ↓
File Creation
 ↓
Android Bridge
 ↓
Storage
```

موارد بررسی:

- Canvas
- Blob
- Base64
- File URI
- Content URI
- Storage Permission
- محدودیت‌های WebView

---

## قوانین پروژه

تغییر ممنوع:

- سیستم فاکتور
- حسابداری
- اطلاعات مشتری
- Database
- Backup
- Restore
- Schema
- Certificate
- Package Identity

نسخه‌های Final Locked باید immutable باقی بمانند.

---

## وضعیت فعلی

انجام‌شده:

- تحلیل معماری APK
- شناسایی ساختار WebView + Native Wrapper
- تعیین مسیر اصلاح
- مستندسازی مشکلات ذخیره و Share

در انتظار:

- Build واقعی Candidate
- Verify Signature
- تست نصب Update روی دستگاه

---

## هدف نهایی

ساخت یک نسخه Candidate واقعی از CiPi Pro که:

- قابل نصب باشد
- با نسخه قبلی Update شود
- اطلاعات کاربر را حفظ کند
- فقط مشکلات مشخص‌شده را اصلاح کند
