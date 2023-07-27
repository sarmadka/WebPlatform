# WebPlatform

[[English]](resources.en.md)

[[رجوع]](../readme.ar.md)

## الموارد (Resources)

### مـورد_صورة (ImageResource)

<div dir=rtl>

```
صنف مـورد_صورة {
    عرف معرف: صـحيح_متكيف = 0؛
    عرف حمل(مسار: مؤشر[مصفوفة[مـحرف]]): سـندنا[مـؤجلة[صـحيح]]؛
    عرف هيئ_من_مرسم(مرسم: سند[مـورد_مرسم])؛
    عرف هات_الأبعاد(): أبـعاد؛
}
```

</div>

```
class ImageResource {
    def id: ArchInt = 0;
    handler this.load(u: ptr[array[Char]]): SrdRef[Promise[Int]];
    handler this.initFromCanvas(canvas: ref[CanvasResource]);
    handler this.getDimensions(): Dimensions;
}
```

مورد صورة يمكن استعماله مع عمليات الصور على مرسم.

`معرف` (`id`) معرف فريد لتمييز المورد.

`حمل` (`load`) تستعمل هذه الطريقة لتحميل المورد من مسار معطى.

`هيئ_من_مرسم` (`initFromCanvas`) تستعمل هذه الطريقة لتهيئة المورد من مرسم معطى.

`هات_الأبعاد` (`getDimensions`) طريقة تستعمل لمعرفة أبعاد المورد.


### مـورد_مرسم (CanvasResource)

<div dir=rtl>

```
صنف مـورد_مرسم {
    عرف معرف: صـحيح_متكيف = 0؛
    عرف هيئ(عرض: صـحيح، ارتفاع: صـحيح)؛
    عرف غير_الأبعاد(عرض: صـحيح، ارتفاع: صـحيح)؛
}
```

</div>

```
class CanvasResource {
    def id: ArchInt = 0;
    handler this.init(w: Int, h: Int);
    handler this.resize(w: Int, h: Int);
}
```

مرسم منفصل يمكن استعماله لتوليد الصور بشكل ديناميكي. كما هو الحال مع `مـرسم` (`Canvas`)، يوفر هذا
الصنف مكون (mixin) `رسـم` لتمكين عمليات الرسم. راجع الصنف `رسـم` لمعرفة العمليات الرسومية التي يدعهما
هذا الصنف.

`معرف` (`id`) معرف فريد لتمييز المورد.

`هيئ` (`init`) دالة لتهيئة مرسم بعرض وارتفاع.

`غير_الأبعاد` (`resize`) دالة لتغيير حجم المرسم إلى العرض والارتفاع المطلوبين.


### مـورد_صوت (AudioResource)

<div dir=rtl>

```
صنف مـورد_صوت {
    عرف معرف: صـحيح_متكيف = 0؛
    عرف حمل(مسار: مؤشر[مصفوفة[مـحرف]]): سـندنا[مـؤجلة[صـحيح]]؛
    عرف شغل(تكرار: ثـنائي)؛
    عرف أوقف()؛
    عرف الجهارة = عـائم؛
    عرف الجهارة:عـائم؛
    عرف أمشتغل(): ثـنائي؛
}
```

</div>

```
class AudioResource {
    def id: ArchInt = 0;
    handler this.load(u: ptr[array[Char]]): SrdRef[Promise[Int]];
    handler this.play(loop: Bool);
    handler this.stop();
    handler this.volume = Float;
    handler this.volume:Float;
    handler this.isPlaying(): Bool;
}
```
صنف يستعمل من أجل الموارد الصوتية.

`معرف` (`id`) معرف فريد لتمييز المورد.

`حمل` (`load`) طريقة تستعمل لتحميل المورد الذي له المسار المعطى.

`شغل` (`play`) طريقة تستعمل لتشغيل المورد الصوتي.

المعطيات:

* `تكرار` (`loop`) تحديد فيما إذا كان الوضع هو تكرار للمورد أم يقف عندما ينتهي.

`أوقف` (`stop`) طريقة تستعمل لإيقاف المورد.

`الجهارة` (`volume`) خاصية الصوت، و هنا يمكننا جلبها أو تحديد قيمة لها.

`أمشتغل` (`isPlaying`) طريقة تستعمل لإختبار فيما إذا كان المورد في وضع التشغيل.
