(rr-renv-binder)=
# عشق

(rr-renv-binder-Overview)=
## نظرة عامة

الآن بعد أن رأينا كيفية استخدام واستيعاب البيئة الحسابية المستخدمة في مشروع بايثون (Python)، وقد حان الوقت للتفكير في كيفية تقاسم تلك البيئة.

مع ملف `environment.yml` (أو ما شابه ذلك، من أنظمة إدارة الحزمة البديلة)،يمكن للآخرين إعادة إنشاء البيئة المحددة بهذا الملف. غير أن ذلك يعتمد على وجود نفس نظام إدارة الحزمة للمستخدم الجديد الذي تم إنشاؤه ومعرفة كيفية استخدامه. سيكون من الأسهل بكثير لو كان هناك حل آلي لإعادة إنشاء البيئة الحسابية - وهذا هو المكان الذي يأتي فيه بيندر.

يستخدم بيندر أداة تسمى `repo2docker` لإنشاء صورة Docker للمشروع استنادًا إلى ملفات التكوين المضمنة. تحتوي الصورة الناتجة على المشروع والبيئة الحسابية التي حددها المستخدم الأصلي. يمكن للمستخدمين الآخرين الوصول إلى الصورة عبر BinderHub، القائم على السحابة، والذي يسمح لهم بعرض وتحرير وتشغيل التعليمات البرمجية من متصفح الويب الخاص بهم.

ويوضح كارتون جولييت تاكا الممتاز أدناه الخطوات المتخذة في إنشاء مشروع "ملزم" وتقاسمه.

**الخطوة 1:** نبدأ مع باحثة أكملت مشروعاً وترغب في مشاركة عملها مع أي شخص، بغض النظر عن بيئتهم الحسابية. ملاحظة أن بيندر لا يتعين تطبيقه فقط على المشاريع المنجزة؛ ويمكن استخدامها بنفس الطريقة لتقاسم المشاريع الجارية.

**الخطوة 2:** يحتوي مشروع الباحث على العديد من الملفات من أنواع مختلفة. وفي هذه الحالة، كان الباحث يعمل في دفاتر مذكرات المشتري. ومع ذلك، يمكن استخدام Binder بنفس القدر من الفعالية مع العديد من صيغ الملفات واللغات الأخرى التي سنغطيها بمزيد من التفصيل قريبا.

**الخطوة 3:** يرفع الباحث تعليماتها البرمجية إلى خدمة استضافة مستودع متاحة للجمهور، مثل GitHub، حيث يمكن للآخرين الوصول إليها. وهي تتضمن ملفاً يصف البيئة الحسابية اللازمة لتشغيل المشروع.

