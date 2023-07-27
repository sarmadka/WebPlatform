# WebPlatform

[[English]](styling.en.md)

[[رجوع]](../readme.ar.md)

## الطرز (Styling)

الطرز تسمح للمستخدم بالتحكم بمظهر واجهة المستخدم عبر التحكم بالخصائص المظهرية للودجات.

### طـراز (Style)

الصنف الرئيسي للتحكم بالخصائص المظهرية لودجة معينة في حالة معينة. تتوفر فيه الخصائص التالية:

<div dir=rtl>

```
طراز_الإطار: طـراز_إطار
طراز_الآوتلاين: طـراز_إطار
الطوفان: طـوفان
الموقع: مـوقع
النسق: نـسق
ملء_السطر: مـلئ_سطر
المحاذاة: مـحاذاة
محاذاة_النص: مـحاذاة_نص
زخرفة_النص: زخـرفة_نص
طراز_زخرفة_النص: طـراز_زخرفة_نص
الاتجاه: اتـجاه
فئة_الخط: نـص
الفيض_س: فـيض
الفيض_ص: فـيض
الإظهار: إظـهار
المؤشر: مـؤشر
التحريك: تـحريك
تقطيع_الكلمات: تـقطيع_كلمات
العرض: مـسافة
الطول: مـسافة
أدنى_عرض: مـسافة
أدنى_طول: مـسافة
أقصى_عرض: مـسافة
أقصى_طول: مـسافة
سمك_الإطار: مـسافة4
لون_الإطار: لـون
نصف_قطر_الإطار: مـسافة4
سمك_الآوتلاين: مـسافة4
إزاحة_الآوتلاين: مـسافة4
لون_الآوتلاين: لـون
تسلسل_العمق: صـحيح
المرونة: مـرونة
الهامش: مـسافة4
لون_زخرفة_النص: لـون
سمك_زخرفة_النص: مـسافة
الحشوة: مـسافة4
حجم_الخط: مـسافة
لون_الخط: لـون
سمك_الخط: مـسافة
ارتفاع_الكتابة: مـسافة
الشفافية: صـحيح
التحول: تـحول
ظل_الصندوق: ظـل
فوق: مـسافة
يسار: مـسافة
يمين: مـسافة
تحت: مـسافة
الخلفية: خـلفية
```

</div>

```
borderStyle: BorderStyle
outlineStyle: BorderStyle
float: Floating
position: Position
flexDirection: Layout
justifyContent: Justify
alignItems: Align
textAlign: TextAlign
textDecoration: TextDecoration
textDecorationstyle": TextDecorationStyle
direction: Direction
fontFamily: String
overflowX: Overflow
overflowY: Overflow
display: Display
cursor: Cursor
animation: Animation
wordBreak: WordBreak
width: Length
height: Length
minWidth: Length
minHeight: Length
maxWidth: Length
maxHeight: Length
borderWidth: Length4
borderColor: Color
borderRadius: Length4
outlineWidth: Length4
outlineOffset: Length4
outlineColor: Color
zIndex: Int
flex: Flex
margin: Length4
textDecorationColor: Color
textDecorationThickness: Length
padding: Length4
fontSize: Length
color: Color
fontWeight: Length
lineHeight: Length
opacity: Int
transform: Transform
boxShadow: Shadow
top: Length
left: Length
right: Length
bottom: Length
background: Background
```

فيما يلي هدف كل طرز، ويمكن إيجاد القيم في شروح كل صنف من أصناف الطرز.

* `طراز_الإطار` (`borderStyle`) الطرز الخاص بالإطار.
* `طراز_الآوتلاين` (`outlineStyle`) الطرز الخاص بالخط الذي يرسم خارج الإطار وحوله. يستخدم مع ودجات
  الإدخال.
