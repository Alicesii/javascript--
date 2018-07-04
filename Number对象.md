---
title: Number对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:
---

> Number（数字对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)


## Number：对数字的支持

构造函数：

```JavaScript
new Number(value)

Number(value)
```
 
参数：`value`：要创建的Number对象的数值，或是要转换成数字的值。

返回值：

* 当Number()和运算符new一起作为构造函数使用时，它返回一个新创建的Number对象。

* 如果不用new运算符，把Number()作为一个函数来调用，它将把自己的参数转换成一个原始的数值，并且返回这个值(如果转换失败，返回NaN)。

常量：

* `Number.MAX_VALUE`：可表示的最大的数。

* `Number.MIN_VALUE`：可表示的最小的数。

* `Number.NaN`：非数字值。

* `Number.NEGATIVE_INFINITY`：负无穷大；溢出时返回该值。

* `Number.POSITIVE_INFINITY`：正无穷大；溢出时返回该值。

方法：

* `toString( )`：把数字转换成字符串，使用指定的基数。

* `toLocaleString( )`：把数字转换成字符串，使用本地数字格式规约。

* `toFixed( )`：把数字转换成字符串，结果的小数点后有指定位数的数字。

* `toExponential( )`：把数字转换成字符串，结果采用指数计数法，小数点后有指定位数的数字。

* `toPrecision( )`：把数字转换成字符串，结果中包含指定位数的行效数字。采用指数计数法或定点计数法，由数字的大小和指定的有效数字位数决定采用哪种方法。

描述：

* 在JavaScript中，数字是—种基本的数据类型，在必要时会自动地进行原始数据和对象之间的转换。

* 构造函数`Number()`可以不与运算符new—起使用，而直接作为转换函数来使用。 以这种方式调用`Number()`时，它会把自己的参数转换成一个数字，然后返回转换后的原始数值(或NaN)。


* 构造函数`Number()`通常还用作5个有用的数字常量的占位符，这5个有用的数字常量分别是可表示的最大的数、可表示的最小的数、正无穷大、负无穷大和特殊的非数 字值。

注意：构造函数`Number()`的数字常量是自身的属性，而不是单独的Number对象的属性。

举例：

```JavaScript

//例如：可以采用如下的形式使用属性MAX_VALUE：

var biggest = Number.MAX_VALUE 

//但是却不能使用：

var n = new Number(2);

var biggest = n.MAX_VALUE 
```

## Number.MAX_VALUE	：最大数值

语法：`Number.MAX_VALUE`

描述：`Number.MAX_VALUE`是JavaScript中可表示的最大的数。它的值近似为1.79E+30

## Number.MIN_VALUE：最小数值

语法：`Number.MIN_VALUE`

描述：`Number.MIN_VALUE`是JavaScript中可表示的最小的数(接近0，但不是负数)。它的值近似为5E-324.

## Number.NaN：特殊的非数字值

语法：`Number.NaN `

描述：

* `Number.NaN`是一个特殊值，说明某些算术运算(如求负数的平方根)的结果不是数字。

* 方法`parseInt()`和`parseFloat()`在不能解析指定的字符串时就返回这个值。 

* 对于一些常规情况下返回有效数字的函数，也可以采用这种方法，用`Number.NaN`说明它的错误情况。

* JavaScript以NaN的形式输出Number.NaN。注意，NaN与其他数值进行比较的结果 总是不相等的，包括它自身在内。因此，不能通过与Number.NaN比较来检测一个值是不是数字，而只能调用函数isNaN()来比较。

## Number.NEGATIVE_INFINITY	：负无穷大

语法：`Number.NEGATIVE_INFINITY `

描述：

* 属性`Number.NEGATIVE_INFINITY`是一个特殊值，它在算术运算或函数生成了一个比JavaScript能表示的最小的数还小的数(也就是比`Number.MIN_VALUE`还小的数)时返回。

* JavaScript显示`NEGATIVE_INFINITY`时使用的是Infinity。这个值的算术行为和无穷大非常相似。例如，任何数乘无穷小结果仍为无穷小，任何数被无穷小除结果为0。 

## Number.POSITIVE_INFINITY：正无穷大

语法：`Number.POSITIVE_INFINITY`

描述：

* 属性`Number.POSITIVE_INFINITY`是一个特殊值，它在算术运算或函数生成了一个比JavaScript能表示的最大的数还大的数(也就是比`Number.MAX_VALUE`还大的数)时返回。注意，当数字向下溢出或`比Number.MIN_VALUE`还小时，JavaScript将它们转换成零。

* JavaScript显示`POSITIVE_INFINITY`时使用的是Infinity。这个值的算术行为和无穷大非常相似。例如，任何数乘无穷大结果仍为无穷大，任何数被无穷大除结果为0。


