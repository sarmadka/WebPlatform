# WebPlatform

[[English]](safetimeout.en.md)

[[رجوع]](../readme.ar.md)

### مـؤقت_آمن (SafeTimeout)

<div dir=rtl>

```
صنف مـؤقت_آمن {
    عملية هذا.ابدأ(مدة: طـبيعي، م: مغلف(جـيسون))؛
    عملية هذا.ألغ()؛
}
```

</div>

```
class SafeTimeout {
    handler this.set(duration: Word, cb: closure (Json));
    handler this.cancel();
}
```

يستخدم هذا الصنف لإنشاء مؤقت آمن يُضمن إلغاؤه تلقائيًا في حال إزالة هذا المؤقت من الذاكرة قبل
انطلاق المؤقت، كما في حالة تعريف المؤقت ضمن صفحة واجهة مستخدم معرضة للإزالة من الذاكرة، مثلا
عند انتقال المستخدم إلى صفحة أخرى. الوظيفة `ابدأ` (`set`) مشابهة للدالة العمومية
`ابدأ_المؤقت` (`setTimeout`) مع فارق وحيد وهو أن المؤقت يُلغى تلقائيًا عند إزالة هذا الصنف
من الذاكرة.

