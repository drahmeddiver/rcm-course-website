# دليل تعديل موقع دورات إدارة دورة الإيرادات في الرعاية الصحية السعودية
# RCM Course Website Modification Guide

## نظرة عامة / Overview

هذا الموقع يعرض دورات إدارة دورة الإيرادات (RCM) في الرعاية الصحية السعودية بمستويين (مبتدئ ومتقدم) باللغتين العربية والإنجليزية.

This website displays Revenue Cycle Management (RCM) courses for Saudi healthcare in two levels (beginner and advanced) in both Arabic and English.

## هيكل المشروع / Project Structure

```
rcm_course_website/
├── src/
│   └── static/
│       └── index.html          # الملف الرئيسي للموقع / Main website file
├── simple_server.py            # خادم Flask البسيط / Simple Flask server
├── requirements.txt            # متطلبات Python / Python requirements
└── README.md                   # هذا الملف / This file
```

## كيفية تشغيل الموقع / How to Run the Website

### 1. تشغيل الخادم المحلي / Running Local Server

```bash
cd rcm_course_website
source venv/bin/activate
python simple_server.py
```

الموقع سيكون متاحاً على: http://localhost:5001
The website will be available at: http://localhost:5001

### 2. إيقاف الخادم / Stopping the Server

اضغط `Ctrl+C` في الطرفية لإيقاف الخادم
Press `Ctrl+C` in the terminal to stop the server

## كيفية تعديل المحتوى / How to Modify Content

### تعديل النصوص / Editing Text Content

جميع محتوى الموقع موجود في ملف واحد: `src/static/index.html`
All website content is in one file: `src/static/index.html`

#### لتعديل المحتوى العربي / To Edit Arabic Content:

ابحث عن القسم:
```html
<div id="arabic-content">
```

#### لتعديل المحتوى الإنجليزي / To Edit English Content:

ابحث عن القسم:
```html
<div id="english-content" class="hidden en">
```

### أمثلة على التعديلات الشائعة / Common Modification Examples

#### 1. تغيير عنوان الدورة / Changing Course Title

**العربي / Arabic:**
```html
<h2 class="course-title">المستوى الأول: المبتدئ</h2>
```

**الإنجليزي / English:**
```html
<h2 class="course-title">Level 1: Beginner</h2>
```

#### 2. إضافة جلسة جديدة / Adding a New Session

**العربي / Arabic:**
```html
<div class="session">
    <div class="session-title">الجلسة الجديدة: عنوان الجلسة</div>
    <div class="session-content">
        <ul>
            <li>النقطة الأولى</li>
            <li>النقطة الثانية</li>
            <li>النقطة الثالثة</li>
        </ul>
    </div>
</div>
```

**الإنجليزي / English:**
```html
<div class="session">
    <div class="session-title">New Session: Session Title</div>
    <div class="session-content">
        <ul>
            <li>First point</li>
            <li>Second point</li>
            <li>Third point</li>
        </ul>
    </div>
</div>
```

#### 3. تعديل المدة الزمنية / Changing Duration

**العربي / Arabic:**
```html
<div class="duration-badge">المدة الإجمالية: 9 جلسات، 27 ساعة</div>
```

**الإنجليزي / English:**
```html
<div class="duration-badge">Total Duration: 9 sessions, 27 hours</div>
```

#### 4. إضافة وحدة جديدة / Adding a New Module

```html
<div class="module">
    <h3 class="module-title">الوحدة الجديدة: اسم الوحدة (عدد الجلسات، المدة)</h3>
    
    <div class="session">
        <div class="session-title">الجلسة 1: عنوان الجلسة</div>
        <div class="session-content">
            <ul>
                <li>محتوى الجلسة</li>
            </ul>
        </div>
    </div>
</div>
```

### تعديل التصميم / Modifying Design

#### تغيير الألوان / Changing Colors

ابحث عن قسم `<style>` في بداية الملف وعدّل المتغيرات التالية:
Look for the `<style>` section at the beginning of the file and modify these variables:

