﻿---
title: Math对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---

> Math（数学对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Math：算术函数和常量

```JavaScript
//语法
Math.constant 

Math.function( )
```

常量：

* `Math.E`：常量e，自然对数的底数。

* `Math.LN10`：10的自然对数。

* `Math.LN2`：2的自然对数。

* `Math.LOG10E`：以10为底的e的对数。

* `Math.LOG2E`：以2为底的e的对数。

* `Math.PI`：常量∏。

* `Math.SQRT1_2`：2的平方根除以1。

* `Math.SQRT2`：2的平方根。

静态函数：

* `Math.abs( )`：计算绝对值。

* `Math.acos( )`：计算反余弦值。

* `Math.asin( )`：计算反正弦值。

* `Math.atan( )`：计算反正切值。

* `Math.atan2( )`：计算从X轴到一个点的角度。

* `Math.ceil( )`：对一个数上舍入。

* `Math.cos( )`：计算余弦值。

* `Math.exp( )`：计算e的指数。

* `Math.floor( )`：对一个数下舍人。

* `Math.log( )`：计算自然对数。

* `Math.max( )`：返回两个数中较大的一个。

* `Math.min( )`：返回两个数中较小的一个。

* `Math.pow( )`：计算xy。

* `Math.random( )`：计算一个随机数。

* `Math.round( )`：舍入为最接近的整数。

* `Math.sin( )`：计算正弦值。

* `Math.sqrt( )`：计算平方根。

* `Math.tan( )`：计算正切值。

描述：

* Math是一个对象，定义了引用有用的算术函数和常量的属性。Math对象对这些函数和常量进行了分组，使用如下的语法就可以调用它们：

```JavaScript

y = Math.sin(x);

area = radius * radius * Math.PI; 

```

* Math并不像Date和String那样是对象的类。没有Math()构造函数，像`Math.sin()`这样的函数只是函数，不是对象的方法。

## Math.abs( )：计算绝对值

语法：`Math.abs(x) `

参数：`x`：任意数。

返回值：x的绝对值。

## Math.acos( )：计算反余弦值

语法：`Math.acos(x)`

参数：`x`：-1.0 和1.0.之间的数。

返回值：指定的值x的反余弦值。返回的是0到∏之间的弧度值。


## Math.asin( )：计算反正弦值

语法：`Math.asin(x)`

参数：`x`：-1.0 和1.0.之间的数。

返回值：指定的值x的反正弦值。返回的是-∏/2和∏/2之间的弧度值。

## Math.atan( )：计算反正切值

语法：`Math.atan(x)`

参数：`x`：任意数。

返回值：指定的值x的反正切值。返回的是 -∏/2 和∏/2 之间的弧度值。

## Math.atan2( )：计算从x轴到一个点之间的角度

语法：`Math.atan2(y, x)`

参数：

* y：指定点的Y坐标。

* x：指定点的X坐标。

返回值：-∏和 ∏之间的值，是从X轴正向逆时针旋转到点(x，y)时经过的角度。


## Math.ceil( )：对一个数上舍入

语法：`Math.ceil(x) `

参数：`x`：任意数或表达式。

返回值：大于等于x，并且与它最接近的整数。

描述：

* `Math.ceil()`：执行的是向上取整计算，它返回的是大于等于函数参数，并且与之最接近的整数。

* `Math.ceil()`：执行的操作不同于`Math.round()`，`Math.ceil()`总是上舍入，而`Math.round()`可以上舍入或下舍入到最接近的整数。

* `Math.ceil()`：不会将负数舍人为更小的负数，而是向0舍入。

## Math.cos( )：计算余弦值

语法：`Math.cos(x)`

参数：`x`：一个角的弧度值。要把角度转换成弧度,只需把角度值乘以0.017453293 (2∏/360).

返回值：指定的值x的余弦值。返回的是-1.0 和 1.0.

## Math.E	算术常量e

语法：`Math.E`

描述：E代表算术常量e，即自然对数的底数，其值近似于2.71828。

## Math.exp( )：计算ex

语法：`Math.exp(x)`