**الخطوة 4:** تقوم بإنشاء رابط في [mybinder.org](https://mybinder.org) BinderHub. بالنقر على هذا الرابط، يمكن لأي شخص الوصول إلى نسخة "ملزمة" من مشروعها. يؤدي النقر إلى تشغيل `repo2docker` لبناء صورة Docker استنادًا إلى محتويات المستودع وملفات الإعدادات الخاصة به. ثم يتم استضافة هذه الصورة على السحابة. الشخص الذي أنقر على الرابط سوف يُنقل إلى نسخة من مشروعها في متصفح الويب الخاص به حيث يمكنه التفاعل معه. وتستضيف هذه النسخة من المشروع في البيئة التي يحددها الباحث في الخطوة 3، بغض النظر عن البيئة الحسابية التي يمكن الوصول إليها منها.

```{figure} ../../figures/binder-comic.png
---
الاسم: binder-comic
البديل : مثال توضيحي للخطوات التي يمكن أن يتخذها الشخص لإنشاء مشروع مربط.
---
رصيد الشكل - [Juliette Taka, Logilab و OpenDreamKit project](https://opendreamkit.org/2017/11/02/use-case-publishing-reproducible-notebooks/)
```

للحصول على فكرة عن الشكل الذي يبدو عليه هذا، أدناه هو عبارة عن مشروع نموذج بسيط. الملفات مدرجة ويمكن النقر عليها وتعديلها من قبل الشخص الذي يصل إلى الباندر.

```{figure} ../../figures/binder-home.png
---
name: binder-Home
البديل : لقطة شاشة لمنصة لمشروع عينة
---
مقطع لمشروع عينة.
```

يمكن للمستخدمين أيضًا فتح المحطات الطرفية لتشغيل أو التفاعل مع الملفات بالنقر على "جديد" ثم على "المحطة الطرفية" في أعلى يمين شاشة بيندر الرئيسية الموضحة أعلاه. هنا يستخدم هذا لتشغيل النص النصي للتحليل في المثال Binder الذي يقوم بانحدار خطي على بعض البيانات:

```{figure} ../../figures/binder-terminal.png
---
name: binder-Teral
البديل : لقطة شاشة لمحطة طرفية حيث يمكن للمستخدمين تشغيل أو التفاعل مع ملفات المشروع
---
لقطة شاشة لمحطة طرفية حيث يمكن للمستخدمين تشغيل أو التفاعل مع ملفات المشروع
```

وكما سبقت الإشارة، فإن بيندر مندمج بشكل جيد مع دفاتر ملاحظات المشتري. يمكن فتح دفاتر الملاحظات بالنقر على "جديد" ثم على "المذكرات" بنفس الطريقة التي يمكن بها فتح المحطات الطرفية. قد تكون هذه أكثر ملاءمة لأولئك الذين يعملون مع مخرجات الرسوم البيانية، كما هو مبين هنا حيث يستخدم واحد لتشغيل `make_plot. y` في المثال Binder:

```{figure} ../../figures/binder-notebook.png
---
الاسم: Binder-note
البديل : لقطة شاشة لمذكرات المشتري مدمجة مع Binder
---
لقطة شاشة لمذكرات المشتري مدمجة مع Binder
```

إذا تم تثبيت R في Binder، ستظهر القائمة المنسدلة الخيارات لفتح دفتر ملاحظات المشتري R و RStudio جلسات في Binder.

(rr-renv-binder-disambiguation)=
## التشكك

وفي هذا الفرع، هناك بعض المصطلحات ذات الصلة التي سيجري إيجازها هنا توخيا للوضوح:

- **Binder**: نسخة مشتركة من المشروع الذي يمكن رؤيته والتفاعل معه في بيئة حسابية قابلة للتكرار عن طريق متصفح ويب.
- **BinderHub**: خدمة تنتج Binders. الأكثر استخداما هو [mybinder.org](https://mybinder.org)، الذي يديره فريق بيندر. من الممكن إنشاء BinderHubs الأخرى التي يمكن أن تدعم تشكيلات أكثر تخصصاً. ويمكن أن يشمل أحد هذه التشكيلات المصادقة لتمكين المستودعات الخاصة من تقاسمها فيما بين المتعاونين الوثيقين.
- **[mybinder.org](https://mybinder.org)**: BinderHub. لأنه عام، يجب ألا تستخدمه إذا كان مشروعك يتطلب أي معلومات شخصية أو حساسة (مثل كلمات المرور).
- **قرع**: لصنع باوندر للمشروع.

(rr-renv-binder-creating)=
## إنشاء بايندر لمشروع

وينطوي إنشاء نسخة مزدوجة من المشروع على ثلاث خطوات رئيسية سيتم شرحها في هذا الفرع:

1. تحديد البيئة الحسابية
2. ضع ملفات المشروع في مكان ما متاحة للعموم (سوف نصف كيفية القيام بذلك باستخدام GitHub)
3. إنشاء رابط إلى بايندر من المشروع

للحصول على قائمة من مستودعات العينة لاستخدامها مع Binder، انظر صفحة [مستودعات عينة من Binder](https://mybinder.readthedocs.io/en/latest/sample_repos.html).

(rr-renv-binder-creating-stepone)=
### الخطوة 1: تحديد البيئة الحسابية

لنفترض أن المشروع لا يحتوي على ملف يحدد البيئة الحاسوبية. عندما يتم إنشاء Binder ، ستكون البيئة هي بيئة Binder الافتراضية (تحتوي على Python 3. ) الذي قد يكون مناسبا أو غير مناسب للمشروع. ومع ذلك، إذا كان يحتوي على ملف تكوين للبيئة، فسيتم إنشاء Binder مع البيئة المحددة. قائمة كاملة من هذه الملفات يقبل Binder ، مع أمثلة ، يمكن العثور على [هنا](https://mybinder.readthedocs.io/en/latest/config_files.html). وترد أدناه مناقشة للمفاهيم، بعضها خاص بلغات:

- `البيئة.yml`
  - تذكر أن ملفات `environment.yml` قد نوقشت في قسم {ref}`rr-renv-package`.
- ملف Dockerfile
  - سيتم مناقشة ملفات Dockers في قسم {ref}`rr-renv-containers` ، لذلك لن يتم مناقشتها بمزيد من التفصيل هنا.
- `apt.txt`
  - التبعيات التي يتم تثبيتها عادة عن طريق أوامر مثل `sudo apt-get install package_name` يجب أن تكون مدرجة في `واب. xt` ملف ، وسيتم تثبيته تلقائياً في Binder.
  - على سبيل المثال إذا كان المشروع يستخدم Latex ملف `apt.txt` يجب أن يكون
    ```
    texlive-latex-base
    ```
    لتثبيت حزمة Latex الأساسية.
- `default.nix`
  - لمن يستخدمون {ref}`rr-renv-pack` Nix a `default.nix` يمكن أن يكون طريقة مناسبة للالتقاط بيئتهم.
- `requirements.txt` (Python)
  - بالنسبة لمستخدمي بايثون `requirements.txt` يمكن استخدام ملف لقائمة الحزم المعتمدة.
  - على سبيل المثال، للحصول على تثبيت Binder `numpy` يحتاج هذا الملف ببساطة إلى ما يلي:
    ```
    numpy
    ```
  - يمكن أيضا تحديد إصدار حزمة محددة باستخدام `==`. على سبيل المثال، للحصول على نسخة Binder المثبتة `1.14.5` من `numpy` ثم سيكون الملف
    ```
    numpy==1.14.5
    ```
  - الملف `requirement.txt` ليس بحاجة إلى أن يكون مكتوبا يدويا. تشغيل الأمر `pip تجميد > requirements.txt` سيخرج ملف `requirements.txt` الذي يحدد بيئة بايثون تعريفا كاملا.
- `runtime.txt`
  - يستخدم لتحديد إصدار معين من Python أو R لاستخدامه Binder .
  - لتحديد نسخة R المراد استخدامها، ابحث عن التاريخ الذي تم التقاط فيه على [MRAN](https://mran.microsoft.com/documents/rro/reproducibility) وإدراجه في `زمن التشغيل. ملف xt` كـ
    ```
    r-<YYYY>-<MM>-<DD>
    ```
  - لتحديد إصدار من Python، حدد الإصدار في ملف `runtime.txt`. على سبيل المثال، لاستخدام Python 2.7، سيحتاج الملف إلى قراءة
    ```
    python-2.7
    ```
- `install.R` أو `DSCRIPTION` (R/RStudio)
  - ملف `install.R` يسرد الحزم التي سيتم تثبيتها. على سبيل المثال، لتثبيت الحزمة `tibble` في Binder:
    ```
    install.packages("tibble")
    ```
  - [ملفات DSCRIPTION](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#The-DESCRIPTION-file) تستخدم عادة في مجتمع R لإدارة التبعية.

(rr-renv-binder-creating-steptwo)=
### الخطوة 2: وضع التعليمات البرمجية الخاصة بك على GitHub

تتم مناقشة GitHub مطولاً في الفصل على {ref}`rr-vcs`، الذي يجب أن تشير إليه إذا كنت ترغب في فهم المزيد حول هذه الخطوة. وفي هذا الفصل، سنقدم تفسيرا موجزا. GitHub منصة تستخدم على نطاق واسع جدا حيث يمكنك إنشاء "مستودعات" وتحميل الكود أو الوثائق أو أي ملفات أخرى فيها. لإكمال هذه الخطوة:

1. إنشاء حساب على [GitHub](https://github.com/).
2. قم بإنشاء مستودع للمشروع الذي ترغب في إنشاء مخزن له.
3. قم بتحميل ملفات مشروعك (بما في ذلك الملف الذي قمت بإنشائه لتحديد البيئة الحسابية الخاصة بك) إلى المستودع وحفظها ("التزام" في مفردات GitHub) هناك.

إذا كنت غير قادر على إكمال هذه الخطوات، يرجى الرجوع إلى الفصل الخاص بـ {ref}`التحكم في الإصدار <rr-vcs>` للحصول على تفسير أكمل.

(rr-renv-binder-creating-stepالثلاثي)=
### الخطوة 3: إنشاء رابط إلى بينار من مشروعك

انتقل إلى [https://mybinder.org](https://mybinder.org). سترى استمارة تطلب منك تحديد مستودع لـ [mybinder.org](https://mybinder.org) للبناء. في الحقل الأول، قم بلصق عنوان URL لمستودع GitHub للمشروع. سوف يبدو شيئا مثل هذا: `https://github.com/<your-username>/<your-repository>`

```{figure} ../../figures/mybinder-gen-link.png
---
الاسم: mybinder-gen-link
البديل : لقطة شاشة من صفحة الويب المستخدمة لإنشاء رابط بيندر لمشروعك
---
واجهة لإنشاء روابط بيندر للمشاريع
```

وكما ترون، هناك مجالات إضافية في هذا الشكل، ولكنها اختيارية ولن تناقش هنا.

بمجرد توريد عنوان URL للمشروع المراد ربطه، سيتم ملء حقلين تلقائياً على الشاشة الموضحة أعلاه:

- `نسخ عنوان URL أدناه ومشاركة Binder الخاص بك مع الحقل` الآخر، يوفر رابط Binder الذي يمكن نسخه ومشاركته.
- `نسخ النص أدناه، ثم لصق في README الخاص بك لإظهار حقل شارة بيندر` ، يمكن أن يتم تضمينه في GitHub لإنشاء زر يسمح لأي شخص يصل إلى مشروعك لتشغيل Binder.

أخيرا، انقر فوق زر التشغيل. هذا سيطلب من [mybinder.org](https://mybinder.org) بناء البيئة اللازمة لتشغيل المشروع. وقد يستغرق ذلك عدة دقائق. يمكنك النقر على زر `بناء سجلات` لرؤية السجلات التي تم إنشاؤها من خلال عملية البناء. هذه السجلات تساعد على حل أي مشاكل تسبب فشل البناء، مثل الأخطاء في الملف الذي يحدد البيئة الحسابية التي سيتم إنشاؤها.

وبمجرد أن يتم بناءها، سيطلق البندر تلقائياً؛ ومرة أخرى، قد يستغرق ذلك بعض الوقت.

(rr-renv-binder-data)=
## بما في ذلك البيانات في Binder

هناك بعض الطرق لجعل البيانات متاحة في Binder. يعتمد أفضل واحد على حجم البيانات الخاصة بك والتفضيلات الخاصة بك لمشاركة البيانات. لاحظ أنه كلما زاد عدد البيانات المشمولة، كلما استغرق الأمر وقتا أطول لإطلاقها. البيانات أيضا تستحوذ على مساحة تخزين يجب دفع ثمنها، لذلك من الجيد أن تكون موضع نظر وتقلل من البيانات التي تضمنها، خاصة على [ميبيندر المقدمة للجمهور. rg](https://mybinder.org).

(rr-renv-binder-data-small)=
### ملفات عامة صغيرة

أبسط نهج لملفات البيانات الصغيرة العامة هو إضافتها مباشرة إلى مستودع GitHub الخاص بك أو تضمينها إلى جانب بقية ملفات مشروعك في Binder. ويعمل هذا بشكل جيد وهو معقول بالنسبة للملفات التي تصل أحجامها إلى 10 ميغابايت.

(rr-renv-binder-data-medi)=
### الملفات العامة المتوسطة

وبالنسبة للملفات المتوسطة الحجم - بضع 10 ثوان من الميغابايت إلى بضع مئات من الميغابايت - تجد أماكن أخرى على الإنترنت لتخزينها والتأكد من إتاحتها للجمهور. أضف ملفًا اسمه `بريد` (وهو سكريبت قذيفة) لذا يجب أن يكون السطر الأول `#! bin/bash`) إلى ملفات مشروعك. في ملف `بريد` ، أضف سطر واحد يقرأ:
```
ربح -q -O name_of_your_file link_to_your_file
```

يتم استخدام ملف `بريد` لتنفيذ الأوامر عندما يتم إنشاء الملفات لإنتاج بايندر. في هذه الحالة، يمكن استخدامه لتحميل بياناتك إلى الملفات المستخدمة لتشغيل البوصلة.

(rr-renv-binder-data-كبير)=
### ملفات عامة كبيرة

الخيار الأفضل للملفات الكبيرة هو استخدام مكتبة خاصة بتنسيق البيانات لبث البيانات أثناء استخدامها. هناك بعض القيود على حركة المرور الصادرة من بيندر الخاص بك والتي يفرضها الفريق الذي يعمل [mybinder.org](https://mybinder.org). يسمح حاليا فقط بالاتصالات مع HTTP و Git. ويأتي هذا عندما يريد الناس استخدام مواقع FTP لجلب البيانات. لأسباب أمنية FTP غير مسموح به على [mybinder.org](https://mybinder.org).
