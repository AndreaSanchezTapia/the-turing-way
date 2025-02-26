(r-open-hardware)=
# فتح الجهاز

"جهاز مفتوح"، أو "جهاز مفتوح المصدر" [{term}`def<Open Source Hardware>`]، يشير إلى مواصفات تصميم جسم مادي مرخص بطريقة يمكن معها دراسة الجسم المذكور، تم تعديلها، إنشاؤها، وتوزيعها من قبل أي شخص. مثل برمجيات المصدر المفتوح، "شفرة المصدر" للمعدات المفتوحة - المخططات، المخططات، التصميمات المنطقية، التصميمات المنطقية، رسومات أو ملفات التصميم المعين بالحاسوب، وما شابه ذلك، متاحة للتعديل أو التحسين من قبل أي شخص. يمكن للمستخدمين الذين لديهم إمكانية الوصول إلى الأدوات التي يمكنها قراءة هذه الملفات المصدرية والتلاعب بها تحديث وتحسين الجهاز المادي والكود الذي يقوم عليه، والقيام، إذا رغبوا في ذلك، بالمضي قدما في تقاسم هذه التعديلات.

وينبغي أن يكون من السهل الوصول إلى شفرة مصدر المعدات المفتوحة، ويفضل أن يكون الحصول على مكوناتها سهلا بالنسبة لأي شخص. وتزيل المعدات المفتوحة أساسا الحواجز الشائعة أمام تصميم وتصنيع السلع المادية؛ فهي توفر أكبر عدد ممكن من الناس القدرة على بناء وإعادة تشكيل وتبادل معرفتهم بتصميم المعدات ووظائفها.

وتجدر الإشارة إلى أن المعدات المفتوحة لا تعني بالضرورة مجاناً. Units may still be sold (by the original designer or by others), but users *could* build them from scratch. سواء اختاروا شراء الوحدة أم لا، يمكن للمستخدمين الحصول على فهم كامل لكيفية عمل المعدات من الوثائق والتصاميم المتاحة وما شابه ذلك.

(r-open-hardware-why)=
## لماذا افتح هارداريو؟

المعدات المفتوحة تسمح للباحثين بفهم ما تفعله معداتهم، وكيف تقوم بذلك، والتحقق من أنها تفعل ذلك بشكل صحيح، بدلاً من أن تضطر إلى تمديد درجة من الثقة. وإدراكا للكيفية التي تعمل بها المعدات التي تولد نتيجة، يضع الباحثين على أساس أقوى في تقييم تلك النتائج. المعدات المفتوحة أيضا تجعل البحث أكثر قابلية لأن الباحثين الذين يتطلعون إلى التحقق من النتائج يمكنهم القيام بنفس الشيء.

وتشمل الفوائد الأخرى للمعدات المفتوحة الحماية من القفل. وتزيد البرمجيات المسجلة الملكية للبنية التحتية الأساسية من خطر حبسها للبائع أو التكنولوجيا. إذا حدث ذلك، ويمكن للباحثين أن يكونوا تحت رحمة زيادة أسعار البائعين وأن يعانوا من انعدام المرونة التي لا يستطيعون الإفلات منها بسهولة وبسهولة. وعلاوة على ذلك، إذا كان الباحثون يرغبون في تعديل معداتهم لتلائم احتياجاتهم على نحو أفضل، ومن الأسهل بكثير القيام بذلك (وقد لا يكون ذلك إلا قانونيا) في حالة المعدات المفتوحة المصدر.

(بآلاف دولارات الولايات المتحدة)
## عناصر من مشروع جهاز مفتوح المصدر

فيما يلي بعض الملفات التي يجب أن تفكر في مشاركتها عند نشر مشروع الأجهزة المفتوح المصدر. ليس مطلوبا منك أن تنشر كلها، ولكن كلما شاركت أكثر، كلما زادت فوائد المجتمع. هناك الكثير من الملفات هنا مع الملفات لتضمينها في مشاريع برمجيات المصدر المفتوح.

(r-open-hardware-elements-Overview)=
### ألف - لمحة عامة ومقدمة
يجب أن يتضمن مشروع الأجهزة المفتوح المصدر وصفاً عاماً لهوية الجهاز والغرض منه، مكتوباً قدر الإمكان لجمهور عام. هذا هو، اشرح ما هو المشروع وما هو عليه قبل أن تدخل في التفاصيل التقنية.

(r-open-hardware-بعناصر-ترخيص)=
### ترخيص
الترخيص المناسب لمشروع المعدات المفتوحة ومحتوياتها يمنح الإذن القانوني لأي شخص بإعادة الاستخدام، تعديل وتوزيع مختلف مكونات المشروع وفقاً للشروط المذكورة (على سبيل المثال يجب أن تعترف بمساهمتك).

(فئة الخدمات العامة-العوامل-التصميم)=
### ملفات التصميم الأصلية

