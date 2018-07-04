---
title: Date对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---
> Date（日期/时间对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Date	操作日期和时间的对象

构造函数：

``` JavaScript
new Date( )

new Date(milliseconds)

new Date(datestring)

new Date(year, month, day, hours, minutes, seconds, ms)

```

* 没有参数的构造函数`Date()`将把创建的Date对象设置为当前的日期和时间。

* 如果传递给它的参数是一个数字，那么这个数字将被作为日期的内部数字表示，其单位是毫秒，就像方法`getTime()`的返回值一样。

* 如果传递给它的参数是一个字符串，它就是日期的字符串表示，其格式就是方法`Date.parse()`接受的格式。

* 否则，传递给该构造函数的参数是2～7个数字，它们分别指定了日期和时间的各个字段。除了前两个字段(年和月字段)外，其他所有字段都是可选的。

* 注意，声明这些日期和时间的字段使用的都是本地时间，而不是UTC时间(类似于GMT时间)。

* `Date()`还可以作为普通函数被调用(不带有运算符new)。以这种方式调用时,`Date()`将忽略传递给它的所有参数，返回当前日期和时间的字符串表示。

参数：

*  `milliseconds`：期望的日期距1970年1月1日午夜(UTC)的毫秒数。

*  `datestring`：一个字符串，声明了日期，也可以同时声明时间。

* `year`：年份，一个四位数。例如，2001指的是2001年。

* `month`：月份，0(代表一月)到11(代表十二月)之间的一个整数。

*  `day`：一个月的某一天，1～31之间的一个整数。

* `hours`：小时，0(午夜)到23(晚上11点)之间的一个整数。该参数是可选的。

* `minutes`：分钟，0～59之间的一个整数。该参数是可选的。

*  `seconds`：秒，0～59之间的一个整数。该参数是可选的。

* `ms`：毫秒，0～999之间的一个整数。该参数是可选的。


方法：

* Date对象没有可以直接读写的属性，所有对日期和时间值的访问都是通过方法执行的。


* Date对象的大多数方法采用两种形式，一种是使用本地时间进行操作，另一种是使用世界(UTC或GMT)时进行操作。
* 

* 只有`Date对象`才能调用Date方法，如果用其他类型的对象调用这些方法，将抛出异常TypeError。


* `get[UTC]Date( )`：返回Date对象所代表的月中的某一天，采用本地时间或世界时。


* `get[UTC]Day( )`：返回Date对象所代表的一周中的某一天，采用本地时间或世界时。


* `get[UTC]FullYear( )`：返回日期中的年份，用四位数表示，采用本地时间或世界时。


* `get[UTC]Hours( )`：返回Date对象的小时字段，采用本地时间或世界时。

* `get[UTC]Milliseconds( )`：返回lDate对象的毫秒字段，采用本地时间或世界时。

* `get[UTC]Minutes( )`：返回Date对象的分钟字段，采用本地时间或世界时。

* `get[UTC]Month( )`：返回Date对象的月份字段，采用本地时间或世界时。

* `get[UTC]Seconds( )`：返回Date对象的秒字殴，采用本地时间或世界时。

* `getTime()`：返回Date对象的内部毫秒表示。注意，该值独立于时区，所有没有单独的 getUTCtime()方法。

* `getTimezoneOffset( )`：返回这个日期的本地时间和UTC表示之间的时差，以分钟为单位。注意，是否是夏令时或在指定的日期中夏令时是否有效，将决定该方法的返回值。

* `getYear( )`：返回Date对象的年份。一般不使用这种方法，推荐使用的方法是`getFullYear()`。

* `set[UTC]Date( )`：设置Date对象的月中的某一天，采用本地时间或世界时。

* `set[UTC]FullYear( )`：设置Date对象的年份字段(月份和天数字段可选)，采用本地时间或世界时。

* `set[UTC]Hours( )`：设置Date对象的小时字段(分钟、秒和毫秒字段可选)，采用本地时间或世界时。

* `set[UTC]Milliseconds( )`：设置Date对象的毫秒字段，采用本地时间或世界时。

* `set[UTC]Minutes( )`：设置Date对象的分钟字段(秒和毫秒字段可选)，采用本地时间或世界时。