* `الطوفان` (`floating`) تحديد كيفية طوفان العنصر ضمن الصندوق الحاوي.
* `الموقع` (`position`) تحديد طرز موقع العنصر.
* `النسق` (`layout`) تحديد النسق المتبع للعنصر عند استخدام نمط الإظهار `_مرن_` (`FLEX`).
* `ملء_السطر` (`justify`) الطرز الخاص بكيفية توزع العناصر ضمن السطر.
* `المحاذاة` (`align`) الطرز الخاص بمحاذاة العنصر ضمن العنصر الذي يحتويه.
* `محاذاة_النص` (`textAlign`) الطرز الخاص بمحاذاة النص ضمن العنصر الذي يحتويه.
* `زخرفة_النص` (`textDecoration`) الطرز الخاص بكيفية زخرفة النص.
* `طراز_زخرفة_النص` (`textDecorationStyle`) الطرز الخاص بشكل الزخرفة الخاصة بالنص.
* `الاتجاه` (`direction`) الاتجاه الخاص بالعنصر.
* `فئة_الخط` (`fontFamily`) فئة الخط الذي يتبع إليها النص.
* `الفيض_س` (`overflowX`) الفيض على محور س.
* `الفيض_ص` (`overflowY`) الفيض على محور ص.
* `الإظهار` (`display`) طريقة عرض العنصر.
* `المؤشر` (`cursor`) الطرز الخاص بالمؤشر.
* `التحريك` (`animation`) التحريكات التي نريد تطبيقها على العنصر.
* `تقطيع_الكلمات` (`wordBreak`)  كيف يجب للكلمات أن تقطع في حال وصلت حدود الإطار.
* `العرض` (`width`) عرض العنصر.
* `الطول` (`height`) طول العنصر.
* `أدنى_عرض` (`minWidth`) أدنى عرض مسموح للعنصر.
* `أدنى_طول` (`minHeight`) أدنى طول مسموح للعنصر.
* `أقصى_عرض` (`maxWidth`) أقصى عرض مسموح للعنصر.
* `أقصى_طول` (`maxHeight`) أقصى طول مسموح للعنصر.
* `سمك_الإطار` (`borderWidth`) سمك الإطار.
* `لون_الإطار` (`borderColor`) لون الإطار.
* `نصف_قطر_الإطار` (`borderRadius`) نصف قطر الإطار، لتنعيم زوايا الإطار (أي يصبح شكلها منحني قليلاً).
* `سمك_الآوتلاين` (`outlineWidth`) سمك الخط حول الإطار.
* `إزاحة_الآوتلاين` (`outlineOffset`) إزاحة الخط حول الإطار عن الإطار ذاته.
* `لون_الآوتلاين` (`outlineColor`) لون الخط حول الإطار.
* `تسلسل_العمق` (`zIndex`) تفيد هذه الخاصية في ترتيب العناصر عند توضعها فوق بعضها.
* `المرونة` (`flex`) الطرز الخاص بالمرونة و التي تحدد نسق لتوضع العناصر.
* `الهامش` (`margin`) الهامش حول العنصر.
* `لون_زخرفة_النص` (`textDecorationColor`) اللون الخاص بالزخرفة للنص.
* `سمك_زخرفة_النص` (`textDecorationThickness`) سمك زخرفة النص.
* `الحشوة` (`padding`) الحشو للعنصر.
* `حجم_الخط` (`fontSize`) حجم الخط.
* `لون_الخط` (`fontColor`) لون الخط.
* `سمك_الخط` (`fontWeight`) سمك الخط.
* `ارتفاع_الكتابة` (`lineHeight`) ارتفاع السطر، هذا يفيد في زيادة أو تقليل المسافة بين الأسطر.
* `الشفافية` (`opacity`) شفافية العنصر.
* `التحول` (`transform`) التحويلات المطبقة على العنصر.
* `ظل_الصندوق` (`boxShadow`) الظل الخاص بالصندوق الذي يحوي العنصر.
* `فوق` (`top`) بعد العنصر عن أعلى العنصر الحاوي له أو الشاشة (تبعاً للخاصية `موقع`).
* `يسار` (`left`) بعد العنصر عن يسار العنصر الحاوي له أو الشاشة (تبعاً للخاصية `موقع`).
* `يمين` (`right`) بعد العنصر عن يمين العنصر الحاوي له أو الشاشة (تبعاً للخاصية `موقع`).
* `تحت` (`bottom`) بعد العنصر عن أسفل العنصر الحاوي له أو الشاشة (تبعاً للخاصية `موقع`).
* `الخلفية` (`background`) خلفية العنصر.


### طـقم_طرز (StyleSet)

يمكن هذا الصنف المستخدم من تحديد عدة طرز للودجة في حالات مختلفة، كما يسمح بتحديد طرز فروع تلك الودجة
وهذا يمكن المبرمج من التحكم بشكل الودجة المبدئي وشكلها عند تغير حالتها (مثلا عند تمرير الفأرة فوقها)
كما تسمح بالتحكم بشكل فروع تلك الودجة عند تغير حالتها. الودجات لا تتعامل مباشرة مع الصنف `طـراز`
وإنما تتعامل مع `طـقم_طرز` بدلًا من ذلك.

#### تطبيق الطرز على عنصر

يمكن تطبيق طرز على عنصر عن طريق الخاصية `الطراز` و التي نضع ضمنها الطرز الذي نريد تطبيقه.

مثال على ذلك:

<div dir=rtl>

```
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
```

</div>

```
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
```

هنا كما نرى نقوم بكتابة دالة لإنشاء عنصر و تطبيق طرز عليه.

داخل الطرز نقوم بوضع قيم كل خاصية نريدها، مثلاً قمنا بتحديد العرض على أنه 100 كنسبة مئوية.

#### تطبيق الطرز على عنصر في حالة معينة

يمكن القيام بذلك بتمرير محدد الحالة إلى `الطراز` لتحديد الحالة التي نريد فيها لذلك الطراز أن يُطبق.
على سبيل المثال:

<div dir=rtl>

```
صـندوق({}).{
    // نطبق بعض الأطرزة
    الطراز.{
        الخلفية = خـلفية(_لون_فاتح_)؛
    }؛
    // نغير لون الخلفية عند مرور المؤشر فوق الصندوق.
    الطراز(مـحدد_حالة._حوم_).{
        الخلفية = خـلفية(_لون_داكن_)؛
    }
}
```

</div>

```
Box({}).{
    // نطبق بعض الأطرزة
    style.{
        background = Background(LIGHT_COLOR);
    };
    // نغير لون الخلفية عند مرور المؤشر فوق الصندوق.
    style(StateSelector.HOVER).{
        background = Background(DARK_COLOR);
    }
}
```

تتوفر الحالات التالية التي يمكن استخدامها، وهذه الحالات تطابق الحالات المستخدمة في CSS:

<div dir=rtl>

```
عرف مـحدد_حالة: {
    عرف _فعال_: ":active"؛
    عرف _معلم_: ":checked"؛
    عرف _مبدئي_: ":default"؛
    عرف _معطل_: ":disabled"؛
    عرف _فارغ_: ":empty"؛
    عرف _ممكن_: ":enabled"؛
    عرف _بؤرة_: ":focus"؛
    عرف _ملء_الشاشة_: ":fullscreen"؛
    عرف _حوم_: ":hover"؛
    عرف _ضمن_النطاق_: ":in-range"؛
    عرف _وسطي_: ":indeterminate"؛
    عرف _باطل_: ":invalid"؛
    عرف _رابط_: ":link"؛
    عرف _اختياري_: ":optional"؛
    عرف _خارج_النطاق_: ":out-of-range"؛
    عرف _قراءة_فقط_: ":read-only"؛
    عرف _قراءة_وكتابة_: ":read-write"؛
    عرف _إلزامي_: ":required"؛
    عرف _مستهدف_: ":target"؛
    عرف _صالح_: ":valid"؛
    عرف _مزار_: ":visited"؛
}
```

</div>