هذه هي ملفات المصدر التي ستستخدمها لإجراء تعديلات على تصميم المعدات. إن مشاركة هذه الملفات هي الممارسة الأساسية لأجهزة المصدر المفتوح.
- مثاليًا، سيتم تصميم مشروع الأجهزة المفتوح المصدر باستخدام تطبيق برمجيات مجانية ومفتوحة المصدر لتعظيم قدرة الآخرين على مشاهدتها وتحريرها.

ومن أجل الأفضل أو الأسوأ، كثيرا ما يتم إنشاء ملفات تصميم المعدات في برامج مسجلة الملكية وتخزينها في أشكال مسجلة الملكية. لا يزال من الضروري مشاركة ملفات التصميم الأصلية هذه؛ وهي تشكل "رمز المصدر" الأصلي للمعدات. وهي نفس الملفات التي سيحتاج إليها شخص ما من أجل المساهمة بتغييرات في تصميم معين.
- حاول جعل ملفات التصميم الخاصة بك سهلة لشخص آخر فهمها. وعلى وجه الخصوص، تنظيمها بطريقة منطقية، والتعليق على الجوانب المعقدة، والإشارة إلى أي إجراءات صناعية غير عادية.
- وتشمل الأمثلة على ملفات التصميم الأصلية رسومات ثنائية الأبعاد، وملفات التصميم بمساعدة الحاسوب.

(فئة الخدمات العامة-العامة-العناصر المساعدة)=
### ملفات التصميم المساعد

بالإضافة إلى ملفات التصميم الأصلية، من المفيد في كثير من الأحيان مشاركة تصميمك في صيغ إضافية أيسر منالا. فعلى سبيل المثال، تتمثل أفضل الممارسات المتبعة في الاستعانة بمصادر مفتوحة في تصميم النظام الحاسوبي الموحد في تقاسم التصميم ليس فقط في شكل الملف الأصلي، ولكن أيضاً في مجموعة من الأشكال القابلة للتبادل والتصدير التي يمكن فتحها أو استيرادها بواسطة برامج أخرى في مجال الترجمة بمساعدة الحاسوب.
- ومن المفيد أيضا توفير نواتج جاهزة للعرض يمكن أن ينظر إليها بسهولة المستعملون النهائيون الذين يرغبون في فهم التصميم (ولكن دون تعديله بالضرورة). ويمكن أن يكون هذا الناتج عبارة عن جهاز PDF لتخطيط لوحة دائرية. هذه ملفات التصميم المساعدة تسمح للناس بدراسة تصميم المعدات، بل وأحيانا يصنعها، حتى بدون الوصول إلى مجموعات برمجيات معينة مسجلة الملكية. غير أنه لاحظ أن ملفات التصميم المساعدة لا يوصى بها أبدا كبدائل لملفات التصميم الأصلية.

(r-open-hardware-بعناصر-رسوم) =
### مسودات فنية إضافية
ومن المفيد تقديم أي رسومات تقنية إضافية في أشكالها الأصلية إذا كانت لازمة لتصنيع الجهاز. ويمكن تقديم هذه الخدمات في شكل يمكن قراءته بصورة شائعة مثل قوات الدفاع الشعبي.

(r-open-hardware-elements-materials) =
### سند المواد

وفي حين أنه قد يكون من الممكن الاستنتاج من ملفات التصميم من الأجزاء التي تشكل قطعة من المعدات، ومن الضروري تقديم فاتورة مواد منفصلة. يمكن أن تكون فاتورة المواد صحيفة جدولية (على سبيل المثال، CSV، XLS، Google Doc) أو مجرد ملف نصي مع جزء واحد لكل سطر. والأشياء المفيدة لإدراجها في فاتورة المواد هي أعداد الجزئيات والموردين والتكاليف ووصف موجز لكل جزء منها. اجعل من السهل معرفة أي عنصر في فاتورة المواد يقابل أي مكون في ملفات التصميم الخاصة بك: استخدم المصممين المرجعيين المطابقين في كلا المكانين، توفير رسم بياني يبين الجزء الذي يذهب إليه أو يشرح المراسلات بطريقة أخرى.

(ص-مفتوح-عناصر-برامجيات)=
### البرمجيات والبرمجيات الثابتة

يجب عليك مشاركة أي كود أو برنامج ثابت مطلوب لتشغيل جهازك. هذا سيسمح للآخرين باستخدامه مع جهازهم أو تعديله جنبا إلى جنب مع تعديلاتهم على جهازك. توثيق العملية المطلوبة لبناء برنامجك، بما في ذلك الروابط لأي تبعية (على سبيل المثال، مكتبات أطراف ثالثة أو أدوات). ومن المفيد أيضاً تقديم لمحة عامة عن حالة البرمجيات (مثلاً، "مستقر" أو "بيتا" أو "اختراق يعمل في الطعام").