* `set[UTC]Month( )`：设置Date对象的月份字段(一个月的天数字段可选)，采用本地时间或世界时。

* `set[UTC]Seconds( )`：设置Date对象的秒字段(毫秒字段可选)，采用本地时间或世界时。

* `setTime( )`：使用毫秒的形式设置Date对象的各个字段。

* `setYear( )`：设置Date对象的年份字段。该方法被反对使用，推荐使用的方法是`setFullYear()`

* `toDateString( )`：返回日期的日期部分的字符串表示，采用本地时间。

* `toGMTString( )`：将Date对象转换成一个字符串，采用GMT时间区。该方法被反对使用，推荐使用的方法是`toUTCString()`。

* `toLocaleDateString( )`：返回表示日期的日期部分的字符串，采用地方日期，使用地方日期格式化规约。

* `toLocaleString( )`：将Date对象转换成单个个字符串，采用本地时间和地方日期的格式化规约。

* `toLocaleTimeString( )`：返回日期的时间部分的字符串表示，采用本地时间，使用本地时间的格式化规约。

* `toString( )`：将Date对象转换成—个字符串，采用本地时间。

* `toTimeString( )`：返回日期的时间部分的字符串表示，采用本地时间。

* `toUTCString( )`：将Date对象转换成一个字符串，采用世界时。

* `valueOf( )`：将Date对象转换成它的内部毫秒格式。

静态方法：

* 除了上面列出的实例方法之外，Date对象还定义了两个静态方法。这两个方法由构造函数`Date()`自身调用，而不是由Date对象调用：

* `Date.parse( )`：解析日期和时间的字符串表示，返回它的内部毫秒表示。

* `Date.UTC( )`：返回指定的UTC日期和时间的毫秒表示。

描述：

* Date对象是JavaScript语言的一种内部数据类型。它由语法`new Date()`语法创建。

* 创建了Date对象后，就可以使用多种方法来操作它。大多数方法只能用来设置或者获取对象的年份字段、月份字段、天数字段、小时字段、分钟字段以及秒字段，采用本地时间或UTC(世界时或GMT)时间。

* 方法`toString()`以及它的变种可以把日期转换成人们能够读懂的字符串。

举例：

```JavaScript

//一旦创建了Date对象，就可以用各种方法操作它：

d = new Date(  );  // 获取当前日期和时间

document.write('Today is: " + d.toLocaleDateString(  ) + '. ');  // 显示日期

document.write('The time is: ' + d.toLocaleTimeString(  ));      // 显示时间

var dayOfWeek = d.getDay(  );                          // 获取一周中的第几天

var weekend = (dayOfWeek == 0) || (dayOfWeek == 6);  // 判断是否是周末
Date对象的另一种常见用法是用某个时间的毫秒表示减去当前时间的毫秒表示来判断 两个时间的时差。下面的例子说明了这种用法：

<script language="JavaScript">

today = new Date(  );      // 创建时间对象

christmas = new Date(  );  // 获取当前日期对象

christmas.setMonth(11);    // 把月份设置为11月

christmas.setDate(25);     // 把日期设置为25号

// 如果圣诞节已经过了，计算当前日期和圣诞节之间的毫秒数

// 把它转换成天数

//输出消息

if (today.getTime(  ) < christmas.getTime(  )) {

    difference = christmas.getTime(  ) - today.getTime(  );

    difference = Math.floor(difference / (1000 * 60 * 60 * 24));

    document.write('Only ' + difference + ' days until Christmas!<p>');

}

</script>

// 此处是其余和HTML文档

<script language="JavaScript">

// 下面用Data对象计时

// 用1000除它，把毫秒转换成秒

now = new Date(  );

document.write('<p>It took ' +

    (now.getTime(  )-today.getTime(  ))/1000 +

    'seconds to load this page.');

</script>
```

## Date.getDate( )：返回一个月中的某一天

语法：`date.getDate()`

返回值：指定Date对象date所指的月份中的某一天，使用本地时间。返回值是1～31之间的一个整数。

## Date.getDay( )：返回一周中的某一天

语法：`date.getDay()`

返回值：指定Date对象date所指的一个星期中的某一天，使用本地时间。返回值是0(周日) 到6(周六)之间的一个整数。

