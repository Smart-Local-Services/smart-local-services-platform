# Week 2 – System Analysis & Software Design

28-10-2026

دي تقسيمة مقترحة لتاسكات الأسبوع الثاني، مقسمة حسب مراحل التنفيذ والـDeliverables، بعيدًا عن عدد أفراد التيم.

## 1. System Analysis – تحليل النظام

- تحديد فكرة النظام والمشكلة التي يعالجها.
- تحديد نطاق النظام (System Scope).
- تحديد المتطلبات الوظيفية (Functional Requirements).
- تحديد المتطلبات غير الوظيفية (Non-Functional Requirements).
- تحديد المستخدمين والأطراف المتفاعلة مع النظام (Actors).
- تحديد الصلاحيات والمسؤوليات لكل Actor.
- تحديد السيناريوهات الأساسية لاستخدام النظام (Main Use Cases).

## 2. System Modeling – نمذجة النظام

- إعداد System Context Diagram.
- إعداد Use Case Diagram.
- إعداد DFD Level 0 (Context Level).
- إعداد DFD Level 1 للعمليات الرئيسية.
- تحديد العمليات الأساسية وتدفق البيانات بينها.
- توثيق وصف الـUse Cases (Use Case Specifications).

## 3. Software Architecture – تصميم معمارية النظام

- تحديد Software Architecture المناسبة للمشروع.
- تحديد مكونات النظام الرئيسية (System Components).
- تحديد مسؤوليات كل مكون.
- تحديد طريقة التواصل بين Mobile App وAdmin Dashboard والـBackend.
- تحديد تكامل Laravel مع Python AI Service.
- تحديد تكامل خدمات الخرائط والـReal-Time Communication.
- إعداد High-Level Architecture Diagram.

## 4. Database Design – تصميم قاعدة البيانات

- تحديد الكيانات الأساسية (Entities).
- تحديد خصائص كل Entity (Attributes).
- تحديد العلاقات بين الكيانات (Relationships).
- تحديد Primary Keys وForeign Keys.
- إعداد ERD – Entity Relationship Diagram.
- تحديد أنواع العلاقات (1:1, 1:M, M:N).
- مراجعة تصميم قاعدة البيانات والتأكد من عدم وجود تكرار غير ضروري.
- البدء في إنشاء Database Schema على SQL Server.

## 5. UML Diagrams – تصميم سلوك وهيكل النظام

Structural Design

- تحديد Classes الأساسية.
- تحديد Attributes وMethods لكل Class.
- تحديد العلاقات بين Classes.
- إعداد Class Diagram.

Behavioral Design

- إعداد Sequence Diagrams للعمليات الرئيسية.
- إعداد Activity Diagrams للـWorkflows الأساسية.
- مراجعة Use Case Diagram وربطه بالـActors والوظائف.

## 6. Documentation & Review – التوثيق والمراجعة

- تجميع الرسومات والـDiagrams في ملف واحد.
- توثيق القرارات المعمارية والتقنيات المستخدمة.
- مراجعة توافق الـERD مع الـClass Diagram.
- مراجعة توافق الـUse Cases مع الـSequence وActivity Diagrams.
- مراجعة التصميم مع متطلبات المشروع والـProposal.
- تحديد المهام التي سيتم تنفيذها في الأسبوع الثالث.

## الـExpected Deliverables بنهاية الأسبوع

| Deliverable           | Expected Output                                 |
| --------------------- | ----------------------------------------------- |
| System Analysis       | Requirements + Actors + Use Cases               |
| System Modeling       | Context Diagram + DFD                           |
| Software Architecture | Architecture Diagram                            |
| Database Design       | ERD + Initial Database                          |
| UML                   | Class + Sequence + Activity + Use Case Diagrams |
| Documentation         | System Design Documentation                     |

ترتيب الأولويات المقترح: ابدأوا بتحليل المتطلبات والـActors والـUse Cases، وبعدها Context Diagram وDFD، ثم Architecture وERD، وبعدها UML والبدء في إنشاء قاعدة البيانات.

ملحوظة: مش لازم كل الرسومات تكون نهائية في الأسبوع ده؛ المهم يكون عندكم تصميم أولي متكامل ومتوافق، وقاعدة بيانات أولية قابلة للمراجعة قبل بدء التنفيذ الفعلي.
