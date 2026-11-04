# **مرجع العمل وقواعد المساهمة \- Smart Local Services Platform**

---

**اسم المشروع:** منصة الخدمات المحلية الذكية (Smart Local Services Platform)

**الهدف:** دليل فريق العمل الشامل لتنظيم الإدارة، السيناريو العملي للتاسكات، هيكل الكود، سياسة الفروع، وقواعد تسليم المهام.

## **أولاً: سيناريو تنفيذ التاسك خطوة بخطوة (Task Execution Scenario)**

1. ---

   **الخطوة 1: استلام التاسك على الـ Project Board**  
   * **اللي بيحصل:** أنت بتنقل التاسك من قائمة Backlog لـ Ready (يعني جاهزة للتنفيذ لأنها مكتوبة صح ولها تفاصيل واضحة).  
   * **دور العضو:** بيدخل يقرأ تفاصيل التاسك (Description والـ Acceptance Criteria) عشان يفهم مطلوب منه إيه بالظبط من غير ما يسألك كل شوية.  
2. **الخطوة 2: فتح فرع خاص بالتاسك على جيت هب (Feature Branch)**  
   * **اللي بيحصل:** المطور بيفتح الـ Terminal على جهازه ويجيب آخر تحديثات من فرع الـ develop، وبعدين يعمل لنفسه فرع جديد فرعي بيسميه باسم التاسك عشان يشتغل براحته من غير ما يبوظ شغل غيره.  
   * **الأوامر اللي بيكتبها:**  
     git checkout develop  
     git pull  
     git checkout \-b feature/BE-034-create-request  
   * *(كده هو بقى واقف على فرع جديد خاص بيه هو لوحده ومستقل تماماً).*  
3. **الخطوة 3: كتابة الكود والـ Commits المحلية**  
   * **اللي بيحصل:** العضو بيفتح Visual Studio ويبدأ يكتب الكود بتاع الـ API والـ Validation ويجرب. وكل ما يخلص جزء صغير ويعمل Save، بيسجله عنده بـ Commit منظم وواضح.  
   * **مثال للي بيكتبه:**  
     git add .  
     git commit \-m "feat(BE-034): implement service request creation endpoint"  
   * *(زي ما اتفقنا، الكلمة بدأت بـ feat وراها رقم التاسك ورسالة واضحة).*  
4. **الخطوة 4: رفع الفرع أونلاين على جيت هب (Push)**  
   * **اللي بيحصل:** بعد ما خلص الكود واختبره عنده وتأكد إنه شغّال، بيبعت الفرع ده أونلاين على جيت هب عشان التيم كله يشوفه.  
   * **الأمر اللي بيكتبه:**  
     git push origin feature/BE-034-create-request  
5. **الخطوة 5: فتح طلب دمج (Pull Request \- PR)**  
   * **اللي بيحصل:** العضو يدخل على موقع GitHub، هيلاقي زرار ظهر لوحده بيقوله (Compare & pull request). بيضغط عليه.  
   * **بيملى النموذج (Template) اللي اتفقنا عليه:**  
     * بيحط رقم التاسك: BE-034  
     * بيكتب هو عمل إيه في الـ Description.  
     * بيحط صور أو سكرين شوت (من Postman مثلاً) بتثبت إن الـ API شغّال و بيراسِل 200 OK.  
     * بيضغط Create Pull Request.  
6. **الخطوة 6: المراجعة (Code Review)**  
   * **اللي بيحصل:** هنا بيجي دورك أنت (أو شخص تاني في التيم) كـ Reviewer.  
     * بتدخل تفتح الـ Pull Request ده.  
     * بتبص على الكود سريعاً، وتتأكد إنه ماشي مع الـ Clean Architecture ومنظم.  
     * لو فيه ملحوظة بتكتبها له (مثلاً: "يا فلان عدل الحتة دي أو ضيف Validation هنا").  
     * لو كله تمام وصح، بتعمل Approve (موافقة).  