## Date.getFullYear( )：返回Date对象的年份字段

语法：`date.getFullYear()`

返回值：当dace用本地时间表示时返回的年份。返回值是一个四位数，表示包括世纪值在内的完整年份，而不是两位数的缩写形式。

## Date.getHours( )：返回Date对象的小时字段

语法：`date.getHours()`

返回值：指定Date对象date的小时字段，以本地时间表示。返回值是0(午夜)到23(晚上 11点)之间的一个整数。

## Date.getMilliseconds( )：返回Date对象的毫秒字段

语法：`date.getMilliseconds()`

返回值：指定Date对象date的毫秒字段，用本地时间表示。返回值在0～999之间。

## Date.getMinutes( )：返回Date对象的分钟字段

语法：`date.getMinutes()`

返回值：指定的Date对象date的分钟字段，以本地时间表示。返回值在0～59之间。

## Date.getMonth( )	：返回Date对象的月份字段

语法：`date.getMonth()`

返回值：指定的Date对象date的月份字段，以本地时间表示。返回值在0(一月)到11(十二月)之间。


## Date.getSeconds( )：返回Date对象的秒字段

语法：`date.getSeconds()`

返回值：指定的Date对象date的秒字段，以本地时间表示。返回值在0～59之间。

## Date.getTime( )：返回Date对象的毫秒表示

语法：`date.getTime()`

返回值：指定的Date对象date的毫秒表示，也就是date指定的日期和时间距1970年1月1 日午夜(GMT时间)之间的毫秒数

描述：

* 方法`getTime()`可以将日期和时间转换戍一个整数。这在比较两个Date对象或者要判断两个日期之间的时差时非常有用。

* 注意，日期的毫秒表示独立于时区。

## Date.getTimezoneOffset( )：判断与GMT的时间差

语法：`date.getTimezoneOffset()`

返回值：本地时间与GMT时间之间的时差，以分钟为单位。

描述：

* `getTimezoneOffset()`返回的是本地时间和GMT时间或UTC时间之间相差的分钟数。

* 返回值以分钟计，而不是以小时计，原因是某些国家所占有的时区甚至不到一个小时的间隔。


## Date.getUTCDate( )：返回该天是一个月的哪一天(世界时)

语法：`date.getUTCDate()`

返回值：当date对象用世界时表示时，返回值是该月中的哪一天(是1～31的一个值)。

## Date.getUTCDay( )：返回该天是星期几(世界时)

语法：`date.getUTCDay()`

返回值：当date对象用世界时表示时，返回值是该星期中的哪一天。该值在0(星期天)到6(星期六)之间

## Date.getUTCFullYear( )：返回年份(世界时)

语法：`date.getUTCFullYear()`

返回值：当date对象是用世界时表示时所代表的年份。该值是四位数，而不是两位数的缩写。

## Date.getUTCHours( )	：返回Date对象的小时字段(世界时)

语法：`date.getUTCHours()`

返回值：当date对象用世界时表示时的小时字段，该值在0(午夜)到23(晚上11点)之间。

## Date.getUTCMilliseconds( )：返回Date对象的毫秒字段(世界时)

语法：`date.getUTCMilliseconds()`

返回值：当date对象是用世界时表示时的毫秒字段。

## Date.getUTCMinutes( )：返回Date对象的分钟字段(世界时)

语法：`date.getUTCMinutes()`

返回值：dsce对象用世界时表示时的分钟字段，该值是0～59之间的整数。

## Date.getUTCMonth( )	：返回Date对象的月份(世界时)

语法：`date.getUTCMonth()`

返回值：

* 当date对象用世界时表示时的月份，该值是0(一月)到11(十二月)之间的一个整数。

* 注意，Date对象以1代表某个月的第一天，而不是像月份字段那样使用0代表一年的第一个月。

## Date.getUTCSeconds( )：返回Date对象的秒字段(世界时)

语法：`date.getUTCSeconds()`

返回值：当dace对象用世界时表示时的秒字段，该值是0～59之间的—个整数。

## Date.getYear( )：返回Date对象的年份字段(世界时)

语法：`date.getYear()`

返回值：指定Date对象date的年份字段减去1900。