(r-open-hardware-elements-phototos)=
### الصور
الصور تساعد الناس على فهم ما هو مشروعك وكيفية جمعه معا. ومن المفيد نشر صور من وجهات نظر متعددة وفي مختلف مراحل التجميع. إذا لم يكن لديك صور، فإن نشر عروض ثلاثية الأبعاد للتصميم الخاص بك هو بديل جيد. وفي كلتا الحالتين، من المفيد تقديم عبارات أو نصوص تشرح ما يظهر في كل صورة ولماذا تكون مفيدة.

(r-open-hardware-بعناصر-تعليمات)=
### تعليمات وتفسيرات أخرى

بالإضافة إلى ملفات التصميم نفسها، هناك مجموعة متنوعة من التفسيرات التي لا تقدر بثمن في مساعدة الآخرين على صنع أو تعديل جهازك:
- صنع المعدات: لمساعدة الآخرين في صنع وتعديل تصميم المعدات الخاصة بك، يجب عليك تقديم إرشادات للانتقال من ملفات التصميم الخاصة بك إلى الأجهزة المادية العاملة. وكجزء من التعليمات، من المفيد الربط إلى أوراق البيانات لمكونات/أجزاء من جهازك وقائمة الأدوات المطلوبة لتجميعها. إذا كان التصميم يتطلب أدوات متخصصة، أخبر الناس أين يحصلون عليها.
- استخدام المعدات: بمجرد قيام شخص ما بصنع المعدات، يجب عليهم معرفة كيفية استخدامها. توفير التعليمات التي تشرح ما يفعله، وكيفية إنشاءه، وكيفية التفاعل معه.
- منطق التصميم: إذا كان شخص ما يريد تعديل تصميمك، فسيريدون أن يعرفوا لماذا هي الطريقة التي يعمل بها. اشرح الخطة العامة لتصميم المعدات ولماذا قمت باختيارات محددة قمت بها.
- الحد من: ضع نصب أعيننا أن هذه التعليمات يمكن أن يقرأها شخص تختلف خبرته أو تدريبك. أكبر قدر ممكن، حاول الكتابة إلى جمهور عام، تحقق من تعليماتك الخاصة بالرغمات الصناعية، وكن صريحاً حول ما تفترض أن المستخدم يعرف ذلك.
- الشكل: يمكن أن تكون التعليمات في أشكال متنوعة، مثل wiki أو ملف نصي أو Google Doc، أو PDF. تذكر، على الرغم من ذلك، أن الآخرين قد يرغبون في تعديل تعليماتك أثناء تعديل تصميم الأجهزة الخاصة بك، لذا من الجيد توفير الملفات الأصلية القابلة للتحرير لتوثيقاتك، وليس فقط صيغ الإخراج مثل PDF.

(عمليات معدات مفتوحة) =
## العمليات والممارسات البرمجية المفتوحة المصدر

(ص-عمليات تصميم المعدات المفتوحة)=
### تصميم جهازك

إذا كنت تخطط لفتح مصدر قطعة معينة من المعدات، واتباع بعض أفضل الممارسات في تصميمه سيسهل على الآخرين صنع المعدات وتعديلها:

- استخدام أدوات تصميم البرمجيات الحرة والمفتوحة المصدر عندما يكون ذلك ممكناً: إذا لم يكن ذلك ممكناً، حاول استخدام مجموعات برمجيات منخفضة التكلفة و/أو واسعة الاستخدام.
- استخدام المكونات والمواد القياسية والمتاحة على نطاق واسع عمليات الإنتاج: حاول تجنب الأجزاء غير المتاحة للعملاء الأفراد أو العمليات التي تتطلب تكاليف إعداد باهظة.

(r-open-equipware-hosting)=
### استضافة ملفات التصميم الخاصة بك

إحدى الطرق الرئيسية لمشاركة ملفاتك هي مع ملف مضغوط على موقعك. ولئن كانت هذه بداية عظيمة، فإنها تجعل من الصعب على الآخرين متابعة التقدم الذي أحرزتموه أو المساهمة في تحسينه. قد يكون استخدام مستودع مصدر-كود على الإنترنت (مثل GitHub، أو GitLab، أو NotaBug) مكانا أفضل لتخزين مشاريع الأجهزة المفتوحة المصدر.

(ص-عمليات المعدات المفتوحة - التوزيع)=
### توزيع الأجهزة المفتوحة المصدر

- قم بتوفير وصلات للمصدر (ملفات التصميم الأصلية) لأجهزتك على المنتج نفسه، أو تغليفه أو وثائقه.
- اجعل من السهل العثور على المصدر (ملفات التصميم الأصلية) من موقع الويب للحصول على منتج.
- قم بتسمية الجهاز برقم الإصدار أو تاريخ الإصدار حتى يتمكن الناس من مطابقة الكائن المادي مع النسخة المقابلة من ملفات التصميم.
- وعلى العموم، تشير بوضوح إلى الأجزاء من المنتج التي تكون مفتوحة المصدر (والأجزاء التي لا تكون متاحة).
