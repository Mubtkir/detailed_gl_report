# Detailed GL Report | تقرير دفتر الأستاذ المفصل

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Frappe](https://img.shields.io/badge/Frappe-v15-blue)](https://frappeframework.com)
[![ERPNext](https://img.shields.io/badge/ERPNext-Compatible-green)](https://erpnext.com)

A comprehensive, line-by-line General Ledger report for ERPNext/Frappe that displays every transaction detail instead of aggregated totals.

تقرير شامل لدفتر الأستاذ يعرض كل سطر من GL Entry بشكل منفصل (سطر بسطر) بدلاً من الإجمالي.

---

## 🎯 Key Features | الميزات الرئيسية

### English
✅ **Line-by-Line Display**: Shows every GL Entry line separately instead of aggregated totals  
✅ **Comprehensive Filters**: All standard filters (Date, Account, Voucher, Party, etc.)  
✅ **Running Balance**: Automatic cumulative balance calculation  
✅ **Accounting Dimensions**: Full support for custom accounting dimensions  
✅ **Custom Fields**: Automatically detects and includes all custom fields  
✅ **Color Coding**: Visual differentiation of debits, credits, and balances  
✅ **Multi-Voucher Support**: Works with Journal Entry, Sales Invoice, Purchase Invoice, Payment Entry, Vouchers Entry, Stock Entry, and more

### العربية
✅ **عرض سطر بسطر**: يُظهر كل سطر من GL Entry بشكل منفصل  
✅ **فلاتر شاملة**: جميع الفلاتر القياسية (التاريخ، الحساب، نوع القيد، الطرف، إلخ)  
✅ **الرصيد التراكمي**: حساب الرصيد التراكمي تلقائياً  
✅ **الأبعاد المحاسبية**: دعم كامل للأبعاد المحاسبية المخصصة  
✅ **الحقول المخصصة**: يكتشف ويضيف جميع الحقول المخصصة تلقائياً  
✅ **التلوين البصري**: تمييز بصري للمدين والدائن والأرصدة  
✅ **دعم متعدد للسندات**: يعمل مع القيود اليومية، فواتير المبيعات، فواتير المشتريات، سندات الدفع، السندات المخصصة، قيود المخزون، وأكثر

---

## 🚀 Installation | التنصيب

### Option 1: From GitHub (Recommended)

```bash
# Get the app from GitHub
bench get-app https://github.com/yourusername/detailed_gl_report

# Install on your site
bench --site your-site-name install-app detailed_gl_report

# Migrate
bench --site your-site-name migrate

# Clear cache and restart
bench clear-cache
bench restart
```

### Option 2: For Frappe Cloud

1. Go to your Frappe Cloud dashboard
2. Navigate to **Apps** section
3. Click **Install App**
4. Enter the GitHub URL: `https://github.com/yourusername/detailed_gl_report`
5. Click **Install**

---

## 📊 Usage | الاستخدام

### Accessing the Report | الوصول للتقرير

**English:**
1. Navigate to: **Accounting > Reports > Detailed General Ledger**
2. Or search for: "Detailed General Ledger" in the search bar
3. Select required filters
4. Click **Refresh**

**العربية:**
1. اذهب إلى: **المحاسبة > التقارير > Detailed General Ledger**
2. أو ابحث عن: "Detailed General Ledger" في شريط البحث
3. اختر الفلاتر المطلوبة
4. اضغط **تحديث**

### Available Filters | الفلاتر المتاحة

**Required | إلزامية:**
- Company | الشركة
- From Date | من تاريخ
- To Date | إلى تاريخ

**Optional | اختيارية:**
- Account | الحساب
- Voucher Type | نوع القيد
- Voucher No | رقم القيد
- Party Type | نوع الطرف
- Party Name | اسم الطرف
- Cost Center | مركز التكلفة
- Project | المشروع
- Note/Remarks | الملاحظات
- User Name | المستخدم
- **+ All Accounting Dimensions** | **+ جميع الأبعاد المحاسبية**
- **+ All Custom Fields** | **+ جميع الحقول المخصصة**

---

## 💡 Examples | أمثلة

### Example 1: View All Lines of a Specific Voucher
### مثال 1: عرض جميع أسطر سند محدد

```
Filters:
- Voucher Type: "Vouchers Entry"
- Voucher No: "DU-PA-B-2026-00500"

Result: All 7 lines of the voucher displayed separately
النتيجة: جميع الأسطر السبعة للسند معروضة بشكل منفصل
```

### Example 2: Account Transactions from Vouchers Entry Only
### مثال 2: حركات حساب معين من السندات المخصصة فقط

```
Filters:
- Account: "Cash - Company"
- Voucher Type: "Vouchers Entry"
- From/To Date: Current Month

Result: All Cash transactions from custom vouchers only
النتيجة: جميع حركات النقدية من السندات المخصصة فقط
```

### Example 3: Customer Receipts Details
### مثال 3: تفاصيل قبوضات عميل

```
Filters:
- Voucher Type: "Vouchers Entry"
- Party Type: "Customer"
- Party: "Customer Name"
- From/To Date: Current Year

Result: All customer receipts with full line details
النتيجة: جميع قبوضات العميل مع التفاصيل الكاملة
```

---

## 🎨 Visual Features | الميزات البصرية

**Color Coding | التلوين:**
- 🟢 **Debit | المدين**: Green | أخضر
- 🔵 **Credit | الدائن**: Blue | أزرق
- 🔴 **Negative Balance | الرصيد السالب**: Red | أحمر
- 🟠 **Vouchers Entry**: Orange (for distinction) | برتقالي (للتمييز)

---

## 🔧 Technical Details | التفاصيل التقنية

### Supported Voucher Types | أنواع السندات المدعومة

- Journal Entry | القيد اليومي
- Sales Invoice | فاتورة مبيعات
- Purchase Invoice | فاتورة شراء
- Payment Entry | سند دفع
- **Vouchers Entry** | **السندات المخصصة** (من تطبيق voucher_management)
- Delivery Note | إذن تسليم
- Purchase Receipt | إذن استلام
- Stock Entry | قيد مخزون
- Expense Claim | مطالبة مصروفات
- Asset | أصل
- Loan Disbursement | صرف قرض
- Loan Repayment | سداد قرض

### Database Query | استعلام قاعدة البيانات

The report fetches data directly from `tabGL Entry` with:
- Individual line selection (not aggregated)
- Running balance calculation
- Support for all custom fields and dimensions

التقرير يجلب البيانات مباشرة من `tabGL Entry` مع:
- اختيار كل سطر بشكل منفصل (غير مجمع)
- حساب الرصيد التراكمي
- دعم جميع الحقول والأبعاد المخصصة

---

## 📝 Comparison | المقارنة

| Feature | Standard GL Report | This Report (Detailed GL) |
|---------|-------------------|--------------------------|
| **Display** | Aggregated totals | Line-by-line |
| **Vouchers Entry (7 lines)** | 1 line (total) | 7 lines (detailed) |
| **Custom Fields** | Limited | Full automatic support |
| **Accounting Dimensions** | Limited | Full automatic support |
| **Running Balance** | Yes | Yes |
| **Visual Colors** | Basic | Enhanced |

| الميزة | التقرير القياسي | هذا التقرير (المفصل) |
|---------|-----------------|---------------------|
| **العرض** | إجمالي | سطر بسطر |
| **سند من 7 أسطر** | سطر واحد (إجمالي) | 7 أسطر (مفصل) |
| **الحقول المخصصة** | محدود | دعم تلقائي كامل |
| **الأبعاد المحاسبية** | محدود | دعم تلقائي كامل |
| **الرصيد التراكمي** | نعم | نعم |
| **التلوين البصري** | أساسي | محسّن |

---

## ⚙️ Requirements | المتطلبات

- Frappe Framework >= 15.0.0
- ERPNext (recommended but not required)
- Python 3.10+

---

## 🤝 Contributing | المساهمة

Contributions are welcome! Please feel free to submit a Pull Request.

المساهمات مرحب بها! لا تتردد في تقديم Pull Request.

---

## 📄 License

MIT License - see LICENSE file for details

---

## 🐛 Bug Reports | الإبلاغ عن الأخطاء

If you encounter any issues, please report them on GitHub Issues.

إذا واجهت أي مشاكل، يرجى الإبلاغ عنها في GitHub Issues.

---

## 📞 Support | الدعم

For support, please:
1. Check the documentation above
2. Search existing GitHub Issues
3. Create a new issue if needed

للدعم، يرجى:
1. مراجعة الوثائق أعلاه
2. البحث في GitHub Issues الموجودة
3. إنشاء issue جديد إذا لزم الأمر

---

## 🌟 Credits | الشكر

Developed by Amir for the Frappe/ERPNext community.

تم تطويره بواسطة عامر لمجتمع Frappe/ERPNext.

---

**Made with ❤️ for the Frappe Community**