描述：方法`getyear()`返回的是指定的Date对象的年份字段减去1900后的值。

## Date.parse( )：解析日期/时间字符串

语法：`Date.parse(date)`

参数：`date`：含有要解析的日期和时间的字符串。

返回值：指定的日期和时间距1970年1月1日午夜(GMT时间)之间的毫秒数。

描述：

* `Date.parse()`是Date对象的静态方法。一般通过Date构造函数，采用Date.parse()的形式调用它，而不是通过date对象，采用date.parse()调用该方法。 

* `Date.parse()`只有一个字符串型的参数。它将解析这个字符串中的日期，然后返回它的毫秒形式。

* ECMAScript标准没有规定`Date.parse()`方法解析的字符串的格式，只是说该方法能解析`Date.toString()`方法和`Date.toUTCString()`方法返回的字符串。但是，这些函数根据实现来格式化日期，所以以某种方式编写所有JavaScript实现都能理解的日期是不可能的。

## Date.setDate( )：设置一个月的某一天

语法：`date.setDate(day_of_month)`

参数：day_of_month：1～31之间的整数，作为date中月中某一天字段的新值(以本地时间计)。

返回值：调整过的日期的毫秒表示。

## Date.setFullYear( )：设置年份，也可以设置月份和天

语法：

```JavaScript
date.setFullYear(year)

date.setFullYear(year, month) 

date.setFullYear(year, month, day)
```

参数：

* `year`：在date中设置的年份，用本地时间表示。该参数应该是一个包含世纪值的完整年份，如1999，而不仅是年份的缩写，如99。

* `month`：可选的整数，在0～11之间，用作date的月份字段的新值(以本地时间计)。

