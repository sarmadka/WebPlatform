# WebPlatform

[[English]](canvas_example.en.md)

[[رجوع]](../readme.ar.md)

## أمثلة

### التعامل مع المرسم

<div dir=rtl>

```
اشمل "مـحا"؛
مـحا.اشمل_ملف("Alusus/WebPlatform"، "مـنصة_ويب.أسس")؛
مـحا.اشمل_ملف("Alusus/Http"، "بـننف.أسس")؛
مـحا.اشمل_ملف("Alusus/Json"، "جـيسون.أسس")؛
مـحا.اشمل_ملف("Alusus/Promises"، "مـؤجلات.أسس")؛
اشمل "مـتم/سندات"؛
اشمل "مـتم/مـصفوفة"؛
اشمل "مـتم/نـص"؛
اشمل "مـتم/طـرفية"؛
اشمل "مـتم/ريـاضيات"؛

استخدم مـتم؛
استخدم مـنصة_ويب؛

//=============================================================================
// الخادم

// نقوم بتعريف المسار الذي سنخزن عليه الموارد
@مسار_موارد عرف مسار_الموارد: "Assets/"؛

//=============================================================================
// واجهة المستخدم

عرف _خط_الكتابة_: "30px AlususMono"؛
عرف _لون_اصلي_: لـون("8e50ef")؛

// دالة لإنشاء ودجة الترويسة
دالة أنشئ_الترويسة():سـندنا[Widget]{
    // هنا نقوم بإنشاء مساحة مستطيلة لوضع مكونات الودجة ضمنها
    أرجع صـندوق({}).{
        // الأطرزة المستعملة لهذه الودجة
        الطراز.{
            العرض = مـسافة.مئوي(100)؛
            الطول = مـسافة.نقاط(40)؛
            الحشوة = مـسافة4.نقاط(5، 0)؛
            الخلفية = خـلفية(_لون_اصلي_)؛
            لون_الإطار = _لون_اصلي_؛
            سمك_الإطار = مـسافة4.نقاط(1.5)؛
            طراز_الإطار = طـراز_إطار._مستمر_؛
            الإظهار = إظـهار._مرن_؛
            النسق = نـسق._عمود_؛
        }؛
        // مكونات الودجة و التي نعتبرها فروع للودجة
        أضف_فروع({
            // هنا سيكون لدينا فقط نص يوضح أننا ننشأ مثال عن المرسم
            كـتابة(نـص("أمثلة منصة ويب الأسس - مرسم")).{ الطراز.{
                لون_الخط = لـون("fff")؛
                حجم_الخط = مـسافة.نقاط(21.0)؛
                العرض = مـسافة.مئوي(100)؛
                الطول = مـسافة.مئوي(100)؛
                الخلفية = خـلفية(_لون_اصلي_)؛
                الهامش = مـسافة4.نقاط(5، 15)؛
            } }
        })؛
    }؛
}

// صنف لنضع ضمنه معلومات الموقع ضمن الشاشة على شكل إحداثيات
صنف مـوقع {
    عرف س: صحيح؛
    عرف ص: صحيح؛
}

// منفذ بياني لموقع الويب خاصتنا
// هنا نحدد أولاً المسار و سيكون لدينا الجذر هنا
// و ثانياً نضع العنوان الخاص بهذا المنفذ البياني
@منفذ_مرئي["/"، "مثال منصة ويب - مرسم"]
دالة رئيسي {
    // سنقوم هنا بتحميل الموارد من السيرفر
    // في البداية نقوم بتعريف مورد من أجل كل نوع موارد نريده
    // مورد للصورة
    عرف صورة: مـورد_صورة؛
    // مورد للصوت
    عرف موسيقى: مـورد_صوت؛
    // مورد للصوت
    عرف صوت: مـورد_صوت؛
    // نقوم بتحميل الموارد بشكل لامتزامن
    انتظر(مـؤجلات.مـؤجلة[صحيح].الكل({
        // لتحميل الصورة يكفي استدعاء تابع التحميل مع مسار الصورة
        صورة.حمل("Assets/logo.svg"),
        // نقوم بتحميل الخط عن طريق اسم الخط و المسار الخاص به
        حمل_خط("AlususMono", "Assets/AlususMono.otf"),
        // أيضاً لتحميل الصوت يكفي استدعاء تابع التحميل مع مسار الملف الصوتي
        موسيقى.حمل("Assets/music.mp3"),
        صوت.حمل("Assets/sound.mp3")
    }).تجاهل_النتيجة())؛

    // نقوم بتعريف بعض المتغيرات التي سنحتاجها تالياً
    // متغير لتخزين الموقع
    عرف موقع: مـوقع؛
    موقع.س = 200؛
    موقع.ص = 150؛
    // متغير لتخزين الحركة
    عرف تغير: مـوقع؛
    تغير.س = تغير.ص = 0؛
    // متغير لتخزين فيما إذا تم الضغط على المؤشر أم لا
    عرف مضغوط: ثنائي = 0؛
    // متغير لتخزين فيما إذا قد تم قفل المؤشر أم لا
    عرف المؤشر_محتكر: ثنائي = 0؛
    // متغير لتحديد فيما إذا كنا في وضع ملء الشاشة أم لا
    عرف ملء_الشاشة: ثـنائي = 0؛
    // متغير لتخزين عدد المقابض
    عرف عدد_المقابض: صحيح = 0؛

    // بناء المشهد
    عرف مرسم: سـندنا[مـرسم]؛
    // نقوم بتطبيق بعض الأطرزة على النافذة
    // هنا مثلاً طبقنا أننا لا نريد حشو أو هوامش
    نـافذة.النموذج.الطراز.{
        الحشوة = مـسافة4.نقاط(0)؛
        الهامش = مـسافة4.نقاط(0)؛
    }؛
    // نقوم بتحديد المشهد الخاص بالنافذة
    نـافذة.النموذج.حدد_المشهد(صـندوق({}).{
        // بعض الأطرزة لتطبيقها على المساحة المربعة التي سنعرف ضمنها المرسم
        // و الأدوات الخاصة به
        الطراز.{
            المحاذاة = مـحاذاة._وسط_؛
            الإظهار = إظـهار._مرن_؛
            النسق = نـسق._عمود_؛
            الاتجاه = اتـجاه._من_اليمين_؛
        }؛
        أضف_فروع({
            // نقوم بإضافة الترويسة التي عرفنا دالة إضافتها سابقاً.
            أنشئ_الترويسة(),
            // مساحة مربعة أخرى لإضافة بعض الخيارات الخاصة بالصوت
            صـندوق({}).{
                الطراز.الإظهار = إظـهار._مرن_؛
                الطراز.النسق = نـسق._سطر_؛
                أضف_فروع({
                    // زر لتشغيل الموسيقى
                    الـزر(نـص("شغل الموسيقى")).{
                        الطراز.{
                            الطول = مـسافة.نقاط(30)؛
                            العرض = مـسافة.نقاط(120)؛
                            الخلفية = خـلفية(لـون(200, 200, 200))؛
                            حجم_الخط = مـسافة.نقاط(16.0)؛
                        }؛
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الموسيقى
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نمرر أننا نريد تشغيل بالموسيقى بشكل متكرر
                        عند_الضغط.اربط(مغلفة (موسيقى: كسند)&(ودجة: سند[ودجـة], حمولة: سند[صحيح]) {
                            موسيقى.شغل(1)؛
                        })؛
                    },
                    // زر لإيقاف تشغيل الموسيقى
                    الـزر(نـص("أوقف الموسيقى")).{
                        الطراز.{
                            الطول = مـسافة.نقاط(30)؛
                            العرض = مـسافة.نقاط(120)؛
                            الخلفية = خـلفية(لـون(200, 200, 200))؛
                            حجم_الخط = مـسافة.نقاط(16.0)؛
                        }؛
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بإيقاف الموسيقى
                        // و ذلك عبر استدعاء تابع الإيقاف الخاص بالمورد
                        عند_الضغط.اربط(مغلفة (موسيقى: كسند)&(ودجة: سند[ودجـة], حمولة: سند[صحيح]) {
                            موسيقى.أوقف()؛
                        })؛
                    },
                    // زر لتشغيل الصوت
                    الـزر(نـص("شغل الصوت")).{
                        الطراز.{
                            الطول = مـسافة.نقاط(30)؛
                            العرض = مـسافة.نقاط(120)؛
                            الخلفية = خـلفية(لـون(200, 200, 200))؛
                            حجم_الخط = مـسافة.نقاط(16.0)؛
                        }؛
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الصوت
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نشغل الصوت لمرة واحدة فقط بما أننا مررنا قيمة خطأ للتكرار
                        عند_الضغط.اربط(مغلفة (صوت: كسند)&(ودجة: سند[ودجـة], حمولة: سند[صحيح]) {
                            صوت.شغل(0)؛
                        })؛
                    },
                    // زر للقيام بتشغيل الصوت بشكل مستمر
                    الـزر(نـص("شغل الصوت بتكرار")).{
                        الطراز.{
                            الطول = مـسافة.نقاط(30)؛
                            العرض = مـسافة.نقاط(150)؛
                            الخلفية = خـلفية(لـون(200, 200, 200))؛
                            حجم_الخط = مـسافة.نقاط(16.0)؛
                        }؛
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الصوت
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نمرر أننا نريد تشغيل بالصوت بشكل متكرر
                        عند_الضغط.اربط(مغلفة (صوت: كسند)&(ودجة: سند[ودجـة], حمولة: سند[صحيح]) {
                            صوت.شغل(1)؛
                        })؛
                    },
                    // تابع ﻷيقاف الصوت
                    الـزر(نـص("أوقف الصوت")).{
                        الطراز.{
                            الطول = مـسافة.نقاط(30)؛
                            العرض = مـسافة.نقاط(120)؛
                            الخلفية = خـلفية(لـون(200, 200, 200))؛
                            حجم_الخط = مـسافة.نقاط(16.0)؛
                        }؛
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بإيقاف الصوت
                        // و ذلك عبر استدعاء تابع الإيقاف الخاص بالمورد
                        عند_الضغط.اربط(مغلفة (صوت: كسند)&(ودجة: سند[ودجـة], حمولة: سند[صحيح]) {
                            صوت.أوقف()؛
                        })؛
                    }
                })؛
            }
            // نقوم بتعريف الودجة الخاصة بالمرسم
            مـرسم().{
                مرسم = هذا؛
                // نقوم بتحديد الطول و العرض
                عرض_الصورة = مـسافة.بكسلات(1280)؛
                طول_الصورة = مـسافة.بكسلات(800)؛
                // نقوم بتطبيق بعض الأطرزة على المرسم
                الطراز.{
                    العرض = مـسافة.مئوي(100)؛
                    الطول = مـسافة.مئوي(100)؛
                    أقصى_عرض = مـسافة.بكسلات(1280)؛
                    أقصى_طول = مـسافة.بكسلات(800)؛
                    سمك_الإطار = مـسافة4.نقاط(2)؛
                    طراز_الإطار = طـراز_إطار._مستمر_؛
                    لون_الإطار = لـون(0, 0, 0)؛
                    الخلفية = خـلفية(لـون(220, 220, 220))؛
                }؛
                عرف أبعاد: أبـعاد(1، 1)؛
                // نقوم بربط إشارة تحريك المؤشر بمغلف بحيث يتم استدعاءه
                // عند تحريك المؤشر لتحديث قيم الموقع
                عند_تحريك_المؤشر.اربط(
                    مغلفة (
                        موقع: كسند، أبعاد: كسند، المؤشر_محتكر: كسند
                    )&(
                        ودجة: سند[ودجـة]، حمولة: سند[حـمولة_تحريك_المؤشر]
                    ) {
                        إذا المؤشر_محتكر {
                            موقع.س += حمولة.إزاحة_س؛
                            موقع.ص += حمولة.إزاحة_ص؛
                        } وإلا {
                            موقع.س = حمولة.موقع_س * 1280 ÷ أبعاد.عرض؛
                            موقع.ص = حمولة.موقع_ص * 800 ÷ أبعاد.طول؛
                        }
                    }
                )؛
                // نقوم بربط إشارة دخول المؤشر بمغلف بحيث يتم استدعاءه
                // عند دخول المؤشر و ذلك لتغيير لون الإطار إلى قيمته الأصلية
                عند_دخول_المؤشر.اربط(مغلفة (ودجة: سند[ودجـة]، حمولة: سند[صحيح]) {
                    هذا.الطراز.لون_الإطار = لـون(0، 0، 0)؛
                })؛
                // نقوم بربط إشارة خروج المؤشر بمغلف بحيث يتم استدعاءه
                // عند خروج المؤشر و ذلك لتغيير لون الإطار إلى الأحمر لتوضيح أننا خارج المرسم
                عند_خروج_المؤشر.اربط(مغلفة (ودجة: سند[ودجـة]، حمولة: سند[صحيح]) {
                    هذا.الطراز.لون_الإطار = لـون(255، 0، 0)؛
                })؛
                // نقوم بربط إشارة بدء الضفط على المؤشر بمغلف بحيث يتم استدعاءه
                // عند بدء الضفط على المؤشر و ذلك لتغيير قيمة المتغير الخاص بتحديد فيما إذا تم
                // الضغط على المؤشر إلى القيمة المناسبة و ذلك فقط إذا تم الضغط على الزر الأيسر
                عند_بدء_النقرة.اربط(مغلفة (مضغوط: كسند)&(ودجة: سند[ودجـة]، حمولة: سند[حـمولة_زر_المؤشر]) {
                    إذا حمولة.الزر == 0 مضغوط = 1؛
                })؛
                // نقوم بربط إشارة نهاية الضفط على المؤشر بمغلف بحيث يتم استدعاءه
                // عند نهاية الضفط على المؤشر و ذلك لتغيير قيمة المتغير الخاص بتحديد فيما إذا تم
                // الضغط على المؤشر إلى القيمة المناسبة و ذلك فقط إذا تم إيقاف الضغط على الزر الأيسر
                عند_انتهاء_النقرة.اربط(مغلفة (مضغوط: كسند)&(ودجة: سند[ودجـة]، حمولة: سند[حـمولة_زر_المؤشر]) {
                    إذا حمولة.الزر == 0 مضغوط = 0؛
                })؛
                // نقوم بربط إشارة تغيير الحجم بمغلف بحيث يتم استدعاءه
                // عند تغيير الحجم و ذلك لتغيير الأبعاد فيما يتناسب مع تغير الحجم
                عند_تغير_الأبعاد.اربط(مغلفة (أبعاد: كسند)&(ودجة: سند[ودجـة]، حمولة: سند[صحيح]) {
                    أبعاد = هذا.هات_الأبعاد()؛
                })؛
            }
        })؛
    })؛

    // سنقوم فيما يلي بتعريف ما يلزم من أجل استعمال المقبض مع المرسم
    نـافذة.النموذج.{
        // المفاتيح التي نريدها هي الاتجاهات فقط
        المفاتيح_المكبوتة = "ArrowUp,ArrowDown,ArrowLeft,ArrowRight"؛
        // نقوم بربط إشارة بدء الضغط على المؤشر بمؤجل يقوم عند استدعاءه
        // بتحديد التغير في الموقع بناء على الزر المضغوط
        عند_بدء_الكبسة.اربط(مغلفة (
            تغير: كسند، المؤشر_محتكر: كسند، ملء_الشاشة: كسند
        )&(
            نافذة: سند[نـافذة]، حمولة: سند[نـص]
        ) {
            إذا حمولة == "ArrowUp" تغير.ص = -5
            وإلا إذا حمولة == "ArrowDown" تغير.ص = 5
            وإلا إذا حمولة == "ArrowRight" تغير.س = 5
            وإلا إذا حمولة == "ArrowLeft" تغير.س = -5
            // كما يقوم هنا بالدخول إلى وضع ملء الشاشة أو الخروج منه
            وإلا إذا حمولة == "Enter" {
                إذا ملء_الشاشة ألغ_ملء_الشاشة()
                وإلا مرسم.التمس_ملء_الشاشة()؛
            }
            // أيضاً نقوم بطلب قفل المؤشر أو الخروج منه
            وإلا إذا حمولة == "Space" {
                إذا المؤشر_محتكر ألغ_احتكار_المؤشر()
                وإلا مرسم.التمس_احتكار_المؤشر()؛
            }
        })؛
        // عند توقف الضغط على المؤشر نقوم بتصفير قيم الحركة
        عند_انتهاء_الكبسة.اربط(مغلفة (تغير: كسند)&(نافذة: سند[نـافذة]، حمولة: سند[نـص]) {
            إذا حمولة == "ArrowUp" تغير.ص = 0
            وإلا إذا حمولة == "ArrowDown" تغير.ص = 0
            وإلا إذا حمولة == "ArrowRight" تغير.س = 0
            وإلا إذا حمولة == "ArrowLeft" تغير.س = 0؛
        })؛
        // نقوم بربط إشارة قفل المؤشر بمؤجل عند تنفيذه يتم تحديث قيمة المتغير الذي نحدد
        // ضمنه فيما إذا كنا في وضع غلق المؤشر أم لا
        عند_تغير_احتكار_المؤشر.اربط(مغلفة (المؤشر_محتكر: كسند)&(نافذة: سند[نـافذة]، حمولة: سند[ثـنائي]) {
            المؤشر_محتكر = حمولة؛
        })؛
        // نقوم بربط إشارة تغير وضع ملء الشاشة بمؤجل عند تنفيذه يتم تحديث قيمة المتغير
        // الذي نخزن ضمنه فيما إذا كنا في وضع ملء الشاشة أم لا
        // كما أننا نقوم بقفل المؤشر عند الدخول في وضع ملء الشاشة و الخروج منه عكس ذلك
        عند_تغير_ملء_الشاشة.اربط(مغلفة (ملء_الشاشة: كسند)&(نافذة: سند[نـافذة]، حمولة: سند[ثـنائي]) {
            ملء_الشاشة = حمولة؛
            إذا حمولة مرسم.التمس_احتكار_المؤشر()
            وإلا ألغ_احتكار_المؤشر()؛
        })؛
        // نقوم بربط إشارات ربط المقيض و فصله بمؤجل عند تنفيذ يتم تحديث
        // قيمة المتغير الذي يخزن عدد المقابض الحالية
        عند_ربط_مقبض.اربط(مغلفة (عدد_المقابض: كسند)&(نافذة: سند[نـافذة]، حمولة: سند[نـص]) {
            عدد_المقابض = هات_عدد_المقابض()؛
        })؛
        عند_فصل_مقبض.اربط(مغلفة (عدد_المقابض: كسند)&(نافذة: سند[نـافذة]، حمولة: سند[نـص]) {
            عدد_المقابض = هات_عدد_المقابض()؛
        })؛
    }؛

    // توليد صورة بشكل ديناميكي
    // مورد الصورة
    عرف صورة_ديناميكية: مـورد_صورة؛
    // المرسم الذي سنرسم عليه
    عرف مورد_مرسم: مـورد_مرسم(100, 100)؛
    مورد_مرسم.حدد_عرض_القلم(5)؛
    مورد_مرسم.حدد_نمط_القلم("#ff5555")؛
    // نقوم برسم خطين على المرسم
    مورد_مرسم.ارسم_خطا(0, 0, 100, 100)؛
    مورد_مرسم.ارسم_خطا(100, 0, 0, 100)؛
    // نقوم برسم مضلع على المرسم
    عرف نقاط: مـصفوفة[صحيح]({ 25, 25, 75, 25, 75, 75, 25, 75 })؛
    مورد_مرسم.ارسم_مضلعا(4, نقاط.صوان, 0)؛
    // نقوم بتحميل الصورة من المرسم
    صورة_ديناميكية.هيئ_من_مرسم(مورد_مرسم)؛

    // حلقة التحريك
    عرف س: صحيح = -80؛
    // نبدأ مؤقت يقوم بتنفيذ ما نريد كل 8 ثواني
    ابدأ_المؤقت_المتكرر(8000, مغلفة (
        س: كسند, صورة: كسند, صورة_ديناميكية: كسند، موقع: كسند، تغير: كسند، مضغوط: كسند، عدد_المقابض: كسند
    ) & (جسون: جـيسون) {
        // في كل مرة نقوم بمحو الرسومات للبدء من جديد
        مرسم.فرغ()؛
        // نرسم خط
        مرسم.ارسم_خطا(0,0, 100,100)؛
        // نرسم دائرة
        مرسم.ارسم_دائرة(100,180, 90)؛
        // نقوم برسم مضلع
        عرف نقاط: مـصفوفة [صحيح]({ 50, 50, 100, 50, 100, 100, 50, 100, 25, 75 })؛
        مرسم.حدد_نمط_الملء("black", "blue", 0, 0, 100, 100)؛
        مرسم.ارسم_مضلعا(5, نقاط.صوان, 1)؛
        // نرسم نص
        عرف _كتابة_: "الأسس"؛
        مرسم.ارسم_كتابة(_كتابة_, _خط_الكتابة_, 550, 150)؛

        عرف حجم: صحيح = ريـاضيات.جا(3.14 * س / 320.0) * 40 + 100؛
        عرف ص1: صحيح = ريـاضيات.جا(3.14 * س / 320.0) * 100 + 400 - حجم / 2؛
        عرف ص2: صحيح = ريـاضيات.جتا(3.14 * س / 320.0) * 100 + 400 - حجم / 2؛
        عرف شفافية: عائم = ريـاضيات.جا(3.14 * س / 80.0) / 4 + 0.75؛
        مرسم.ارسم_صورة(صورة, س, ص1, حجم, حجم, شفافية)؛
        مرسم.ارسم_صورة(صورة_ديناميكية, س, ص2, حجم, حجم, شفافية)؛

        // في كل مرة في حال كان لدينا مقابض نقوم بجلب الحركة التي تمت بواسطتها
        // و نقوم بالتحريك كما يلزم
        إذا عدد_المقابض > 0 {
            تغير.س = هات_قيمة_محور_المقبض(0، 0) * 5؛
            تغير.ص = هات_قيمة_محور_المقبض(0، 1) * 5؛
            مضغوط = هات_قيمة_زر_المقبض(0، 0) > 0.5؛
        }

        إذا مضغوط مرسم.ارسم_صورة(صورة, موقع.س, موقع.ص, حجم, حجم, شفافية)
        وإلا مرسم.ارسم_صورة(صورة_ديناميكية, موقع.س, موقع.ص, حجم, حجم, شفافية)؛
        إذا ++س >= 1280 س = -80؛
        موقع.س += تغير.س؛
        موقع.ص += تغير.ص؛
    })؛

    نفذ_حلقة_معالجة_الأحداث()؛
}


طـرفية.اطبع("تشغيل الخادم على المنفذ 8010...\nURL: http://localhost:8010/\n")؛
// نبدأ تشغيل السيرفر على المنفذ 8010
ابن_وشغل_الخادم(مـصفوفة[مـؤشر_محارف]({ "listening_ports"، "8010"، "static_file_max_age"، "0" }))؛
```

