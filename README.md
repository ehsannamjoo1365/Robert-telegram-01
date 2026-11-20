# Robert Telegram Assistant

ربات مستقل پاسخ‌گویی اولیه و دریافت درخواست پشتیبانی.

## فرمان‌ها
- `/start` و `/help`: راهنما
- `/about`: معرفی و وضعیت قابلیت‌ها
- `/support متن`: ارسال متن درخواست به مالک ربات
- `/id`: شناسه گفتگو

نسخه فعلی پاسخ‌های فرمان‌محور دارد و هنوز به هوش مصنوعی یا CRM متصل نیست.

## تنظیمات مستقل
- `BOT_TOKEN`: توکن اختصاصی همین ربات
- `OWNER_ID`: شناسه عددی تلگرام مالک
- `BOT_USERNAME`: (اختیاری) نام کاربری بدون @ برای کنترل تطابق توکن

توکن را در کد، فایل README یا commit قرار نده. `.env.example` فقط نمونه نام متغیرهاست.

## اجرا
```bash
export BOT_TOKEN='توکن اختصاصی'
export OWNER_ID='شناسه عددی مالک'
python bot.py
```
یا با Docker:
```bash
docker build -t robert-telegram .
docker run -d --restart unless-stopped -e BOT_TOKEN -e OWNER_ID -e BOT_USERNAME robert-telegram
```

این ربات از long polling استفاده می‌کند و به پردازش Python دائمی نیاز دارد؛ GitHub Pages و هاست اشتراکی صرفاً PHP برای اجرای دائمی آن کافی نیستند. برای استقرار، VPS یا سرویس کانتینری لازم است.
