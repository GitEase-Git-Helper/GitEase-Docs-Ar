# توثيق أوامر Git لرفع المشاريع على GitHub

هذا الملف يشرح الأوامر الأساسية للتعامل مع **Git** ورفع المشاريع على **GitHub**، مع الشرح بالعربي من اليمين لليسار، بحيث يسهل على أي مطور سواء مبتدئ أو محترف استخدامه مباشرة بدون الحاجة لحفظ الأوامر.

---

## رفع مشروع جديد لأول مرة

```bash
git init
git add .
git status
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/username/repository-name.git
git push -u origin main
```

**الشرح:**
- `git init` → تهيئة مجلد المشروع ليكون مشروع Git.
- `git add .` → إضافة جميع الملفات للتجهيز لرفعها.
- `git status` → التحقق من حالة الملفات.
- `git commit -m "first commit"` → حفظ نسخة من الملفات مع رسالة توضح التغيير.
- `git branch -M main` → تحديد الفرع الأساسي باسم **main**.
- `git remote add origin <الرابط>` → ربط المشروع مع المستودع على GitHub.
- `git push -u origin main` → رفع الملفات لأول مرة إلى GitHub.

---

## تحديث مشروع موجود على جهازك

```bash
git status
git add .
git status
git commit -m "update project"
git push
```

**الشرح:**
- `git status` → مراجعة التغييرات في الملفات.
- `git add .` → إضافة كل الملفات المعدلة.
- `git commit -m "update project"` → حفظ التغييرات مع رسالة.
- `git push` → رفع التحديثات إلى GitHub.

---

## تحديث مشروع غير موجود على جهازك (Clone)

```bash
git clone https://github.com/username/repository-name.git
cd repository-name
```

**بعد التعديلات:**
```bash
git status
git add .
git commit -m "your commit message"
git push
```

**الشرح:**
- `git clone <الرابط>` → تنزيل المشروع من GitHub إلى جهازك.
- `cd repository-name` → الدخول إلى مجلد المشروع.
- `git status` → مراجعة الملفات المعدلة.
- `git add .` → تجهيز الملفات المعدلة.
- `git commit -m "رسالة"` → حفظ التغييرات.
- `git push` → رفع التغييرات إلى GitHub.

---

## إدارة الحسابات (ربط Git مع GitHub)

### 1. إضافة الحساب (اسم المستخدم + البريد)
```bash
git config --global user.name "YourGitHubUsername"
git config --global user.email "your-email@example.com"
```

### 2. التحقق من البيانات المدخلة
```bash
git config --global user.name
git config --global user.email
```

### 3. ربط GitHub مع جهازك باستخدام SSH (اختياري لكن مهم)

إنشاء مفتاح SSH جديد:
```bash
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```

تشغيل خدمة الـ SSH Agent:
```bash
eval "$(ssh-agent -s)"
```

إضافة المفتاح الجديد:
```bash
ssh-add ~/.ssh/id_rsa
```

نسخ المفتاح (لإضافته في GitHub → Settings → SSH Keys):
```bash
cat ~/.ssh/id_rsa.pub
```

### 4. التحقق من الاتصال مع GitHub
```bash
ssh -T git@github.com
```
إذا ظهرت رسالة: **Hi username! You've successfully authenticated** يبقى الاتصال شغال.

---

## الموقع المباشر

[اضغط هنا لعرض الأوامر مباشرة بدون شرح](https://git-ease-five.vercel.app/)
