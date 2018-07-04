---
title: Boolean对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---
> Boolean（布尔对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Boolean	对布尔值的支持

构造函数：

```JavaScript
new Boolean(value) //构造函数

Boolean(value) //转换函数
```

参数：`value`:由布尔对象存放的值或者要转换成布尔值的值

返回值：

* 当作为一个构造函数(带有运算符new)调用时，`Boolean()`将把它的参数转换成一个布尔值，并且返回一个包含该值的Boolean对象。

* 如果作为一个函数(不带有运算符new)调用的，`Boolean()`只将它的参数转换成一个原始的布尔值，并且返回这个值。

* 0、NaN、null、空字符串""和undefined都将转换成false。

* 其他的原始值，除了false(但包括字符串"false")，以及其他的对象和数组都会被转换成true。

方法：

`toString( )`：根据Boolean对象代表的布尔值返回"true"或"false"。

`valueOf( )`：返回Boolean对象中存放的原始布尔值。

描述：

* 在JavaScript中，布尔值是一种基本的数据类型。

* Boolean对象是一个将布尔值打包的布尔对象。

* Boolean对象主要用于提供将布尔值转换成字符串的`toString()`方法。 

* 当调用`toString()`方法将布尔值转换成字符串时(通常是由JavaScript隐式地调用)，JavaScript会内在地将这个布尔值转换成一个临时的Boolean对象，然后调用这个对象的`toString()`方法。


## Boolean.toString( )	将布尔值转换成字符串

语法：`b.toString( )`

返回值：根据原始布尔值或者Boolean对象b存放的值返回字符串"true"或"false"。

抛出：`TypeError`:如果调用该方法时，对象不是Boolean，则抛出该异常。

## Boolean.valueOf( )	Boolean对象的布尔值

语法：`b.valueOf( )`

返回值：`Boolean`:对象b存放的原始布尔值。

抛出：`TypeError`:如果调用该方法时，对象不是Boolean，则抛出该异常。