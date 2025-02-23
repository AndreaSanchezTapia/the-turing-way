(rr-vcs-workflow)=
# سير العمل العام

التحكم في الإصدار هو نهج منهجي لتسجيل التغييرات التي تحدث في ملف، أو مجموعة من الملفات، مع مرور الوقت. وهذا يتيح لك ولمعاونيك تتبع التاريخ، ومعرفة ما تم تغييره، واستدعاء إصدارات محددة في وقت لاحق عند الحاجة. وفيما يلي إجراء نموذجي لاستخدام التحكم في النسخة:

1. إنشاء ملفات - قد تحتوي على نص أو كود أو كليهما.
2. العمل على هذه الملفات، بتغيير أو حذف أو إضافة محتوى جديد.
3. إنشاء لقطة من حالة الملف (المعروفة أيضًا بالإصدار) في هذا الوقت.

ووصفت عملية إنشاء لقطة بشكل مختلف في مختلف برامج التحكم في الإصدار. فعلى سبيل المثال، تصف Git ذلك بأنه "التزام". بعض النظم تسميها "نقطة زمنية" أو "نقطة تفتيش"؛ وهذا يشار إليه باسم "حفظ عملك" في حالات أخرى مثل [مستندات جوجل](https://docs.google.com/) أو [HackMD](http://hackmd.io/).

بينما تستمر في حفظ عملك بإضافة تغييرات، تصنع المزيد والمزيد من اللقطة. يمكنك التفكير في هذه على أنها حفظ إصدارات من هذه الملفات أثناء توثيق تاريخها. إذا كنت بحاجة إلى العودة إلى نسخة سابقة من الملف بسبب الخطأ، أو إذا غيرت رأيك حول تحديث سابق، يمكنك الوصول إلى الملف في الإصدار المفضل الخاص بك، أو إعادة المشروع بأكمله إلى حالة سابقة.

ويرد أدناه مثال على ذلك.

```{figure} ../../figures/main-branch.png
---
name: main-branch
البديل : مثال توضيحي للفرع الرئيسي
---
مثال توضيحي للفرع الرئيسي
```

في العديد من أنظمة تحكم الإصدار، ستتمكن من إضافة تعليق في كل مرة تقوم بحفظ إصدار جديد. وينبغي أن تكون هذه التعليقات واضحة وموجزة لتيسير فهم التغييرات المقترحة والتحديثات التي أجريت في صيغة ما. وهذا يضمن أنه من السهل العثور على ما تبحث عنه عندما تحتاج إلى العودة إلى إصدار سابق. سيشكرك المتعاونون معك، ولكن كذلك ستصدر الإصدارات من نفسك.

(rr-vcs-workflow-Branches)=
## التطوير غير الخطي لمشروعك مع "الفروع"

إذاً لديك مشروعك وترغب في إضافة شيء جديد أو محاولة شيء قبل أن تعكس التغييرات في مجلد المشروع الرئيسي. لإضافة شيء جديد، يمكنك الاستمرار في تحرير ملفاتك وحفظها مع التغييرات المقترحة. لنفترض أنك تريد تجربة شيء ما دون أن تعكس التغييرات في المستودع المركزي. في تلك الحالة، يمكنك استخدام خاصية "فرع" أنظمة تحكم أكثر تقدماً مثل Git. يقوم الفرع بإنشاء نسخة محلية من المستودع الرئيسي حيث يمكنك العمل وتجربة تغييرات جديدة. لن يتم التفكير في أي عمل تقوم به في فرعك في مشروعك الرئيسي (المشار إليه بفرعك الرئيسي) لذلك فإنه يبقى آمناً وخالياً من الأخطاء. في نفس الوقت، يمكنك اختبار أفكارك واستكشاف الأخطاء في فرع محلي.

عندما تكون سعيدا بالتغييرات الجديدة، يمكنك تقديمها للمشروع الرئيسي. وتسمح خاصية الدمج في نظام Git بإدماج خطوط التنمية المستقلة في فرع محلي في الفرع الرئيسي.

```{figure} ../../figures/one-branch.png
---
الاسم: فرع واحد
البديل : مثال توضيحي للتطوير والفرع الرئيسي في git
---
مثال توضيحي للتطوير والفرع الرئيسي في git.
```

يمكنك أن يكون لديك أكثر من فرع واحد من نسختك الرئيسية. إذا كان أحد فروعك لا يعمل، يمكنك إما التخلي عنه أو حذفه دون التأثير على الفرع الرئيسي لمشروعك.

```{figure} ../../figures/two-branches.png
---
الاسم: فرعان
البديل : مثال توضيحي لفرعين للتنمية وفرع رئيسي واحد في git
---
فرعان للتنمية وفرع رئيسي واحد في git.
```

إذا أردت، يمكنك إنشاء فروع من الفروع (وفروع من هذه الفروع وما إلى ذلك).

```{figure} ../../figures/sub-branch.png
---
الاسم: فرع فرعي 1
البديل : مثال توضيحي لفرع التطوير في Git.
---
فرع تنمية في Git.
```

بغض النظر عن عدد الفروع التي لديك، يمكنك الوصول إلى الإصدارات السابقة التي قمت بها على أي منها. إذا كنت ترغب في معرفة كيفية استخدام هذه الميزة في الممارسة، سوف تجد المزيد من التفاصيل في بعض الأقسام المقبلة.
