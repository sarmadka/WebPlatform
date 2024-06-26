# WebPlatform

[[English]](be_endpoints.en.md)

[[رجوع]](../readme.ar.md)

## إنشاء منافذ الخادم

ننشئ منفذ الخادم (backend endpoints) بكتابة دالة وإضافة المبدل `@منفذ_بياني` لها. يجب أن تستقبل
الدالة معطى واحدًا، وهو مؤشر إلى `بـننف.اتـصال` (`Http.Connection`)، تستخدمه لقراءة بيانات الطلب
وإرسال الرد.

يحتاج هذا المبدل المعطيات التالية:

`طريقة` (`method`): طريقة HTTP التي يمكن بواسطتها الوصول إلى المنفذ و جلب أو إرسال البيانات.

`مسار` (`uri`): المسار الخاص لهذا المنفذ ضمن الخادم.

### مثال

<div dir=rtl>

```
// و له المسار المعطى GET منفذ بياني يقبل الطريقة
// يستعمل هذا المنفذ لجلب الرسائل
@منفذ_بياني["GET"، "/messages"]
دالة هات_الرسائل (اتصال: مؤشر[بـننف.اتـصال]) {
    // ادمج الرسائل سويةً مع سطر فارغ بين كل رسالة و الأخرى
    عرف الرد: نـص = نـص.ادمج(رسائل، "<br>")؛
    // نضع الترويسات اللازمة
    بـننف.اطبع(اتصال، "HTTP/1.1 200 Ok\r\n")؛
    بـننف.اطبع(اتصال، "Content-Type: text/plain\r\n")؛
    بـننف.اطبع(اتصال، "Cache-Control: no-cache\r\n")؛
    بـننف.اطبع(اتصال، "Content-Length: %d\r\n\r\n"، الرد.هات_الطول())؛
    // نضع محتوى الصوان الذي يحمل الرسائل
    بـننف.اطبع(اتصال، الرد.صوان)؛
}
```

</div>

```
// و له المسار المعطى GET منفذ بياني يقبل الطريقة
// يستعمل هذا المنفذ لجلب الرسائل
@beEndpoint["GET", "/messages"]
func getMessages (conn: ptr[Http.Connection]) {
    // ادمج الرسائل سويةً مع سطر فارغ بين كل رسالة و الأخرى
    def response: String = String.merge(messages, "<br>");
    // نضع الترويسات اللازمة
    Http.print(conn, "HTTP/1.1 200 Ok\r\n");
    Http.print(conn, "Content-Type: text/plain\r\n");
    Http.print(conn, "Cache-Control: no-cache\r\n");
    Http.print(conn, "Content-Length: %d\r\n\r\n", response.getLength());
    // نضع محتوى الصوان الذي يحمل الرسائل
    Http.print(conn, response.buf);
}
```

نلاحظ في مثالنا السابق كيف قمنا بتعريف دالة تقبل اتصال و تقوم بوضع البيانات بواسطة استدعاء التابع `اطبع` على `بـننف`
بحيث نقوم بوضع الترويسات المناسبة و وضع البيانات التي نريد إرجاعها و هذا ما يظهر في آخر  سطر.

كما قمنا بإضافة المبدل وتحديد الطريقة `GET` للمنفذ وتحديد المسار كـ`/messages`.

