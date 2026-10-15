# ORBIT — تقرير المشروع | Project Report

**تاريخ المراجعة / Review date:** 15 أكتوبر 2026 / October 15, 2026

## 🇪🇬 التقرير بالعربي

### ✨ فايدة الموقع

ORBIT مساحة بسيطة لترتيب المهام والمشروعات ومتابعة التقدم من لوحة واحدة. تقدر تشوف المطلوب النهارده، المواعيد القريبة، المهام المتأخرة، ونسبة إنجاز كل مشروع. عرض Kanban بيساعدك تنقل الشغل بين «للتنفيذ» و«قيد التنفيذ» و«مكتمل».

### 🧭 أستخدمه إزاي؟

1. **ابدأ من Overview:** راجع ملخص يومك والمواعيد وتقدم المشروعات.
2. **اعمل مشروع:** من زر **Add project**، اكتب الاسم، الوصف، اللون، والموعد الاختياري.
3. **ضيف مهمة:** استخدم **New task** أو **Add task**. اكتب العنوان وحدد الحالة والأولوية والتاريخ والمشروع والوسوم لو محتاج.
4. **تابع الشغل:** من **My Tasks** ابحث، فلتر بالحالة أو المشروع، ورتب بالتاريخ أو الأولوية. اضغط مربع الإنجاز لإكمال المهمة.
5. **استخدم لوحة المشروع:** افتح مشروعًا ثم **Board view**. اسحب بطاقة المهمة من المقبض إلى العمود المناسب؛ ومن **Add task** داخل عمود تقدر تضيف مهمة بنفس الحالة.
6. **ابحث بسرعة:** `Ctrl+K` على ويندوز/لينكس أو `⌘K` على ماك. افتح مهمة جديدة بـ `Ctrl+N` أو `⌘N`.
7. **ظبط إعداداتك:** من **Settings** غيّر الاسم، الوضع المضغوط، واللون. استخدم **Export JSON** لنسخة احتياطية.

### 🔐 الأمان والخصوصية

- الموقع ثابت ويعمل داخل المتصفح، ولا يوجد تسجيل دخول أو خادم أو مزامنة. بيانات كل مستخدم تظل في مساحة التخزين المحلية لمتصفحه.
- أضفت ترويسات أمنية لـ Vercel وNetlify: سياسة CSP، منع تضمين الموقع داخل iframe، منع تخمين نوع الملفات، وتقييد صلاحيات الكاميرا والميكروفون والموقع الجغرافي.
- أزلت تحميل الخطوط من خدمة خارجية. لا تفتح منفذًا على جهازك لتشغيل الموقع للعامة؛ انشر `dist/` على استضافة HTTPS، واترك جدار الحماية/WAF عند مزود الاستضافة.
- هذه مراجعة تطبيق وتهيئة نشر، وليست شهادة اختراق أو ضمانًا أمنيًا مطلقًا. لا توجد حماية حسابات أو نسخ سحابي لأن التطبيق لا يملك خادمًا.

### ✅ الفحوص التي تمت

- `npm install`: اكتمل.
- `npm audit`: لا توجد ثغرات معروفة في التبعيات وقت الفحص.
- `npm run build`: نجح؛ تم تقسيم ملفات JavaScript لتقليل حجم كل جزء.
- تم التحقق من ملفات إعدادات Vercel وNetlify ومن نسخ ترويسات الحماية إلى `dist/`.
- نسخة الإنتاج التجريبية أعادت HTTP 200 للصفحة ولكل ملفات JavaScript/CSS السبعة المشار إليها.
- تم تشغيل Vite والتحقق من استجابة الصفحة وملف التطبيق محليًا في المراجعة السابقة.
- فحص المتصفح التفاعلي الشامل وواجهات الموبايل لم يكتمل؛ تشغيل Edge headless فشل داخل بيئة التنفيذ بسبب قيود GPU/النظام. يلزم تجربة النشر الفعلي على الأجهزة والمتصفحات المستهدفة قبل الإعلان عن خلوه تمامًا من الأخطاء.
- لم يتم نشر الموقع للعامة ولم يتم تعديل جدار حماية الجهاز. تحتاج النشرة العامة إلى اختيار/ربط حساب استضافة ودومين.

## 🇬🇧 English report

### ✨ What ORBIT is for

ORBIT is a focused place to organize projects, track tasks, and see progress at a glance. The dashboard surfaces today's work, upcoming deadlines, overdue tasks, completion totals, weekly activity, and project progress. A Kanban board helps move tasks through To Do, In Progress, and Done.

Vercel Web Analytics is mounted for page-view measurement after Analytics is enabled in the Vercel project dashboard and the app is deployed there.

New workspaces start empty instead of showing sample tasks or projects. On the first visit, an animated Arabic/English welcome guide explains the benefits and the steps to create a project, add tasks, and track progress. يبدأ ORBIT بمساحة فاضية، وبتظهر للمستخدم أول مرة نافذة متحركة بالعربي والإنجليزي تشرح الفايدة وطريقة الاستخدام.

### 🧭 How to use it

1. **Start at Overview** to review today's focus, deadlines, and project progress.
2. **Create a project** with **Add project**. Enter a name and optionally add a description, color, and target date.
3. **Create tasks** with **New task** or **Add task**. Set status, priority, due date, project, and optional tags.
4. **Manage work** in **My Tasks**. Search, filter by status or project, sort by due date or priority, and use the checkbox to complete a task.
5. **Use the project board** by opening a project and selecting **Board view**. Drag a card by its handle to change status. The Add task action in a column starts a task in that status.
6. **Search quickly:** `Ctrl+K` / `⌘K`. Open task creation with `Ctrl+N` / `⌘N`.
7. **Personalize and back up** in **Settings**. Change the display name, compact mode, or accent; use **Export JSON** to download a backup.

### 🔐 Security and privacy

ORBIT is a static frontend with no authentication, backend, sync, or collaboration. Each visitor's workspace stays in that browser's local storage. Vercel and Netlify configurations add a Content Security Policy, anti-framing, MIME sniffing protection, referrer policy, and restricted browser permissions. There is no inbound service port to open on your computer; use the hosting provider's HTTPS, edge firewall, and WAF controls.

### ✅ Verification status

Dependencies installed; `npm audit` reported zero known dependency vulnerabilities; and `npm run build` passed with code split into smaller files. Vercel/Netlify header files were validated, and the production preview returned HTTP 200 for its HTML and all seven referenced JS/CSS assets. iPhone safe areas, touch target rules, Safari input sizing, and reduced-motion styles are present; the updated app entry and mobile stylesheet returned HTTP 200 from Vite. Full interactive browser and real-device viewport testing could not be completed because Edge headless failed under this execution environment's GPU/system restrictions. No public deployment or host firewall change was made. Treat this as a deployment-ready static build, not a guarantee of zero defects or a formal penetration test.
