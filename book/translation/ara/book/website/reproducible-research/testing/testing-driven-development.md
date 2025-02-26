(ص - اختبار - تطوير مدفوع)=
# اختبار التطوير المدفوع

وإحدى طرق ضمان عدم إهمال الاختبارات في أي مشروع هي اعتماد عملية تطوير مدفوعة بالاختبار. وهذا نهج تُكتب فيه اختبارات الوحدة قبل وضع الشفرة. وهكذا تصف الاختبارات "عقد" من المتوقع أن يمتثل له الرموز. وهذا يكفل أن تكون الشفرة صحيحة (بقدر ما يمكن إنفاذها بموجب عقد الاختبار) بصيغتها المكتوبة، ويوفر إطاراً مفيداً للتفكير في كيفية تصميم المدونة، ما الذي يجب أن توفره ، وكيف يمكن أن تعمل الخوارزميات الخاصة بها. يمكن أن يكون هذا مساعدة عقلية مرضية جداً في تطوير خوارزميات عسيرة.

وبمجرد كتابة الاختبارات، توضع التعليمات البرمجية بحيث تجتاز جميع الاختبارات المرتبطة بها. اختبار الكود منذ البداية يضمن أن الكود الخاص بك دائما في حالة قابلة للإفراج (طالما أنه يجتاز الاختبارات!). اختبر التطوير المدفوع يجبرك على تقسيم التعليمات البرمجية الخاصة بك إلى وحدات صغيرة منفصلة، لجعلها أسهل لاختبارها؛ يجب أن تكون التعليمات البرمجية وحدة. تمت مناقشة فوائد هذا في القسم الخاص بـ {ref}`اختبار الوحدة<rr-testing-unittest>`.

وثمة نهج للتنمية البديلة يتمثل في التنمية القائمة على السلوك. ببساطة، تحت نموذج التطوير الذي يحركه الاختبار، نحن نتحقق من "هل تم فعل الشيء بشكل صحيح؟ , بينما في إطار التطوير المدفوع بالسلوك نقوم باختبار "هل تم إنجاز الشيء الصحيح؟". وتستخدم هذه البرامجيات في أغلب الأحيان في تطوير البرامجيات التجارية لتركيز التطوير على جعل البرامجيات بسيطة وفعالة قدر الإمكان بالنسبة للمستعملين. نادراً ما تكون تجربة المستخدم في قلب التعليمات البرمجية المكتوبة لأغراض البحث، ولكن هناك حالات تكتب فيها هذه البرمجيات مع مراعاة قاعدة كبيرة من المستخدمين. وفي مثل هذه الحالات، يكون التطور القائم على السلوك طريقا جديرا بالنظر فيه.