## Number.toExponential( )	：用指数计数法格式化数字

语法：`number.toExponential(digits)`

参数：`digits`：小数点后的数字位数，值在0～20之间，包括0和20，有些实现可能支持更大的数值范围。

返回值：`number`的字符串表示，采用指数计数法，即小数点之前有一位数字，小数点后有digits位数字。该数字的小数部分将被舍人，必要时用0补足，以便它达到指定的 长度。

抛出：

* `RangeError`：digits太小或太大时抛出的异常。0～20之间(包括0和20)的值不会引发RangeError。有些实现允许支持更大范围或更小范围内的值。

* `TypeError`：调用该方法的对象不是Number时抛出的异常。

举例：

```JavaScript

var n = 12345.6789;

n.toExponential(1);     // 返回 1.2e+4

n.toExponential(5);     // 返回 1.23457e+4

n.toExponential(10);    // 返回 1.2345678900e+4

n.toExponential(  );    // 返回 1.23456789e+4
```

## Number.toFixed( )：采用定点计数法格式化数字

语法：`number.toFixed(digits)`

参数：`digits`：小数点后的数字位数，是0～20之间的值，包括0和20，有些实现可以支持更 大的数值范围。如果省略了该参数，将用0代理。

返回值：`number`的字符串表示，不采用指数计数法，小数点后有固定的digics位数字。如果必要，该数字会被舍入，也可以用0补足，以便它达到指定的长度。如果number大于le+21，该方法只调用`Number.toString()`，返回采用指数计数法表示的字符串。

抛出：

* `RangeError`：digits太小或太大时抛出的异常。0～20之间(包括0和20)的值不会引发 RangeError。有些实现支持更大范围或更小范围内的值。

* `TypeError`：调用该方法的对象不是Number时抛出的异常。

举例：

```JavaScript
var n = 12345.6789;

n.toFixed(  );            // 返回 12346，注意舍入，没有小数部分

n.toFixed(1);             // 返回 12345.7，注意舍入

n.toFixed(6);             // 返回 12345.678900，注意补零

(1.23e+20).toFixed(2);    // 返回 123000000000000000000.00

(1.23e-10).toFixed(2)     // 返回 0.00
```
## Number.toLocaleString( )：把数字转换成本地格式的字符串

语法：`number.toLocaleString( )`

返回值：数字的字符串表示，由实现决定，根据本地规范进行格式化。可能影响到小数点或千分位分隔符采用的标点符号。

抛出：`TypeError`：调用该方法的对象不是Number时抛出的异常。

## Number.toPrecision( )：格式化数字的有效位

语法：`number.toPrecision(precision)`

参数：`precision`：返回的字符串中的有效位数，是1～21之间(包括1和21)的值。有些实际允许有选择地支持更大或更小的precision。如果省略了该参数，将调用方法toString()，而不是把数字转换成十进制的值。

返回值：`number`的字符串表示，包含precision个有效数字。如果precision足够大，能够包括number整数部分的所有数字，那么返回的字符串将采用定点计数法。否则，采用指数计数法，即小数点前有一位数字，小数点后有precision-l位数字。必要时， 该数字会被舍入或用0补足。

抛出：

* `RangeError`：digits太小或太大时抛出的异常。1～21之间(包括1和21)的值不会引发 RangeError。有些实现支持更大范围或更小范围内的值。

* `TypeError`：调用该方法的对象不是Number时抛出的异常。

举例：

```JavaScript
var n = 12345.6789;

n.toPrecision(1);   // 返回 1e+4

n.toPrecision(3);   // 返回 1.23e+4

n.toPrecision(5);   // 返回 12346:注意舍入

n.toPrecision(10);  // 返回 12345.67890:注补L零
```

## Number.toString( )：将—个数字转换成字符串

语法：`number.toString(radix)`

参数：`radix`：可选的参数，指定表示数字的基数，是2～36之间的整数。如果省略了该参数，使用基数10。但要注意，如果该参数是10以外的其他值，则ECMAScript标准 允许实现返回任意值。

返回值：数字的字符串表示。

抛出：`TypeError`：调用该方法的对象不是Number时抛出的异常。

描述：`Number`对象的方法`toString()`可以将数字换成字符串。当省略了radix参数或指定它的值为10时，该数字将被转换成基数为10的字符串。如果radix是其他值，该方法将返回由实现定义的字符串。

## Number.valueOf( )：返回原始数值

语法：`number.valueOf( )`

返回值：`Number`对象的原始数值。几乎没有必要明确调用该方法。

抛出：`TypeError`：调用该方法的对象不是Number时抛出的异常。