```
def StateSelector: {
    def ACTIVE: ":active";
    def CHECKED: ":checked";
    def DEFAULT: ":default";
    def DISABLED: ":disabled";
    def EMPTY: ":empty";
    def ENABLED: ":enabled";
    def FOCUS: ":focus";
    def FULLSCREEN: ":fullscreen";
    def HOVER: ":hover";
    def IN_RANGE: ":in-range";
    def INTERMEDIATE: ":indeterminate";
    def INVALID: ":invalid";
    def LINK: ":link";
    def OPTIONAL: ":optional";
    def OUT_OF_RANGE: ":out-of-range";
    def READ_ONLY: ":read-only";
    def READ_WRITE: ":read-write";
    def REQUIRED: ":required";
    def TARGET: ":target";
    def VALID: ":valid";
    def VISITED: ":visited";
}
```

* `_فعال_` (`ACTIVE`) حالة كون العنصر فعال.
* `_معلم_` (`CHECKED`) حال كون العنصر معلم، مثل صندوق التعليم عندما نعلمه.
* `_مبدئي_` (`DEFAULT`) الحالة الافتراضية.
* `_معطل_` (`DISABLED`) حالة كون العنصر معطل، أي عكس الحالة `_فعال_`.
* `_فارغ_` (`EMPTY`) حالة كون العنصر فارغ، مثل مربع نص.
* `_ممكن_` (`ENABLED`) حالة كون العنصر ممكن.
* `_بؤرة_` (`FOCUS`) حالة كون البؤرة على العنصر، أي مثلاً عندما نضعط على مربع نص تصبح البؤرة عليه.
* `_ملء_الشاشة_` (`FULLSCREEN`) حالة ملء الشاشة.
* `_حوم_` (`HOVER`) حالة الحوم بالمؤشر على العنصر.
* `_ضمن_النطاق_` (`IN_RANGE`) حالة أن تكون القيمة ضمن نطاق ما.
* `_وسطي_` (`INTERMEDIATE`) الحالة الوسطية.
* `_باطل_` (`INVALID`) حالة أن يكون العنصر باطل، أي مثلاً عندما نكتب في خانة البريد عنوان بريد غير صالح.
* `_رابط_` (`LINK`) حالة أن يكون رابط.
* `_اختياري_` (`OPTIONAL`) حالة أن يكون العنصر اختياري، أي مثلاً في الاستبيانات قد لا تكون كل العناصر مطلوبة.
* `_خارج_النطاق_` (`OUT_OF_RANGE`) حالة أن تكون القيمة خارج النطاق.
* `_قراءة_فقط_` (`READ_ONLY`) حالة أن يكون العنصر للقراءة فقط.
* `_قراءة_وكتابة_` (`READ_WRITE`) حالة أن يكون العنصر للقراءة و الكتابة.
* `_إلزامي_` (`REQUIRED`) حالة أن يكون العنصر إلزامي، مثل كلمة المرور عند التسجيل في موقع.
* `_مستهدف_` (`TARGET`) حالة أن يكون العنصر مستهدف.
* `_صالح_` (`VALID`) حالة أن يكون العنصر صالح.
* `_مزار_` (`VISITED`) حالة أن يكون العنصر مزار، أي عندما يكون لدينا رابط.

#### تطبيق الطرز على عنصر فرعي

يمكن القيام بذلك بتمرير اسم فئة إلى `الطراز` لتحديد ما نريد أن يطبق عليه الطرز.

كما يمكننا أيضاً تحديد حالة محددة للعنصر يتم عندها تطبيق الطراز على الفرع. مثلاً حالة أن يكون
المؤشر فوق الودجة الرئيسية فيُطبق عندها الطراز على الفرع. يتم ذلك بتمرير الحالة إلى `الطراز`
قبل اسم الفئة، كما في المثال التالي:

<div dir=rtl>

```
صـندوق({}).{
    // نطبق بعض الأطرزة
    الطراز.{
        الحشوة = مـسافة4.نقاط(3)؛
        الخلفية = خـلفية(_لون_فاتح_)؛
        الإظهار = إظـهار._مرن_؛
        النسق = نـسق._سطر_؛
        المحاذاة = مـحاذاة._وسط_؛
    }؛
    // نطبق طراز على ودجة فرعية من الفئة أيقونة
    الطراز(">>icon").{
        الحشوة = مـسافة4.نقاط(0, 4)؛
        العرض = مـسافة.نقاط(20)؛
        الطول = مـسافة.نقاط(0)؛
        انتقال_الطول = انـتقال(0.2)؛
    }
    // نقوم بتطبيق طراز على ودجة فرعية من الفئة أيقونة 
    // هذا الطراز يطبق عندما نحوم بالمؤشر على الأيقونة
    الطراز({ مـحدد_حالة._حوم_, ">>icon" }).{
        الطول = مـسافة.نقاط(20)؛
    }
    أضف_فروع({
        // ودجة رابط
        // و الذي يحوي على ودجة فرعية هي صورة
        ارتـباط_تشعبي(رابط, صـورة().{
            الرابط = أيقونة؛
            // فئة هذا الرابط هو أيقونة
            اسم_الفئة = نـص("icon")؛
        })
    })؛
}؛
```

</div>

```
Box({}).{
    // نطبق بعض الأطرزة
    style.{
        padding = Length4.pt(3);
        background = Background(LIGHT_COLOR);
        display = Display.FLEX;
        layout = Layout.ROW;
        align = Align.CENTER;
    };
    // نطبق طراز على ودجة فرعية من الفئة أيقونة
    style(">>icon").{
        padding = Length4.pt(0, 4);
        width = Length.pt(20);
        height = Length.pt(0);
        heightTransition = Transition(0.2);
    }
    // نقوم بتطبيق طراز على ودجة فرعية من الفئة أيقونة 
    // هذا الطراز يطبق عندما نحوم بالمؤشر على الأيقونة
    style({ StateSelector.HOVER, ">>icon" }).{
        height = Length.pt(20)
    }

    // الودجات الفرعية
    addChildren({
        // ودجة رابط
        // و الذي يحوي على ودجة فرعية هي صورة
        Hyperlink(link, Image().{
            url = icon;
            // فئة هذا الرابط هو أيقونة
            className = String("icon");
        })
    });
}
```

