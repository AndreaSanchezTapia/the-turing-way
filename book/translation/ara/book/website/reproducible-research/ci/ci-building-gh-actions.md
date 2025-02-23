(إجراءات بناء ر.س.س.س.س.س.ر =
# بناء كتلة من إجراءات Github

كما هو مبين سابقاً، تستخدم ملفات سير العمل بناء YAML، الذي يحتوي إما على امتداد ملف `.yml` أو `.yaml`. إذا كنت جديداً على YAML وترغب في معرفة المزيد، {ref}`انظر القسم الخاص بنا حول YMAL<rr-renv-yaml>`. يجب تخزين ملفات سير العمل هذه في دليل `.github/workflow` للمستودع الخاص بك.

كل سير عمل محدد في YAML منفصل. سوف نقدم لبنة البناء لسير العمل باستخدام مثال مرحبا عالمي:

```
الاسم:
    مرحبا حزمة العالم
على:
  دفع:
    الفروع: [ الرئيس]
الوظائف:
  بناء:
    تشغيل: ubuntu-latest
    خطوات:
      - الاستخدامات: الإجراءات/checkout@v2
```

**1. اسم**

هذا هو اسم سير العمل وهو اختياري. سيستخدم GitHub هذا الاسم ليتم عرضه على صفحة إجراءات المستودع.
```
الاسم:
    مرحبا بالحزمة العالمية
```

**2. في**

الحقل `على` يخبر GHA متى يتم تشغيله. على سبيل المثال، يمكننا تشغيل سير العمل في أي وقت يوجد `دفعة` أو `سحب` على فرع `الرئيسي`.
```
على:
  الدفع:
    الفروع: [ الرئيسية]
  pll_request:
    الفروع: [ الرئيسية]
```
هناك العديد من الأحداث التي يمكن استخدامها لتشغيل سير العمل. يمكنك استكشافها [هنا](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions).

**3. الوظائف والخطوات**

هذه الكتلة تحدد المكون الأساسي لسير عمل العمل. تصنع سير العمل من `وظائف`. كل وظيفة تحتاج أيضًا إلى آلة مضيفة محددة لتشغيلها، `تشغيل:` الحقل هو كيفية تحديدها. يعمل قالب سير العمل على تشغيل `بناء` وظيفة في أحدث إصدار من Ubuntu، نظام تشغيل قائم على لينوكس.

```
الوظائف:
  بناء:
  يدور: ubuntu-latest
```

يمكننا أيضا فصل وظائف `بناء` و `اختبار` لسير العمل في أكثر من وظيفة واحدة سيتم تشغيلها عند تشغيل سير العمل. الوظائف مصنوعة من `خطوات`. هذه تسمح لك بتحديد ما يمكن تشغيله في كل وظيفة. وهناك ثلاث طرق لتحديد الخطوات.

- باستخدام `استخدامات`
- مع `تشغيل`
- مع `اسم`

```

الوظائف:
  بناء:
    تشغيل: ubuntu-latest
    خطوات:
    - استخدامات: الإجراءات/checkout@v2
  اختبار:
    خطوات:
    - الاسم: npm تثبيت
      تشغيل: <unk>
        npm تثبيت
        npm الاختبار
```

الإجراء الأساسي `actions/checkout@v2`. يستخدم هذا إجراء GitHub الذي تم توفيره يسمى [`الخروج`](https://github.com/actions/checkout) للسماح لسير العمل للوصول إلى محتويات المستودع. وتسير جميع خطوات العمل بشكل متتابع على الرابط المرتبط بالوظيفة. بشكل افتراضي، إذا فشلت خطوة، يتم تخطي الخطوات التالية من العمل. وتمثل كل كلمة مفتاحية عملية جديدة وقذيفة جديدة في بيئة التشغيل. عندما تقدم أوامر متعددة الأسطر، كل خط يعمل في نفس القذيفة.

ويتجاوز توفير دليل شامل لجميع الخيارات المتاحة نطاق هذا الاستعراض، وبدلاً من ذلك، نحن نحثكم على دراسة [الوثائق المرجعية الرسمية](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions) و/أو مراجع مشاريع المصدر المفتوح لتكوين CI في القسم السابق.