* `day`：可选的整数，在1～31之间，用作date的天数字段的新值(以本地时间计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setHours( )：设置Date对象的小时字段、分钟字段、秒字段和毫秒字段

语法：

```JavaScript

date.setHours(hours)

date.setHours(hours, minutes) 

date.setHours(hours, minutes,seconds) 

date.setHours(hours, minutes, seconds, millis)
```
参数：

* `hours`：0(午夜)到23(晚上11点)之间的整数，用作date的小时宇段的新值(以本地时间计)。

* `minutes`：可选的整数，在0～59之间，用作date的分钟字段的新值(以本地时间计)。 

* `seconds`：可选的整数，在0～59之间，用作date的秒字段的新值(以本地时间计)。 

* `millis`：可选的整数，在0～999之间，用作date的毫秒字段的新值(以本地时间计)。 

返回值：调整过的日期的毫秒表示。

## Date.setMilliseconds( )：设置Date对象的毫秒字段

语法：`date.setMilliseconds(millis)`

参数：`millis`：用于设置date的毫秒字段，用本地时间表示。该参数是0～999之间的整数。

返回值：调整过的日期的内部毫秒表示。

## Date.setMinutes( )：设置Date对象的分钟字段和秒字段

语法：

```JavaScript

date.setMinutes(minutes) 

date.setMinutes(minutes, seconds) 

date.setMinutes(minutes, seconds, millis)
```
参数：

* `minutes`：0～59之间的整数，用于设置Date对象date的分钟字段(以本地时间计)

* `second`：可选的整数，在0～59之间，用做date的秒字段的新值(以本地时间计)。 

* `millis`：可选的整数，在0到999之间，用作date的毫秒字段的新值(以本地时间计)。 

返回值：0～59之间的整数，用于设置Date对象date的分钟字段(以本地时间计)。

## Date.setMonth( )：设置Date对象的月份字段和天字段

语法：

```JavaScript
date.setMonth(month)

date.setMonth(month, day)
```
参数：

* `mont``：0(一月)到11(十二月)之间的整数，用于设置Date对象date的月份字段。 注意，月份从0开始编号，而月中的某一天则从1开始编号。

* `day`：可选的整数，在1～31之间，用做date的天数字段的新值(以本地时间计)。 

返回值：调整过的日期的毫秒表示。

## Date.setSeconds( )：设置Date对象的秒字段和毫秒字段

语法：

```JavaScript
date.setSeconds(seconds) 

date.setSeconds(seconds, millis)
```
参数：

* `seconds`：0～59之间的一个整数，用于设置Date对象date的秒字段。

* `millis`：可选的整数，在0～999之间，用做date的毫秒字段的新值(以本地时间计)。

返回值：调整过的日期的毫秒表示。

## Date.setTime( )：以毫秒设置Date对象

语法：`date.setTime(milliseconds)`

参数：`milliseconds`：要设置的日期和时间距GMT时间1970年1月1日午夜之间的毫秒数。

返回值：参数milliseconds。

## Date.setUTCDate( )：设置一个月中的某一天(世界时)

语法：`date.setUTCDate(day_of_month)`

参数：`day_of_month`：要给date设置的一个月中的某一天，用世界时表示。该参数是1～31之间的整数。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCFullYear( )：设置年份、月份和天(世界时)

语法：

```JavaScript


date.setUTCFullYear(year)

date.setUTCFullYear(year, month)

date.setUTCFullYear(year, month, day)
```

参数：

*  `year`：要给date设置的年份值，用世界时表示。该参数应该是含有世纪值的完整年份， 如1999，而不只是缩写的年份值，如99。

* `month`：可选的整数，在0～11之间，用作date的月份字段的新值(以世界时计)。

* `day`：可选的整数，在1～31之间，用作date的天字段的新值(以世界时计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCHours( )	：设置Date对象的小时字段、分钟字段、秒字段和毫秒字段(世界时)

语法：

```JavaScript
date.setUTCHours(hours) 

date.setUTCHours(hours, minutes) 

date.setUTCHours(hours, minutes, seconds) 

date.setUTCHours(hours,minutes, seconds, millis)
```

参数：

* `hours`：要设置的date的小时字段的值，用世界时表示。该参数应该是0(午夜)到23 (晚上11点)之间的一个整数。

* `minutes`：可选的整数，在0～59之间，用作date的分钟字段的新值(以世界时计)。

* `seconds`：可选的整数，在0～59之间，用作date的秒字段的新值(以世界时计)。

* `millis`：可选的整数，在0～999之间，用作date的毫秒字段的新值(以世界时计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCMilliseconds( )：设置Date对象的毫秒字段(世界时)

语法：`date.setUTCMilliseconds(millis)`

参数：`millis`：要设置的date的毫秒字段的值，用世界时表示。该参数是0～999之间的整数。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCMinutes( )：设置Date对象的分钟字段和秒字段(世界时)

语法：

```JavaScript

date.setUTCMinutes(minutes) 

date.setUTCMinutes(minutes, seconds) 

date.setUTCMinutes(minutes, seconds, millis)
```

参数：

* `minutes`：要设置的date的分钟字段的值，用世界时表示。该参数应该是0～59之间的一个整数。

* `seconds`：可选的整数，在0～59之间，用作date的秒字段的新值(以世界时计)。

* `millis`：可选的整数，在0～999之间，用作date的毫秒字段的新值(以世界时计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCMonth( )	：设置Date对象的月份字段和天数字段(世界时)

语法：

```JavaScript
date.setUTCMonth(month) 

date.setUTCMonth(month, day)
```

参数：

* `month`：要设置的date的月份字段的值，用世界时表示。该参数是0(一月)到11(十 二月)之间的整数。注意，月份从0开始编码，而月中的某一天则从1开始编码。

* `day`：可选的整数，在1～31之间，用作date的天字段的新值(以世界时计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setUTCSeconds( )：设置Date对象的秒字段和毫秒字段(世界时)

语法

```JavaScript

date.setUTCSeconds(seconds) 

date.setUTCSeconds(seconds, millis)
```
参数

* `seconds`:要设置的date的秒字段的值，用世界时表示。该参数应该是0～59之间的一个整数。

* `millis`:可选的整数，在0～999之间，用作date的毫秒字段的新值(以世界时计)。

返回值：调整过的日期的内部毫秒表示。

## Date.setYear( )：设置Date对象的年份字段

语法：`date.setYear(year)`

参数：`year`：要设置的Date对象date的年份字段的值，是一个整数。如果这个值在0～99之 间，包括0和99，将给它加上1900，作为1900～1999间的值处理。

返回值：调整过的日期的毫秒表示。

描述：方法`setYear()`可以设置指定的Date对象的年份字段，对于1900～1999之间的年份，带有特殊的行为。

## Date.toDateString( )：返回Date对象日期部分作为字符串

语法：`date.toDateString()`

返回值：date的日期部分的字符串表示，由实现决定，可以读懂，以本地时间表示。

## Date.toGMTString( )：将Date转换为世界时字符串

语法：`date.toGMTString() `

返回值：Date对象date所指定的日期和时间的字符串表示。这个日期在转换成字符串之前由本地时区转换成了GMT时区。

## Date.toLocaleDateString( )：回Date对象的日期部分作为本地已格式化的字符串

语法：`date.toLocaleDateString()`

返回值：date的日期部分的字符串表示，由实现决定，可以读懂，以本地时间表示，根据本地规约格式化。

## Date.toLocaleString( )：将Date转换为本地已格式化的字符串

语法：`date.toLocaleString()`

返回值：Date对象dace指定的日期和时间的字符串表示。该日期和时间用本地时间区表示， 根据本地规约格式化。

用法：

* 方法`toLocaleString()`可以将日期转换成用本地时间区表示的字符串。

* 该方法的日期和时间格式还使用地方规约，所以在不同平台上以及不同国家之间，日期和时间的格式都有所不同。

* 它返回的字符串格式通常都是用户想要的日期和时间格式。

## Date.toLocaleTimeString( )：返回Date对象的时间部分作为本地已格式化的字符串

语法：`date.toLocaleTimeString() `

返回值：date的时间部分的字符串表示，由实现决定，可以读取的，以本地时区表示，根 据本地规约格式化。

## Date.toString( )：将Date转换为字符串

语法：`date.toString() `

返回值：`date`的字符串表示，是人们可以读取的，用本地时间表示。

描述：

* 方法`toStrzng()`返回一个人们可以读取的、由实现决定的日期的字符串表示。

* 它与`toUTCString()`的不同，`toString()`以本地时间表示日期。

* 它与`toLocaleString()`的不同之处在于它不使用地方规约采用的形式表示日期和时间。

## Date.toTimeString( )：返回Date对象日期部分作为字符串

语法：`date.toTimeString() `

返回值：date的时间部分的字符串表示，由实现决定，可以读取，以本地时间表示。

## Date.toUTCString( )：将Date转换为字符串(世界时)

语法：`date.toUTCString() `

返回值：date的字符串表示，可以读取，用世界时表示。

描述：方法`toUTCString()`返回一个人们可以读取的、由实现决定的日期的字符串表示。它以世界时表示。


## Date.UTC( )：将Date规范转换成毫秒数

语法：`Date.UTC(year, month, day, hours, minutes, seconds, ms)`

参数：

* `year`：四位数表示的年份值。如果该参数在0～99之间(包括0和99)，它将加上1900， 作为1900～1999之间的年份处理。

* `month`：月份值，是0(一月)到11(十二月)之间的整数。

* `day`：一个月中的某一天，是1～31之间的整数。注意，该参数的最小值是1，而其他参数的最小值则是0。该参数是可选的。

* `hours`：小时值，是0(午夜)到23(晚上11点)之间的整数。该参数是可选的。

* `minutes`：分钟值，是0～59之间的整数。该参数是可选的。

* `seconds`：是0～59之间的整数。该参数是可选的。

* `ms`：毫秒数。该参数是可选的。

返回值：指定的世界时的毫秒表示。简而言之，该方法返回指定的时间距GMT时间1970年1 月1日午夜的毫秒数。

描述：

* `Date.UTC()`是一种静态方法，它通过构造函数Date()调用，而不是通过某个Date 对象调用

* `Date.UTC()`方法的参数指定日期和时间，它们都是UTC时间，处于GMT时区。指定的UTC时间将转换成毫秒的形式，这样构造函数Date()和方法Date.setTime() 就可以使用它了。

* `Date.UTC()`能接受的日期和时间格式，构造函数Date()也可以接受。区别在于构造函数Date()假定这些参数是本地时间，而Date.UTC()却假定它们是世界时(GMT时间)。

## Date.valueOf( )：将Date转换成毫秒表示

语法：`date.valueOf()`

返回值：date的毫秒表示。返回值和方法`Date.getTime()`返回的值相等。