هنا نلاحظ أننا حددنا الابن المباشر الذي له الخاصية icon في أول تطبيق للطرز.

من ثم قمنا بتحديد حالة أن يكون المؤشر فوق العنصر عن طريق تمرير StateSelector.HOVER أيضاً.


### تـحريك (Animation)

<div dir=rtl>

```
صنف تـحريك {
    عرف حدد(مدة_كلية: عـائم، أطرزة: مـصفوفة[طـراز])؛
    عرف حدد(مدة_كلية: عـائم، أطرزة: ربـط[عـائم، طـراز])؛
}
```

</div>

```
class Animation {
    handler this.set(totalDuration: Float, styles: Array[Style]);
    handler this.set(totalDuration: Float, styles: Map[Float, Style]);
}
```

يستعمل هذا الصنف لإنشاء تحريك لعنصر ما.

`حدد` (`set`) وظيفة للقيام بتحديد التحريك الذي نريده.

هنالك نسختان من هذه الطريقة، واحدة تقبل الأنماط على شكل مصفوفة و الأخرى على شكل تـطبيق تمثل مفاتيحه
الوقت الذي يُطبق فيه الطراز المعرف في القيمة المقابلة لذلك المفتاح.


### أبـعاد (Dimensions)

<div dir=rtl>

```
صنف أبـعاد {
    عرف عرض: صـحيح = 0؛
    عرف طول: صـحيح = 0؛
}
```

</div>

```
class Dimensions {
    def width: Int = 0;
    def height: Int = 0;
}
```
صنف يحمل معلومات الأبعاد.

`عرض` (`width`) العرض.

`طول` (`height`) الطول.


### لـون (Color)

<div dir=rtl>

```
صنف لـون {
    عرف أحمر: صـحيح = 0؛
    عرف أخضر: صـحيح = 0؛
    عرف أزرق: صـحيح = 0؛
    عرف شفافية: صـحيح = 0؛
    عرف حول_لنص: لقب toString؛
}
```

</div>

```
class Color {
    def red: Int = 0;
    def green: Int = 0;
    def blue: Int = 0;
    def alpha: Int = 0;
}
```
صنف يحمل معلومات اللون.

`أحمر` (`red`) نسبة اللون الأحمر في اللون.

`أخضر` (`green`) نسبة اللون الأخضر في اللون.

`أزرق` (`blue`) نسبة اللون الأزرق في اللون.

`شفافية` (`alpha`) شفافية اللون.


### مـسافة (Length)

<div dir=rtl>

```
صنف مـسافة {
    عرف_مهيء[بكسلات، "بكسلات"]؛
    عرف_مهيء[نقاط، "نقاط"]؛
    عرف_مهيء[مم، "مم"]؛
    عرف_مهيء[عن، "عن"]؛
    عرف_مهيء[طن، "طن"]؛
    عرف_مهيء[بنص، "بنص"]؛
    عرف_مهيء[بنك، "بنك"]؛
    عرف_مهيء[حخ، "حخ"]؛
    عرف_مهيء[مئوي، "%"]؛
    عرف حول_لنص(هذا:طـول): نـص؛
}
```

</div>

```
class Length {
    defineInitializer[px, "px"];
    defineInitializer[pt, "pt"];
    defineInitializer[mm, "mm"];
    defineInitializer[vw, "vw"];
    defineInitializer[vh, "vh"];
    defineInitializer[vmin, "vmin"];
    defineInitializer[vmax, "vmax"];
    defineInitializer[em, "em"];
    defineInitializer[percent, "%"];
    handler (this:Length).toString(): String;
}
```
صنف يحمل معلومات المسافة.

يقوم هذا الصنف بتعريف العديد من واحدات القياس و التي هي كما يلي:

`بكسلات` (`px`) عدد البكسلات.

`نقاط` (`pt`) عدد النقاط.

`مم` (`mm`) عدد الميليمترات

`عن` (`vw`) مسافة نسبية بالنسبة لـ 1 بالمئة من عرض نافذة المتصفح.

`طن` (`vh`) مسافة نسبية بالنسبة لـ 1 بالمئة من  ارتفاع نافذة المتصفح.

`بنص` (`vmin`) مسافة نسبية بالنسبة لـ 1 بالمئة من أصغر جانب لنافذة المتصفح.

`بنك` (`vmax`) مسافة نسبية بالنسبة لـ 1 بالمئة من أكبر جانب لنافذة المتصفح.

`حخ` (`em`) مسافة نسبية بالنسبة لحجم الخط للعنصر.

`مئوي` (`percent`) نسبة مئوية بالنسبة للعنصر الذي يحتوي العنصر.

كما يحوي الطريقة التالية:

`حول_لنص` (`toString`) طريقة لتحويل معلومات الصتف إلى ترميز نصي.


### مـسافة4 (Length4)

<div dir=rtl>

```
صنف مـسافة4 {
    عرف_مهيء[بكسلات، "بكسلات"]؛
    عرف_مهيء[نقاط، "نقاط"]؛
    عرف_مهيء[مم، "مم"]؛
    عرف_مهيء[عن، "عن"]؛
    عرف_مهيء[طن، "طن"]؛
    عرف_مهيء[بنص، "بنص"]؛
    عرف_مهيء[بنك، "بنك"]؛
    عرف_مهيء[حخ، "حخ"]؛
    عرف_مهيء[مئوي، "%"]؛
    عرف حول_لنص(هذا:طـول): نـص؛
}
```

</div>

