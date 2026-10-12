# g2action: Codespace Proxy Launcher via GitHub Actions

اجرای پروکسی V2Ray/Xray روی GitHub Codespaces بدون نیاز به باز کردن مرورگر، با کنترل کامل از طریق GitHub Actions و دریافت کانفیگ در لاگ.

## مزیت نسبت به اجرای مستقیم Codespaces
در زمان کندی یا قطعی اینترنت، نیازی به لود کردن محیط سنگین وب‌سایت Codespaces نیست؛ کاربر تنها دکمه Run workflow را می‌زند و لینک اتصال را از لاگ اکشن دریافت می‌کند.

## مراحل راه‌اندازی

1. **ساخت Personal Access Token (PAT):**
   - به مسیر `GitHub Settings -> Developer Settings -> Personal access tokens (classic)` بروید.
   - یک توکن با دسترسی‌های `codespace` و `repo` ایجاد کنید.
2. **ثبت سکرت در ریپازیتوری:**
   - در ریپازیتوری به `Settings -> Secrets and variables -> Actions` بروید.
   - یک سکرت با نام `GH_PAT` ایجاد کرده و مقدار توکن را در آن قرار دهید.
3. **اجرا:**
   - به تب **Actions** بروید و گردش‌کار **Codespace Proxy Launcher** را انتخاب کنید.
   - روی **Run workflow** کلیک کنید (`action: start`).
   - پس از اتمام مرحله، کانفیگ‌های `VLESS + WS + TLS` و `VLESS + XHTTP + TLS` در لاگ نمایش داده می‌شوند.

## مدیریت وضعیت
از همان منوی Run workflow می‌توانید متغیر `action` را روی `stop` (توقف موقت) یا `delete` (حذف کامل) تنظیم کنید تا سهمیه مصرفی رایگان ذخیره شود.