参数：`x`：数值或表达式，被用作指数。

返回值：e∧x，e 的x次幂。这里e代表自然对数的底数，其值近似为2.71828。

## Math.floor( )：对一个数下舍入

语法：`Math.floor(x)`

参数：`x`：任意的数值或表达式。

返回值：小于等于x，并且与它最接近的整数。

## Math.LN10：算术常loge10

语法：`Math.LN10`

描述：`Math.LN10 is loge2`, 即10的自然对数，其值近似为`2.3025850929940459011`.

## Math.LN2：算术常量loge2

语法：`Math.LN2`

描述：`Math.LN2 is loge2`，即2的自然对数，其值近似为`0.69314718055994528623`.

## Math.log( )：计算一个数的自然对数

语法：`Math.log(x)`

参数：`x`：任何大于0的数值或表达式。

返回值：x的自然对数。

## Math.LOG10E	：算术常量log10e

语法：`Math.LOG10E`

描述：`Math.LOG10E `：表示常量 log10e,t即以2为底数e的对数。其值近似为 `0.43429448190325181667`.

## Math.LOG2E：算术常量log2e

语法：`Math.LOG2E `

描述：`Math.LOG2E` 表示常量 log2e, 即以10为底的e的对数，其值近似为`1.442695040888963387`。

## Math.max( )：返回最大的参数

语法：`Math.max(args...)`

参数：`args...`：0个或多个值。

返回值：参数中最大的值。如果没有参数，返回`-Infinity`。如果有一个参数为NaN，或是不能转换成数字的非数字值，则返回NaN。

## Math.min( )：返回最小的参数

语法：`Math.min(args...)`

参数：`args...`：0个或多个值。

返回值：参数中最小的值。如果没有参数，返回`Infinity`。如果有一个参数为NaN，或是不能转换成数字的非数字值，则返HNaN。

## Math.PI：算术常量PI

语法：`Math.PI`

描述：`Math.PI`表示的是常量∏ 或 pi，即圆的周长和它的直径之比，这个值近似为`3.14159265358979`。

## Math.pow( )：计算xy

语法：`Math.pow(x, y)`

参数：

* `x`：底数。

* `y`：幂数。

返回值：x的y次幂, x^y。

描述：

* `Math.pow()`计算x的y次幂。x和y可以是任意值。但如果结果是虚数或复数，`Math.pow()`将返回NaN。

* 如果x是一个负数，那么y就 应该是一个正整数或是一个负整数。

* 如果指数过大会引起浮点溢出，此时该方法将返回Infinity。

## Math.random( )：返回一个伪随机数

语法：`Math.random( )`

返回值：返回一个0.0 和 1.0之间的一个伪随机数。

## Math.round( )：舍入到最接近的整数

语法：`Math.round(x)`

参数：`x`：任意数。

返回值：与x最接近的数。

描述：`Math.round( )`将把它的参数上舍入或下舍入到与它最接近的整数。对于0.5，它将上舍入。例如，2.5将被舍入为3，-2.5将被舍入为-2。

## Math.sin( )	：计算正弦值

语法：`Math.sin(x)`

参数：`x`：一个以弧度表示的角。将角度乘以0.017453293 (2∏/360)即可转换成弧度。

返回值：x的正弦值。

## Math.sqrt( )：计算平方根

语法：`Math.sqrt(x)`

参数：`x`:大于等于0的数。

返回值：x的平方根。如果x小于0，返回NaN。

## Math.SQRT1_2：算数常量1/√2

语法：`Math.SQRT1_2`

描述：`Math.SQRT1_2`就是常量1/√2，即2的平方根，它的值近似于0.7071067811865476。

## Math.SQRT2：算数常量√2

语法：`Math.SQRT2`

描述：`Math.SQRT2`就是常量 √2，即2的平方根，它的值近似于1.414213562373095。

## Math.tan( )：计算正切值

语法：`Math.tan(x) `

参数：`x`：一个以弧度表示的角。将角度乘以0.017453293 (2∏/360)即可转换成弧度。

返回值：指定的角x的正切值。