```
class Length4 {
    defineInitializer[px, "px"];
    defineInitializer[pt, "pt"];
    defineInitializer[mm, "mm"];
    defineInitializer[vw, "vw"];
    defineInitializer[vh, "vh"];
    defineInitializer[vmin, "vmin"];
    defineInitializer[vmax, "vmax"];
    defineInitializer[em, "em"];
    defineInitializer[percent, "%"];
    handler (this:Length).toString(): String set_ptr;
}
```

مشابه لـ`مـسافة` (`Length`) ولكن يعرف 4 قيم، قيمة لكل من الاتجاهات الأربعة.


### انـتقال (Transition)

<div dir=rtl>

```
صنف انـتقال {
    عرف المدة: عـائم = 0؛
    عرف الدالة: نـص؛
    عرف التأخير: عـائم = 0؛
    عرف حول_لنص(): نـص؛
}
```

</div>

```
class Transition {
    def duration: Float = 0;
    def fn: String;
    def delay: Float = 0;
    handler this.toString(): String;
}
```
صنف يحمل معلومات الانتقال.

`المدة` (`duration`) مدة الانتقال.

`الدالة` (`fn`) اسم دالة الانتقال المطبقة.

`التأخير` (`delay`) التأخير في تنفيذ الانتقال.

`حول_لنص` (`toString`) طريقة لتحويل معلومات الصنف إلى ترميز نصي.


### تـحول (Transform)

<div dir=rtl>

```
وحدة تـحول {
    عرف ماتركس(أ: عـائم، ب: عـائم، ج: عـائم، د: عـائم، انتقال_س: عـائم، انتقال_ع: عـائم): نـص؛
    عرف ماتركس(
        أ1: عـائم، ب1: عـائم، ج1: عـائم، د1: عـائم،
        أ2: عـائم، ب2: عـائم، ج2: عـائم، د2: عـائم،
        أ3: عـائم، ب3: عـائم، ج3: عـائم، د3: عـائم،
        أ4: عـائم، ب4: عـائم، ج4: عـائم، د4: عـائم
    ): نـص؛
    عرف دور(درجة: عـائم): نـص؛
    عرف دور(س: عـائم، ع: عـائم، ج: عـائم، درجة: عـائم): نـص؛
    عرف حجم(س: عـائم): نـص؛
    عرف حجم(س: عـائم، ع: عـائم): نـص؛
    عرف حجم(س: عـائم، ع: عـائم، ج: عـائم): نـص؛
    عرف أزح(س: سند[مـسافة]، ع: سند[مـسافة]): نـص؛
    عرف أزح(س: سند[مـسافة]، ع: سند[مـسافة]، ج: سند[مـسافة]): نـص؛
}
```

</div>

```
module Transform {
    func matrix(a: Float, b: Float, c: Float, d: Float, tx: Float, ty: Float): String;
    func matrix(
            a1: Float, b1: Float, c1: Float, d1: Float,
            a2: Float, b2: Float, c2: Float, d2: Float,
            a3: Float, b3: Float, c3: Float, d3: Float,
            a4: Float, b4: Float, c4: Float, d4: Float
    ): String;
    func rotate(deg: Float): String;
    func rotate(x: Float, y: Float, z: Float, deg: Float): String;
    func scale(x: Float): String;
    func scale(x: Float, y: Float): String;
    func scale(x: Float, y: Float, z: Float): String;
    func translate(x: ref[Length], y: ref[Length]): String;
    func translate(x: ref[Length], y: ref[Length], z: ref[Length]): String;
}
```
صنف يحمل معلومات التحول.

`ماتركس` (`matrix`) طريقة لتعريف مصفوفة التحول.

هنالك نسختان من هذه الطريقة، الأولى تعرف مصفوفة تحول ثنائية الأبعاد بينما الثانية تعرفها ثلاثية الأبعاد.

`دور` (`rotate`) طريقة لتطبيق تحول دوران على عنصر.

هذه الطريقة لها نسختان، الأولى لتطبيق الدوران في فضاء ثنائي البعد، بينما الثانية لتطبيقه في فضاء ثلاثي الأبعاد.

في الطريقة الأولى نحتاج فقط الزاوية، بينما في الطريقة الثانية نحدد أيضاً شعاع المحور الذي نريد التدوير حوله
عبر تحديد مساقطه على المحاور الثلاث.

`حجم` (`scale`) طريقة لتحجيم الشكل و لها نسختان ثنائية بعد و ثلاثية بعد.

`أزح` (`translate`) طريقة لإزاحة شكل و لها نسختان ثنائية بعد و ثلاثية بعد.


### خـلفية (Background)

<div dir=rtl>

```
صنف خـلفية {
    عرف حول_لنص(هذا:خـلفية): نـص؛
}
```

</div>

```
class Background {
    handler (this:Background).toString(): String;
}
```

صنف يحمل معلومات الخلفية.

`حول_لنص` (`toString`) طريقة لتحويل معلومات الخلفية إلى ترميز نصي.


### مـرونة (Flex)

<div dir=rtl>

```
صنف مـرونة {
    عرف حول_لنص(): نـص؛
}
```

</div>

```
class Flex {
    handler this.toString(): String;
}
```
صنف يحمل معلومات المرونة.

`حول_لنص` (`toString`) طريقة لتحويل معلومات المرونة إلى ترميز نصي.


### ظـل (Shadow)

<div dir=rtl>

```
صنف ظـل {
    عرف حول_لنص(): نـص؛
}
```

</div>

```
class Shadow {
    handler this.toString(): String;
}
```
صنف يحمل معلومات الظل.

`حول_لنص` (`toString`) طريقة لتحويل معلومات الظل إلى ترميز نصي.


### مـوقع (Position)

<div dir=rtl>

```
صنف مـوقع {
    تعداد_قيمة_نصية[_ساكن_، "ساكن"]؛
    تعداد_قيمة_نصية[_نسبي_، "نسبي"]؛
    تعداد_قيمة_نصية[_مثبت_، "مثبت"]؛
    تعداد_قيمة_نصية[_مطلق_، "مطلق"]؛
    تعداد_قيمة_نصية[_لزج_، "لزج"]؛
}
```