</div>

```
import "Srl/Math";
import "Apm";
Apm.importFile("Alusus/WebPlatform");
use Srl;
use WebPlatform;

//==============================================================================
// Backend

// نقوم بتعريف المسار الذي سنخزن عليه الموارد
@assetsRoute def assetsRoute: "Assets/";

//==============================================================================
// Frontend

def PRIMARY_COLOR: Color("8e50ef");

// دالة لإنشاء ودجة الترويسة
func createHeader (): SrdRef[Widget] {
    // هنا نقوم بإنشاء مساحة مستطيلة لوضع مكونات الودجة ضمنها
    return Box({}).{
        // الأطرزة المستعملة لهذه الودجة
        style.{
            width = Length.percent(100);
            height = Length.pt(40);
            padding = Length4.pt(5, 0);
            background = Background(PRIMARY_COLOR);
            borderColor = PRIMARY_COLOR;
            borderWidth = Length4.pt(1.5);
            borderStyle = BorderStyle.SOLID;
            display = Display.FLEX;
            layout = Layout.COLUMN;
        };
        // مكونات الودجة و التي نعتبرها فروع للودجة
        addChildren({
            // هنا سيكون لدينا فقط نص يوضح أننا ننشأ مثال عن المرسم
            Text(String("Alusus Web Platform Examples - Canvas")).{ style.{
                fontColor = Color("fff");
                fontSize = Length.pt(21.0);
                width = Length.percent(100);
                height = Length.percent(100);
                background = Background(PRIMARY_COLOR);
                margin = Length4.pt(5, 15);
            } },
        });
    }~cast[SrdRef[Widget]];
}

// صنف لنضع ضمنه معلومات الموقع ضمن الشاشة على شكل إحداثيات
class Position {
    def x: Int;
    def y: Int;
}

// منفذ بياني لموقع الويب خاصتنا
// هنا نحدد أولاً المسار و سيكون لدينا الجذر هنا
// و ثانياً نضع العنوان الخاص بهذا المنفذ البياني
@uiEndpoint["/", "WebPlatform Example - Canvas"]
func main {
    // سنقوم هنا بتحميل الموارد من السيرفر
    // في البداية نقوم بتعريف مورد من أجل كل نوع موارد نريده
    def img: ImageResource;  // مورد للصورة
    def music: AudioResource;  // مورد للصوت
    def sound: AudioResource;  // مورد للصوت
    // نقوم بتحميل الموارد بشكل لامتزامن
    await(Promises.Promise[Int].all({
        // لتحميل الصورة يكفي استدعاء تابع التحميل مع مسار الصورة
        img.load("Assets/logo.svg"),
        // نقوم بتحميل الخط عن طريق اسم الخط و المسار الخاص به
        loadFont("AlususMono", "Assets/AlususMono.otf"),
        // أيضاً لتحميل الصوت يكفي استدعاء تابع التحميل مع مسار الملف الصوتي
        music.load("Assets/music.mp3"),
        sound.load("Assets/sound.mp3")
    }).ignoreResult());

    // نقوم بتعريف بعض المتغيرات التي سنحتاجها تالياً
    // متغير لتخزين الموقع
    def pos: Position;
    pos.x = 200;
    pos.y = 150;
    // متغير لتخزين الحركة
    def delta: Position;
    delta.x = delta.y = 0;
    // متغير لتخزين فيما إذا تم الضغط على المؤشر أم لا
    def pressed: Bool = 0;
    // متغير لتخزين فيما إذا قد تم قفل المؤشر أم لا
    def pointerLocked: Bool = false;
    // متغير لتحديد فيما إذا كنا في وضع ملء الشاشة أم لا
    def fullscreen: Bool = false;
    // متغير لتخزين عدد المقابض
    def gamepadsCount: Int = 0;

    // بناء المشهد
    def canvas: SrdRef[Canvas];
    // نقوم بتطبيق بعض الأطرزة على النافذة
    // هنا مثلاً طبقنا أننا لا نريد حشو أو هوامش
    Window.instance.style.{
        padding = Length4.pt(0);
        margin = Length4.pt(0);
    };
    // نقوم بتحديد المشهد الخاص بالنافذة
    Window.instance.setView(Box({}).{
        // بعض الأطرزة لتطبيقها على المساحة المربعة التي سنعرف ضمنها المرسم
        // و الأدوات الخاصة به
        style.{
            align = Align.CENTER;
            display = Display.FLEX;
            layout = Layout.COLUMN;
        };
        addChildren({
            // نقوم بإضافة الترويسة التي عرفنا دالة إضافتها سابقاً.
            createHeader(),
            // مساحة مربعة أخرى لإضافة بعض الخيارات الخاصة بالصوت
            Box({}).{
                style.display = Display.FLEX;
                style.layout = Layout.ROW;
                addChildren({
                    // زر لتشغيل الموسيقى
                    Button(String("Play Music")).{
                        style.{
                            height = Length.pt(30);
                            width = Length.pt(120);
                            background = Background(Color(200, 200, 200));
                            fontSize = Length.pt(16.0);
                        };
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الموسيقى
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نمرر أننا نريد تشغيل بالموسيقى بشكل متكرر
                        onClick.connect(closure (music: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                            music.play(true);
                        });
                    },
                    // زر لإيقاف تشغيل الموسيقى
                    Button(String("Stop Music")).{
                        style.{
                            height = Length.pt(30);
                            width = Length.pt(120);
                            background = Background(Color(200, 200, 200));
                            fontSize = Length.pt(16.0);
                        };
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بإيقاف الموسيقى
                        // و ذلك عبر استدعاء تابع الإيقاف الخاص بالمورد
                        onClick.connect(closure (music: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                            music.stop();
                        });
                    },
                    // زر لتشغيل الصوت
                    Button(String("Play Sound")).{
                        style.{
                            height = Length.pt(30);
                            width = Length.pt(120);
                            background = Background(Color(200, 200, 200));
                            fontSize = Length.pt(16.0);
                        };
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الصوت
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نشغل الصوت لمرة واحدة فقط بما أننا مررنا قيمة خطأ للتكرار
                        onClick.connect(closure (sound: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                            sound.play(false);
                        });
                    },
                    // زر للقيام بتشغيل الصوت بشكل مستمر
                    Button(String("Play Repeating Sound")).{
                        style.{
                            height = Length.pt(30);
                            width = Length.pt(180);
                            background = Background(Color(200, 200, 200));
                            fontSize = Length.pt(16.0);
                        };
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بتشغيل الصوت
                        // و ذلك عبر استدعاء تابع التشغيل الخاص بالمورد
                        // نلاحظ هنا أننا نمرر أننا نريد تشغيل بالصوت بشكل متكرر
                        onClick.connect(closure (sound: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                            sound.play(true);
                        });
                    },
                    // تابع ﻷيقاف الصوت
                    Button(String("Stop Sound")).{
                        style.{
                            height = Length.pt(30);
                            width = Length.pt(120);
                            background = Background(Color(200, 200, 200));
                            fontSize = Length.pt(16.0);
                        };
                        // نقوم هنا بربط إشارة الضفط على هذا الزر بتابع يقوم بإيقاف الصوت
                        // و ذلك عبر استدعاء تابع الإيقاف الخاص بالمورد
                        onClick.connect(closure (sound: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                            sound.stop();
                        });
                    }
                });
            }
            // نقوم بتعريف الودجة الخاصة بالمرسم
            Canvas().{
                canvas = this;
                // نقوم بتحديد الطول و العرض
                bitmapWidth = Length.px(1280);
                bitmapHeight = Length.px(800);
                // نقوم بتطبيق بعض الأطرزة على المرسم
                style.{
                    width = Length.percent(100);
                    height = Length.percent(100);
                    maxWidth = Length.px(1280);
                    maxHeight = Length.px(800);
                    borderWidth = Length4.pt(2);
                    borderStyle = BorderStyle.SOLID;
                    borderColor = Color(0, 0, 0);
                    background = Background(Color(220, 220, 220));
                };
                def dim: Dimensions(1, 1);
                // نقوم بربط إشارة تحريك المؤشر بمغلف بحيث يتم استدعاءه
                // عند تحريك المؤشر لتحديث قيم الموقع
                onMouseMove.connect(closure (
                    pos: by_ref, dim: by_ref, pointerLocked: by_ref
                )&(
                    widget: ref[Widget], payload: ref[MouseMovePayload]
                ) {
                    if pointerLocked {
                        pos.x += payload.deltaX;
                        pos.y += payload.deltaY;
                    } else {
                        pos.x = payload.posX * 1280 / dim.width;
                        pos.y = payload.posY * 800 / dim.height;
                    }
                });
                // نقوم بربط إشارة دخول المؤشر بمغلف بحيث يتم استدعاءه
                // عند دخول المؤشر و ذلك لتغيير لون الإطار إلى قيمته الأصلية
                onMouseEnter.connect(closure (widget: ref[Widget], payload: ref[Int]) {
                    this.style.borderColor = Color(0, 0, 0);
                });
                // نقوم بربط إشارة خروج المؤشر بمغلف بحيث يتم استدعاءه
                // عند خروج المؤشر و ذلك لتغيير لون الإطار إلى الأحمر لتوضيح أننا خارج المرسم
                onMouseOut.connect(closure (widget: ref[Widget], payload: ref[Int]) {
                    this.style.borderColor = Color(255, 0, 0);
                });
                // نقوم بربط إشارة بدء الضفط على المؤشر بمغلف بحيث يتم استدعاءه
                // عند بدء الضفط على المؤشر و ذلك لتغيير قيمة المتغير الخاص بتحديد فيما إذا تم
                // الضغط على المؤشر إلى القيمة المناسبة و ذلك فقط إذا تم الضغط على الزر الأيسر
                onMouseDown.connect(closure (pressed: by_ref)&(widget: ref[Widget], payload: ref[MouseButtonPayload]) {
                    if payload.button == 0 pressed = 1;
                });
                // نقوم بربط إشارة نهاية الضفط على المؤشر بمغلف بحيث يتم استدعاءه
                // عند نهاية الضفط على المؤشر و ذلك لتغيير قيمة المتغير الخاص بتحديد فيما إذا تم
                // الضغط على المؤشر إلى القيمة المناسبة و ذلك فقط إذا تم إيقاف الضغط على الزر الأيسر
                onMouseUp.connect(closure (pressed: by_ref)&(widget: ref[Widget], payload: ref[MouseButtonPayload]) {
                    if payload.button == 0 pressed = 0;
                });
                // نقوم بربط إشارة تغيير الحجم بمغلف بحيث يتم استدعاءه
                // عند تغيير الحجم و ذلك لتغيير الأبعاد فيما يتناسب مع تغير الحجم
                onResize.connect(closure (dim: by_ref)&(widget: ref[Widget], payload: ref[Int]) {
                    dim = this.getDimensions();
                });
            }
        });
    });

    // سنقوم فيما يلي بتعريف ما يلزم من أجل استعمال المقبض مع المرسم
    Window.instance.{
        // المفاتيح التي نريدها هي الاتجاهات فقط
        keysToSwallow = "ArrowUp,ArrowDown,ArrowLeft,ArrowRight";
        // نقوم بربط إشارة بدء الضغط على المؤشر بمؤجل يقوم عند استدعاءه
        // بتحديد التغير في الموقع بناء على الزر المضغوط
        onKeyDown.connect(closure (
            delta: by_ref, pointerLocked: by_ref, fullscreen: by_ref
        )&(
            window: ref[Window], payload: ref[String]
        ) {
            if payload == "ArrowUp" delta.y = -5
            else if payload == "ArrowDown" delta.y = 5
            else if payload == "ArrowRight" delta.x = 5
            else if payload == "ArrowLeft" delta.x = -5
            // كما يقوم هنا بالدخول إلى وضع ملء الشاشة أو الخروج منه
            else if payload == "Enter" {
                if fullscreen exitFullScreen()
                else canvas.requestFullScreen();
            }
            // أيضاً نقوم بطلب قفل المؤشر أو الخروج منه
            else if payload == "Space" {
                if pointerLocked exitPointerLock()
                else canvas.requestPointerLock();
            }
        });
        // عند توقف الضغط على المؤشر نقوم بتصفير قيم الحركة
        onKeyUp.connect(closure (delta: by_ref)&(window: ref[Window], payload: ref[String]) {
            if payload == "ArrowUp" delta.y = 0
            else if payload == "ArrowDown" delta.y = 0
            else if payload == "ArrowRight" delta.x = 0
            else if payload == "ArrowLeft" delta.x = 0;
        });
        // نقوم بربط إشارة قفل المؤشر بمؤجل عند تنفيذه يتم تحديث قيمة المتغير الذي نحدد
        // ضمنه فيما إذا كنا في وضع غلق المؤشر أم لا
        onPointerLockChange.connect(closure (pointerLocked: by_ref)&(window: ref[Window], payload: ref[Bool]) {
            pointerLocked = payload;
        });
        // نقوم بربط إشارة تغير وضع ملء الشاشة بمؤجل عند تنفيذه يتم تحديث قيمة المتغير
        // الذي نخزن ضمنه فيما إذا كنا في وضع ملء الشاشة أم لا
        // كما أننا نقوم بقفل المؤشر عند الدخول في وضع ملء الشاشة و الخروج منه عكس ذلك
        onFullScreenChange.connect(closure (fullscreen: by_ref)&(window: ref[Window], payload: ref[Bool]) {
            fullscreen = payload;
            if payload canvas.requestPointerLock()
            else exitPointerLock();
        });
        // نقوم بربط إشارات ربط المقيض و فصله بمؤجل عند تنفيذ يتم تحديث
        // قيمة المتغير الذي يخزن عدد المقابض الحالية
        onGamepadConnected.connect(closure (gamepadsCount: by_ref)&(window: ref[Window], payload: ref[String]) {
            gamepadsCount = getGamepadsCount();
        });
        onGamepadDisconnected.connect(closure (gamepadsCount: by_ref)&(window: ref[Window], payload: ref[String]) {
            gamepadsCount = getGamepadsCount();
        });
    };

    // توليد صورة بشكل ديناميكي
    def dynImg: ImageResource;  // مورد الصورة
    def canvasRes: CanvasResource(100, 100);  // المرسم الذي سنرسم عليه
    canvasRes.setLineWidth(5);
    canvasRes.setStrokeStyle("#ff5555");
    // نقوم برسم خطين على المرسم
    canvasRes.drawLine(0, 0, 100, 100);
    canvasRes.drawLine(100, 0, 0, 100);
    // نقوم برسم مضلع على المرسم
    def points: Array [Int]({ 25, 25, 75, 25, 75, 75, 25, 75 });
    canvasRes.drawPolygon(4, points.buf, false);
    // نقوم بتحميل الصورة من المرسم
    dynImg.initFromCanvas(canvasRes);

    // حلقة التحريك
    def x: Int = -80;
    // نبدأ مؤقت يقوم بتنفيذ ما نريد كل 8 ثواني
    startTimer(8000000, closure (
        x: by_ref, img: by_ref, dynImg: by_ref, pos: by_ref, delta: by_ref, pressed: by_ref, gamepadsCount: by_ref
    ) & (json: Json) {
        // في كل مرة نقوم بمحو الرسومات للبدء من جديد
        canvas.clear();
        canvas.drawLine(0, 0, 100, 100);  // نرسم خط
        canvas.drawCircle(100, 180, 90);  // نرسم دائرة
        // نقوم برسم مضلع
        def points: Array [Int]({ 50, 50, 100, 50, 100, 100, 50, 100, 25, 75 });
        canvas.setFillStyle("black", "blue", 0, 0, 100, 100);
        canvas.drawPolygon(5, points.buf, true);
        // نرسم نص
        def TEXT: "Alusus";
        canvas.drawText(TEXT, "30px AlususMono", 550, 150);

        def size: Int = Math.sin(3.14 * x / 320.0) * 40 + 100;
        def y1: Int = Math.sin(3.14 * x / 320.0) * 100 + 400 - size / 2;
        def y2: Int = Math.cos(3.14 * x / 320.0) * 100 + 400 - size / 2;
        def alpha: Float = Math.sin(3.14 * x / 80.0) / 4 + 0.75;
        canvas.drawImage(img, x, y1, size, size, alpha);
        canvas.drawImage(dynImg, x, y2, size, size, alpha);

        // في كل مرة في حال كان لدينا مقابض نقوم بجلب الحركة التي تمت بواسطتها
        // و نقوم بالتحريك كما يلزم
        if gamepadsCount > 0 {
            delta.x = getGamepadAxis(0, 0) * 5;
            delta.y = getGamepadAxis(0, 1) * 5;
            pressed = getGamepadButton(0, 0) > 0.5;
        }

        if pressed canvas.drawImage(img, pos.x, pos.y, size, size, alpha)
        else canvas.drawImage(dynImg, pos.x, pos.y, size, size, alpha);
        if ++x >= 1280 x = -80;
        pos.x += delta.x;
        pos.y += delta.y;
    });

    runEventLoop();
}


Console.print("Starting server on port 8010...\nURL: http://localhost:8010/\n");
// نبدأ تشغيل السيرفر على المنفذ 8010
buildAndRunServer(Array[CharsPtr]({ "listening_ports", "8010", "static_file_max_age", "0" }));
```

