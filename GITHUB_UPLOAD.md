# كيفية رفع التطبيق على GitHub
# How to Upload the App to GitHub

## 📤 الخطوات | Steps

### 1️⃣ إنشاء Repository على GitHub

**English:**
1. Go to https://github.com
2. Click **"New"** or **"+"** → **"New repository"**
3. Enter repository details:
   - **Repository name**: `detailed_gl_report`
   - **Description**: "Detailed General Ledger Report for ERPNext - Line by Line Display"
   - **Visibility**: Public (recommended) or Private
   - **DO NOT** initialize with README (we already have one)
4. Click **"Create repository"**

**العربية:**
1. اذهب إلى https://github.com
2. اضغط **"New"** أو **"+"** → **"New repository"**
3. أدخل تفاصيل المستودع:
   - **Repository name**: `detailed_gl_report`
   - **Description**: "تقرير دفتر الأستاذ المفصل لـ ERPNext - عرض سطر بسطر"
   - **Visibility**: Public (موصى به) أو Private
   - **لا تقم** بتهيئة README (لدينا واحد بالفعل)
4. اضغط **"Create repository"**

---

### 2️⃣ رفع الملفات من السيرفر

**من مجلد التطبيق:**

```bash
# انتقل إلى مجلد التطبيق | Navigate to app folder
cd frappe-bench/apps/detailed_gl_report

# تهيئة Git | Initialize Git
git init

# إضافة جميع الملفات | Add all files
git add .

# عمل Commit | Make initial commit
git commit -m "Initial commit: Detailed General Ledger Report v1.0.0"

# إضافة Remote Repository | Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/detailed_gl_report.git

# رفع الملفات | Push files
git branch -M main
git push -u origin main
```

**استبدل YOUR_USERNAME باسم المستخدم الخاص بك على GitHub!**

---

### 3️⃣ التحقق من الرفع | Verify Upload

افتح الرابط:
```
https://github.com/YOUR_USERNAME/detailed_gl_report
```

يجب أن ترى:
- ✅ جميع الملفات
- ✅ ملف README.md معروض بشكل جميل
- ✅ وصف المشروع

---

### 4️⃣ التنصيب من GitHub

الآن يمكن لأي شخص تنصيب التطبيق:

```bash
# للتنصيب على سيرفر عادي | For regular server
bench get-app https://github.com/YOUR_USERNAME/detailed_gl_report
bench --site your-site install-app detailed_gl_report

# للتنصيب على Frappe Cloud | For Frappe Cloud
# استخدم الرابط مباشرة في لوحة التحكم
# Use the link directly in dashboard:
https://github.com/YOUR_USERNAME/detailed_gl_report
```

---

## 🔄 للتحديثات المستقبلية | For Future Updates

عند إجراء تعديلات:

```bash
# انتقل إلى المجلد | Navigate to folder
cd frappe-bench/apps/detailed_gl_report

# أضف التغييرات | Add changes
git add .

# عمل Commit | Make commit
git commit -m "Update: وصف التغيير"

# رفع التحديثات | Push updates
git push origin main
```

---

## 📋 Checklist قبل الرفع | Pre-upload Checklist

تأكد من:
- [ ] جميع الملفات موجودة
- [ ] ملف README.md محدث
- [ ] ملف LICENSE موجود
- [ ] ملف .gitignore موجود
- [ ] لا توجد معلومات حساسة (كلمات مرور، API keys، إلخ)
- [ ] تم اختبار التطبيق على موقع تجريبي

---

## 🎯 نصائح مهمة | Important Tips

### للمطورين | For Developers

1. **استخدم Branches للتطوير:**
   ```bash
   git checkout -b development
   # قم بالتعديلات
   git commit -m "Feature: ميزة جديدة"
   git push origin development
   ```

2. **استخدم Tags للإصدارات:**
   ```bash
   git tag -a v1.0.0 -m "Release version 1.0.0"
   git push origin v1.0.0
   ```

3. **اكتب Commit Messages واضحة:**
   - ✅ "Fix: حل مشكلة حساب الرصيد"
   - ✅ "Feature: إضافة فلتر جديد للمشروع"
   - ❌ "update"
   - ❌ "fix bug"

### للتوثيق | For Documentation

1. **حدّث CHANGELOG.md** مع كل إصدار جديد
2. **حدّث README.md** عند إضافة ميزات جديدة
3. **أضف screenshots** للميزات المهمة

---

## 🌐 جعل التطبيق عام | Making App Public

إذا كنت تريد مشاركة التطبيق مع المجتمع:

1. **أضف Topics على GitHub:**
   - frappe
   - erpnext
   - accounting
   - general-ledger
   - reporting

2. **شارك في المجتمع:**
   - Frappe Forum: https://discuss.frappe.io/
   - ERPNext Telegram Groups
   - LinkedIn

3. **أضف Badge للـ README:**
   ```markdown
   [![Frappe](https://img.shields.io/badge/Frappe-v15-blue)](https://frappeframework.com)
   ```

---

## 🆘 حل المشاكل | Troubleshooting

### المشكلة: git push يطلب Username & Password
**الحل:**
استخدم Personal Access Token بدلاً من كلمة المرور:
1. اذهب إلى GitHub Settings → Developer settings → Personal access tokens
2. أنشئ Token جديد
3. استخدمه بدلاً من كلمة المرور

### المشكلة: التطبيق لا يعمل بعد التنصيب من GitHub
**الحل:**
```bash
bench --site your-site migrate
bench clear-cache
bench restart
```

---

## ✅ اكتمل! | Done!

الآن التطبيق متاح على:
```
https://github.com/YOUR_USERNAME/detailed_gl_report
```

يمكن لأي شخص تنصيبه واستخدامه! 🎉

---

**Need help? | تحتاج مساعدة?**
- 📧 Email: amirmasni@gmail.com
- 💬 GitHub Issues: [Create an issue](https://github.com/YOUR_USERNAME/detailed_gl_report/issues)