</div>

```
class Position {
    enumStringValue[STATIC, "static"];
    enumStringValue[RELATIVE, "relative"];
    enumStringValue[FIXED, "fixed"];
    enumStringValue[ABSOLUTE, "absolute"];
    enumStringValue[STICKY, "sticky"];
}
```

صنف يحمل قيم الموقع الممكنة على شكل تعدادات.
* `_ساكن_` (`STATIC`)
* `_نسبي_` (`RELATIVE`)
* `_مثبت_` (`FIXED`)
* `_مطلق_` (`ABSOLUTE`)
* `_لزج_` (`STICKY`)


### فـيض (Overflow)

<div dir=rtl>

```
صنف فـيض {
    تعداد_قيمة_نصية[_ظاهر_، "ظاهر"]؛
    تعداد_قيمة_نصية[_مخفي_، "مخفي"]؛
    تعداد_قيمة_نصية[_مقطوع_، "مقطوع"]؛
    تعداد_قيمة_نصية[_تمرير_، "تمرير"]؛
    تعداد_قيمة_نصية[_تلقائي_، "تلقائي"]؛
}
```

</div>

```
class Overflow {
    enumStringValue[VISIBLE, "visible"];
    enumStringValue[HIDDEN, "hidden"];
    enumStringValue[CLIP, "clip"];
    enumStringValue[SCROLL, "scroll"];
    enumStringValue[AUTO, "auto"];
}
```

صنف يحمل قيم الفيض الممكنة على شكل تعدادات.
* `_ظاهر_` (`VISIBLE`)
* `_مخفي_` (`HIDDEN`)
* `_مقطوع_` (`CLIP`)
* `_تمرير_` (`SCROLL`)
* `_تلقائي_` (`AUTO`)


### إظـهار (Display)

<div dir=rtl>

```
صنف إظـهار {
    تعداد_قيمة_نصية[_ضمني_، "inline"]؛
    تعداد_قيمة_نصية[_كتلة_، "block"]؛
    تعداد_قيمة_نصية[_مرن_، "flex"]؛
    تعداد_قيمة_نصية[_شبكة_، "grid"]؛
    تعداد_قيمة_نصية[_مخفي_، "none"]؛
}
```

</div>

```
class Display {
    enumStringValue[INLINE, "inline"];
    enumStringValue[BLOCK, "block"];
    enumStringValue[FLEX, "flex"];
    enumStringValue[GRID, "grid"];
    enumStringValue[NONE, "none"];
}
```
صنف يحمل قيم الإظهار الممكنة على شكل تعدادات.
* `_ضمني_` (`INLINE`)
* `_كتلة_` (`BLOCK`)
* `_مرن_` (`FLEX`)
* `_شبكة_` (`GRID`)
* `_مخفي_` (`NONE`)


### نـسق (Layout)

<div dir=rtl>

```
صنف نـسق {
    تعداد_قيمة_نصية[_سطر_، "سطر"]؛
    تعداد_قيمة_نصية[_سطر_معكوس_، "سطر_معكوس"]؛
    تعداد_قيمة_نصية[_عمود_، "عمود"]؛
    تعداد_قيمة_نصية[_عمود_معكوس_، "عمود_معكوس"]؛
}
```

</div>

```
class Layout {
    enumStringValue[ROW, "row"];
    enumStringValue[ROW_REVERSE, "row-reverse"];
    enumStringValue[COLUMN, "column"];
    enumStringValue[COLUMN_REVERSE, "column-reverse"];
}
```

صنف يحمل قيم النسق الممكنة على شكل تعدادات.
* `_سطر_` (`ROW`)
* `_سطر_معكوس_` (`ROW_REVERSE`)
* `_عمود_` (`COLUMN`)
* `_عمود_معكوس_` (`COLUMN_REVERSE`)


### مـحاذاة (Align)

<div dir=rtl>

```
صنف مـحاذاة {
    تعداد_قيمة_نصية[_بداية_، "بداية"]؛
    تعداد_قيمة_نصية[_وسط_، "وسط"]؛
    تعداد_قيمة_نصية[_نهاية_، "نهاية"]؛
    تعداد_قيمة_نصية[_تمدد_، "تمدد"]؛
}
```

</div>

```
class Align {
    enumStringValue[START, "start"];
    enumStringValue[CENTER, "center"];
    enumStringValue[END, "end"];
    enumStringValue[STRETCH, "stretch"];
}
```

صنف يحمل قيم المحاذاة الممكنة على شكل تعدادات.
* `_بداية_` (`START`)
* `_وسط_` (`CENTER`)
* `_نهاية_` (`END`)
* `_تمدد_` (`STRETCH`)


### مـلء_سطر (Justify)

<div dir=rtl>

```
صنف مـلء_سطر {
    تعداد_قيمة_نصية[_بداية_، "بداية"]؛
    تعداد_قيمة_نصية[_وسط_، "وسط"]؛
    تعداد_قيمة_نصية[_نهاية_، "نهاية"]؛
    تعداد_قيمة_نصية[_تمدد_، "تمدد"]؛
    تعداد_قيمة_نصية[_مسافة_بينية_، "مسافة_بينية"]؛
    تعداد_قيمة_نصية[_مسافة_محيطية_، "مسافة_محيطية"]؛
    تعداد_قيمة_نصية[_مسافة_متساوية_، "مسافة_متساوية"]؛
}
```

</div>

```
class Justify {
    enumStringValue[START, "start"];
    enumStringValue[CENTER, "center"];
    enumStringValue[END, "end"];
    enumStringValue[STRETCH, "stretch"];
    enumStringValue[SPACE_BETWEEN, "space-between"];
    enumStringValue[SPACE_AROUND, "space-around"];
    enumStringValue[SPACE_EVENLY, "space_evenly"];
}
```