7. **الخطوة 7: الدمج النهائي على الـ develop (Merge)**  
   * **اللي بيحصل:** بعد الموافقة، بتضغط على زرار Merge Pull Request على جيت هب.  
   * الكود بتاعه بيتحط جوه فرع الـ develop الرئيسي، وكده التاسك دي بقت جزء من السيستم المتكامل\!  
   * في الآخر، بيعملوا ديليت للفرع القديم feature/BE-034 عشان ينظفوا الـ Repository.  
   * التاسك بتتحرك على الـ Board من In Review لـ Done.

## **ثانياً: مرجع العمل وقواعد المساهمة الشاملة**

### ---

**1\. هيكل النظام المعماري (System Architecture)**

احنا شغالين بـ **Clean Architecture** في الـ Backend (.NET 10\) عشان ننظم الكود في طبقات منفصلة وتسهل شغل التيم من غير تداخل:

* **Domain:** قاعدة البيانات والمودلز الأساسية (Entities).  
* **Application:** منطق الشغل وقواعد العمل (Use Cases).  
* **Infrastructure:** الاتصال بقاعدة البيانات (SQL Server / Entity Framework) والخدمات الخارجية.  
* **API:** الـ Controllers والـ Endpoints اللي بيكلمها تطبيق الموبايل (React Native).

### **2\. سياسة الفروع على جيت هب (Branching Strategy)**

* main: الفرع الرئيسي والمقدس للنسخ المستقرة للمناقشة فقط. **ممنوع الكتابة عليه مباشرة.**  
* develop: فرع التجميع والتطوير المستمر لتكامل شغل الفرق.  
* **Feature Branches:** لما تاخد تاسك جديدة، افتح فرع فرعي من الـ develop بالتسمية دي:  
  * لميزات الجديدة: feature/TaskID-short-description (مثال: feature/BE-034-create-request)  
  * لتصحيح الأخطاء: fix/TaskID-short-description (مثال: fix/BE-037-cancel-request)  
  * للتوثيق: docs/topic-name

### **3\. قواعد كتابة الـ Commit Messages**

ممنوع كتابة رسائل عشوائية. التزم بالصيغة القياسية التالية:

type(Task-ID): short description in English

**أنواع الـ Types المعتمدة:**

* feat: إضافة ميزة جديدة (مثال: feat(BE-034): implement service request creation)  
* fix: تصحيح خطأ أو Bug (مثال: fix(BE-037): correct request status validation)  
* test: إضافة اختبارات (مثال: test: add request creation tests)  
* docs: تعديل في ملفات التوثيق (مثال: docs: update API contracts)

### **4\. نموذج تسليم المهام (Pull Request Template)**

لما تخلص التاسك وترفع فرعك على GitHub، املأ النموذج ده في الـ Pull Request:

\#\# Related Task  
\[اكتب رقم التاسك هنا، مثال: BE-034\]

\#\# Description  
\[اكتب باختصار إنت عملت إيه في التاسك دي\]

\#\# Changes  
\- \[تعديل 1، مثلاً: Added request creation endpoint\]  
\- \[تعديل 2، مثلاً: Added data validation\]

\#\# Testing  
\- \[اختبار 1، مثلاً: Tested valid request \-\> Success 200 OK\]  
\- \[اختبار 2، مثلاً: Tested invalid input \-\> Returns 400\]

\#\# Screenshots / Evidence  
\[حط هنا صورة أو سكرين شوت من Postman أو الواجهة بتثبت إن الشغل شغال\]

\#\# Checklist  
\- \[ \] Code builds successfully  
\- \[ \] Tests pass  
\- \[ \] Documentation updated  
\- \[ \] Related issue linked


### **5\. القواعد الذهبية للتيم كله**

1. **No Task Without an Owner:** مفيش تاسك تتفذ من غير ما يكون محدد مين المسؤول عنها.  
2. **No Code on Main:** ممنوع تماماً رفع كود مباشرة على فرع الـ main.  
3. **Always Branch from Develop:** ابدأ شغلك وافتح فروعك الجديدة دايماً من الـ develop.  
4. **Review Before Merge:** أي كود لازم يعدي على مراجعة (Code Review) من زميلك قبل ما يتدمج في الـ develop.