```css
.header {
    background: linear-gradient(135deg, #2c3e50, #3498db); /* لون الرأس / Header color */
}

.course-title {
    color: #2c3e50; /* لون عناوين الدورات / Course title color */
    border-bottom: 3px solid #3498db; /* لون الخط السفلي / Underline color */
}

.module {
    border-left: 4px solid #3498db; /* لون حدود الوحدات / Module border color */
}
```

#### تغيير الخطوط / Changing Fonts

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* نوع الخط / Font family */
}
```

### إضافة محتوى جديد / Adding New Content

#### إضافة مستوى ثالث / Adding a Third Level

1. انسخ هيكل إحدى البطاقات الموجودة (Level 1 أو Level 2)
   Copy the structure of one of the existing cards (Level 1 or Level 2)

2. غيّر العناوين والمحتوى
   Change the titles and content

3. أضف البطاقة الجديدة داخل `<div class="course-grid">`
   Add the new card inside `<div class="course-grid">`

#### إضافة صفحة جديدة / Adding a New Page

1. أنشئ ملف HTML جديد في مجلد `src/static/`
   Create a new HTML file in the `src/static/` folder

2. أضف رابط للصفحة الجديدة في `index.html`
   Add a link to the new page in `index.html`

```html
<a href="new-page.html">الصفحة الجديدة / New Page</a>
```

## نصائح مهمة / Important Tips

### 1. النسخ الاحتياطي / Backup

قم بعمل نسخة احتياطية من `index.html` قبل التعديل:
Make a backup of `index.html` before editing:

```bash
cp src/static/index.html src/static/index.html.backup
```

### 2. اختبار التغييرات / Testing Changes

بعد كل تعديل، احفظ الملف وأعد تحميل الصفحة في المتصفح لرؤية التغييرات.
After each modification, save the file and refresh the page in the browser to see changes.

### 3. التحقق من صحة HTML / HTML Validation

تأكد من أن جميع العلامات مغلقة بشكل صحيح:
Make sure all tags are properly closed:

- `<div>` يجب أن يُغلق بـ `</div>`
- `<ul>` يجب أن يُغلق بـ `</ul>`
- `<li>` يجب أن يُغلق بـ `</li>`

### 4. الحفاظ على التناسق / Maintaining Consistency

عند إضافة محتوى جديد، تأكد من:
When adding new content, make sure to:

- استخدام نفس هيكل HTML / Use the same HTML structure
- الحفاظ على نفس أسلوب التصميم / Maintain the same design style
- إضافة المحتوى باللغتين العربية والإنجليزية / Add content in both Arabic and English

## استكشاف الأخطاء / Troubleshooting

### المشكلة: الموقع لا يعمل / Problem: Website not working

**الحل / Solution:**
1. تأكد من تشغيل الخادم / Make sure the server is running
2. تحقق من المنفذ (Port) المستخدم / Check the port being used
3. تأكد من وجود ملف `index.html` / Ensure `index.html` exists

### المشكلة: التصميم مكسور / Problem: Design is broken

**الحل / Solution:**
1. تحقق من صحة HTML / Check HTML validity
2. تأكد من إغلاق جميع العلامات / Ensure all tags are closed
3. راجع قسم CSS / Review the CSS section

### المشكلة: تبديل اللغة لا يعمل / Problem: Language toggle not working

**الحل / Solution:**
1. تأكد من وجود JavaScript في نهاية الملف / Ensure JavaScript is at the end of the file
2. تحقق من console المتصفح للأخطاء / Check browser console for errors

## الدعم / Support

إذا واجهت أي مشاكل أو تحتاج مساعدة إضافية، يمكنك:
If you encounter any problems or need additional help, you can:

1. مراجعة هذا الدليل مرة أخرى / Review this guide again
2. البحث عن أمثلة HTML/CSS مشابهة عبر الإنترنت / Search for similar HTML/CSS examples online
3. استخدام أدوات تطوير المتصفح لفهم المشكلة / Use browser developer tools to understand the issue

---

**ملاحظة:** هذا الموقع مصمم ليكون بسيطاً وسهل التعديل. جميع المحتوى في ملف واحد لتسهيل الصيانة.

**Note:** This website is designed to be simple and easy to modify. All content is in one file for easy maintenance.