صنف يحمل قيم ملء السطر الممكنة على شكل تعدادات.
* `_بداية_` (`START`)
* `_وسط_` (`CENTER`)
* `_نهاية_` (`END`)
* `_تمدد_` (`STRETCH`)
* `_مسافة_بينية_` (`SPACE_BETWEEN`)
* `_مسافة_محيطية_` (`SPACE_AROUND`)
* `_مسافة_متساوية_` (`SPACE_EVENLY`)


### مـؤشر (Cursor)

<div dir=rtl>

```
صنف مـؤشر {
    تعداد_قيمة_نصية[_تلقائي_، "تلقائي"]؛
    تعداد_قيمة_نصية[_مبدئي_، "مبدئي"]؛
    تعداد_قيمة_نصية[_مساعدة_، "مساعدة"]؛
    تعداد_قيمة_نصية[_سبابة_، "سبابة"]؛
    تعداد_قيمة_نصية[_تقدم_، "تقدم"]؛
    تعداد_قيمة_نصية[_انتظار_، "انتظار"]؛
    تعداد_قيمة_نصية[_تقاطع_، "تقاطع"]؛
    تعداد_قيمة_نصية[_كتابة_، "كتابة"]؛
    تعداد_قيمة_نصية[_تحريك_، "تحريك"]؛
    تعداد_قيمة_نصية[_ممنوع_، "ممنوع"]؛
    تعداد_قيمة_نصية[_إمساك_، "إمساك"]؛
    تعداد_قيمة_نصية[_ممسك_، "ممسك"]؛
    تعداد_قيمة_نصية[_تحجيم_أفقي_، "تحجيم_أفقي"]؛
    تعداد_قيمة_نصية[_تحجيم_عمودي_، "تحجيم_عمودي"]؛
    تعداد_قيمة_نصية[_تحجيم_مائل_، "تحجيم_مائل"]؛
    تعداد_قيمة_نصية[_تحجيم_مائل_معكوس_، "تحجيم_مائل_معكوس"]؛
    تعداد_قيمة_نصية[_تكبير_، "تكبير"]؛
    تعداد_قيمة_نصية[_تصغير_، "تصغير"]؛
}
```

</div>

```
class Cursor {
    enumStringValue[AUTO, "auto"];
    enumStringValue[DEFAULT, "default"];
    enumStringValue[HELP, "help"];
    enumStringValue[POINTER, "pointer"];
    enumStringValue[PROGRESS, "progress"];
    enumStringValue[WAIT, "wait"];
    enumStringValue[CROSSHAIR, "crosshair"];
    enumStringValue[TEXT, "text"];
    enumStringValue[MOVE, "move"];
    enumStringValue[NOT_ALLOWED, "not-allowed"];
    enumStringValue[GRAB, "grab"];
    enumStringValue[GRABBING, "grabbing"];
    enumStringValue[EW_RESIZE, "ew-resize"];
    enumStringValue[NS_RESIZE, "ns-resize"];
    enumStringValue[NESW_RESIZE, "nesw-resize"];
    enumStringValue[NWSE_RESIZE, "nwse-resize"];
    enumStringValue[ZOOM_IN, "zoom-in"];
    enumStringValue[ZOOM_OUT, "zoom-out"];
}
```

صنف يحمل قيم المؤشر الممكنة على شكل تعدادات.
* `_تلقائي_` (`AUTO`)
* `_مبدئي_` (`DEFAULT`)
* `_مساعدة_` (`HELP`)
* `_سبابة_` (`POINTER`)
* `_تقدم_` (`PROGRESS`)
* `_انتظار_` (`WAIT`)
* `_تقاطع_` (`CROSSHAIR`)
* `_كتابة_` (`TEXT`)
* `_تحريك_` (`MOVE`)
* `_ممنوع_` (`NOT_ALLOWED`)
* `_إمساك_` (`GRAB`)
* `_ممسك_` (`GRABBING`)
* `_تحجيم_أفقي_` (`EW_RESIZE`)
* `_تحجيم_عمودي_` (`NS_RESIZE`)
* `_تحجيم_مائل_` (`NESW_RESIZE`)
* `_تحجيم_مائل_معكوس_` (`NWSE_RESIZE`)
* `_تكبير_` (`ZOOM_IN`)
* `_تصغير_` (`ZOOM_OUT`)


### طـراز_إطار (BorderStyle)

<div dir=rtl>

```
صنف طـراز_إطار {
    تعداد_قيمة_نصية[_منقط_، "منقط"]؛
    تعداد_قيمة_نصية[_مقطع_، "مقطع"]؛
    تعداد_قيمة_نصية[_مستمر_، "مستمر"]؛
    تعداد_قيمة_نصية[_مزدوج_، "مزدوج"]؛
    تعداد_قيمة_نصية[_أخدود_، "أخدود"]؛
    تعداد_قيمة_نصية[_حافة_، "حافة"]؛
    تعداد_قيمة_نصية[_بلا_، "بلا"]؛
    تعداد_قيمة_نصية[_مخفي_، "مخفي"]؛
}
```

</div>

```
class BorderStyle {
    enumStringValue[DOTTED, "dotted"];
    enumStringValue[DASHED, "dashed"];
    enumStringValue[SOLID, "solid"];
    enumStringValue[DOUBLE, "double"];
    enumStringValue[GROOVE, "groove"];
    enumStringValue[RIDGE, "ridge"];
    enumStringValue[NONE, "none"];
    enumStringValue[HIDDEN, "hidden"];
}
```

صنف يحمل قيم طراز الإطار الممكنة على شكل تعدادات.
* `_منقط_` (`DOTTED`)
* `_مقطع_` (`DASHED`)
* `_مستمر_` (`SOLID`)
* `_مزدوج_` (`DOUBLE`)
* `_أخدود_` (`GROOVE`)
* `_حافة_` (`RIDGE`)
* `_بلا_` (`NONE`)
* `_مخفي_` (`HIDDEN`)


