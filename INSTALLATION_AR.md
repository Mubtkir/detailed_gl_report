# دليل التنصيب السريع
# Quick Installation Guide

## 📦 للتنصيب على سيرفر عادي | For Regular Server

```bash
# 1. احصل على التطبيق | Get the app
cd frappe-bench
bench get-app https://github.com/yourusername/detailed_gl_report

# 2. نصّب على الموقع | Install on site
bench --site your-site-name install-app detailed_gl_report

# 3. هاجر قاعدة البيانات | Migrate database
bench --site your-site-name migrate

# 4. امسح الذاكرة المؤقتة وأعد التشغيل | Clear cache and restart
bench clear-cache
bench restart
```

## ☁️ للتنصيب على Frappe Cloud

1. افتح لوحة التحكم Frappe Cloud Dashboard
2. اذهب إلى قسم **Apps**
3. اضغط **Install App**
4. أدخل رابط GitHub:
   ```
   https://github.com/yourusername/detailed_gl_report
   ```
5. اضغط **Install**
6. انتظر حتى يكتمل التنصيب (عادة 2-5 دقائق)

## ✅ التحقق من التنصيب | Verify Installation

بعد التنصيب:
1. افتح ERPNext
2. ابحث عن: **Detailed General Ledger**
3. إذا ظهر التقرير، التنصيب نجح! ✅

## 🔍 استخدام التقرير | Using the Report

### مثال سريع | Quick Example

لعرض سند رقم DU-PA-B-2026-00500 بالتفصيل:

```
الفلاتر | Filters:
- Company: اختر شركتك
- From Date: 2026-03-01
- To Date: 2026-03-31
- Voucher No: DU-PA-B-2026-00500
```

اضغط **Refresh** وسترى جميع الأسطر مفصلة! 🎉

## 🆘 حل المشاكل | Troubleshooting

### المشكلة: التقرير لا يظهر
**الحل:**
```bash
bench --site your-site-name migrate
bench clear-cache
bench restart
```

### المشكلة: خطأ في الأذونات
**الحل:**
تأكد من أن دورك (Role) لديه صلاحية الوصول للتقارير المحاسبية:
- Accounts User
- Accounts Manager
- Auditor

## 📝 ملاحظات مهمة | Important Notes

1. **التوافق | Compatibility**: 
   - يعمل مع Frappe >= 15.0.0
   - متوافق مع ERPNext
   - متوافق مع تطبيق Voucher Management

2. **الأداء | Performance**:
   - للبيانات الكبيرة (أكثر من 10,000 سطر)، استخدم فلاتر أكثر تحديداً
   - يُنصح باختيار حساب محدد أو فترة زمنية قصيرة

3. **الحقول المخصصة | Custom Fields**:
   - يكتشف التقرير جميع الحقول المخصصة تلقائياً
   - لا حاجة لتعديل الكود!

## 🎯 الخلاصة | Summary

**قبل:**
- السند DU-PA-B-2026-00500 (7 أسطر) → يظهر سطر واحد فقط ❌

**بعد:**
- السند DU-PA-B-2026-00500 (7 أسطر) → يظهر 7 أسطر مفصلة ✅

---

**جاهز للاستخدام! | Ready to use!** 🚀