### تـقطيع_كلمات (WordBreak)

<div dir=rtl>

```
صنف تـقطيع_كلمات {
    تعداد_قيمة_نصية[_عادي_، "عادي"]؛
    تعداد_قيمة_نصية[_قطع_الكل_، "قطع_الكل"]؛
    تعداد_قيمة_نصية[_احتفظ_بالكل_، "احتفظ_بالكل"]؛
    تعداد_قيمة_نصية[_قطع_الكلمات_، "قطع_الكلمات"]؛
}
```

</div>

```
class WordBreak {
    enumStringValue[NORMAL, "normal"];
    enumStringValue[BREAK_ALL, "break-all"];
    enumStringValue[KEEP_ALL, "keep-all"];
    enumStringValue[BREAK_WORD, "break-word"];
}
```

صنف يحمل قيم تقطيع الكلمات الممكنة على شكل تعدادات.
* `_عادي_` (`NORMAL`)
* `_قطع_الكل_` (`BREAK_ALL`)
* `_احتفظ_بالكل_` (`KEEP_ALL`)
* `_قطع_الكلمات_` (`BREAK_WORD`)


### اتـجاه (Direction)

<div dir=rtl>

```
صنف اتـجاه {
    تعداد_قيمة_نصية[_من_اليسار_، "من_اليسار"]؛
    تعداد_قيمة_نصية[_من_اليمين_، "من_اليمين"]؛
}
```

</div>

```
class Direction {
    enumStringValue[LTR, "ltr"];
    enumStringValue[RTL, "rtl"];
}
```

صنف يحمل قيم الاتجاه الممكنة على شكل تعدادات.
* `_من_اليسار_` (`LTR`)
* `_من_اليمين_` (`RTL`)


### زخـرفة_نص (TextDecoration)

<div dir=rtl>

```
صنف زخـرفة_نص {
    تعداد_قيمة_نصية[_بلا_، "بلا"]؛
    تعداد_قيمة_نصية[_تحت_، "تحت"]؛
    تعداد_قيمة_نصية[_فوق_، "فوق"]؛
    تعداد_قيمة_نصية[_خلال_، "خلال"]؛
}
```

</div>

```
class TextDecoration {
    enumStringValue[NONE, "none"];
    enumStringValue[UNDERLINE, "underline"];
    enumStringValue[OVERLINE, "overline"];
    enumStringValue[LINE_THROUGH, "line-through"];
}
```

صنف يحمل قيم زخرفة النص الممكنة على شكل تعدادات.
* `_بلا_` (`NONE`)
* `_تحت_` (`UNDERLINE`)
* `_فوق_` (`OVERLINE`)
* `_خلال_` (`LINE_THROUGH`)


### طـراز_زخرفة_نص (TextDecorationStyle)

<div dir=rtl>

```
صنف طـراز_زخرفة_نص {
    تعداد_قيمة_نصية[_مستمر_، "مستمر"]؛
    تعداد_قيمة_نصية[_مزدوج_، "مزدوح"]؛
    تعداد_قيمة_نصية[_منقط_، "منقط"]؛
    تعداد_قيمة_نصية[_مقطع_، "مقطع"]؛
    تعداد_قيمة_نصية[_متموج_، "متموج"]؛
}
```

</div>

```
class TextDecorationStyle {
    enumStringValue[SOLID, "solid"];
    enumStringValue[DOUBLE, "double"];
    enumStringValue[DOTTED, "dotted"];
    enumStringValue[DASHED, "dashed"];
    enumStringValue[WAVY, "wavy"];
}
```

صنف يحمل قيم طراز زخرفة النص الممكنة على شكل تعدادات.
* `_مستمر_` (`SOLID`)
* `_مزدوج_` (`DOUBLE`)
* `_منقط_` (`DOTTED`)
* `_مقطع_` (`DASHED`)
* `_متموج_` (`WAVY`)


### مـحاذاة_نص (TextAlign)

<div dir=rtl>

```
صنف مـحاذاة_نص {
    تعداد_قيمة_نصية[_يسار_، "يسار"]؛
    تعداد_قيمة_نصية[_يمين_، "يمين"]؛
    تعداد_قيمة_نصية[_وسط_، "وسط"]؛
    تعداد_قيمة_نصية[_املأ_، "املأ"]؛
}
```

</div>

```
class TextAlign {
    enumStringValue[LEFT, "left"];
    enumStringValue[RIGHT, "right"];
    enumStringValue[CENTER, "center"];
    enumStringValue[JUSTIFY, "justify"];
}
```
صنف يحمل قيم محاذاة النص الممكنة على شكل تعدادات.
* `_يسار_` (`LEFT`)
* `_يمين_` (`RIGHT`)
* `_وسط_` (`CENTER`)
* `_املأ_` (`JUSTIFY`)


### سـمك_خط (FontWeight)

<div dir=rtl>

```
عرف سـمك_خط {
    عرف _عادي_: 400؛ 
    عرف _سميك_: 700؛
}
```

</div>

```
def FontWeight: {
    def NORMAL: 400;
    def BOLD: 700;
}
```

صنف يحمل قيم الخط الممكنة.
* `_عادي_` (`NORMAL`)
* `_سميك_` (`BOLD`)


### طـوفان (Floating)

<div dir=rtl>

```
صنف طـوفان {
    تعداد_قيمة_نصية[_بلا_، "بلا"]؛
    تعداد_قيمة_نصية[_يسار_، "يسار"]؛
    تعداد_قيمة_نصية[_يمين_، "يمين"]؛
}
```

</div>

```
class Floating {
    enumStringValue[NONE, "none"];
    enumStringValue[LEFT, "left"];
    enumStringValue[RIGHT, "right"];
}
```

صنف يحمل قيم الطوفان الممكنة على شكل تعدادات.
* `_بلا_` (`NONE`)
* `_يسار_` (`LEFT`)
* `_يمين_` (`RIGHT`)
