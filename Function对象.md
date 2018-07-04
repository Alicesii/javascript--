---
title: Function对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---

> Function（函数对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Function：JavaScript的函数

语法：

```JavaScript
function functionname(argument_name_list) // 函数定义语句
{
    body 
} 

function (argument_name_list) { body } // 未命名的函数直接量

functionname(argument_value_list)      // 函数调用

new Function(argument_names..., body) //构造函数
```
参数：

* `argument_names...`：任意多个字符串参数，每个字符串命名一个或多个要创建的Function对象的参数。

* `body`：一个字符串，指定函数的主体，可以含有任意多条JavaScript语句，这些语句之间用分号隔开，可以给该构造函数引用前面的参数设置的任何参数名。

返回值：新创建的Function对象。调用该函数，将执行body指定的JavaScript代码。

抛出：`SyntaxError`：说明在参数body或某个argument_names参数中存在JavaScript语法错误。

属性：

* `arguments[]`：一个参数数组，元素是传递给函数的参数。反对使用该属性。

* `caller`：对调用当前函数的Function对象的引用，如果当前函数由顶层代码调用，这个属性的值为null。反对使用该属性。

* `length`：在声明函数时指定的命名参数的个数。

* `prototype`：一个对象，用于构造函数，这个对象定义的属性和方法由构造函数创建的所有对象共享。

方法：

* `apply( )`：将函数作为指定对象的方法来调用，传递给它的是指定的参数数组。

* `call( )`：将函数作为指定对象的方法来调用，传递给它的是指定的参数。

* `toString( )`：返回函数的字符串表示。

描述：

* 函数是JavaScript的一种基本数据类型。注意，虽然可以用Function()构造函数创建函数对象， 但这样做效率不高，在大多数情况下，会使用函数定义语句或函数直接量来定义函数。

* 函数主体会被自动地给予一个局部变量arguments，它引用一个Arguments对象。该对象是一个数组，元素是传递给函数的参数值。

## Function.apply( )：将函数作为一个对象的方法调用

语法：`function.apply(thisobj, args)`

参数；

* `thisobj`：调用function的对象。在函数主体中，thisobj是关键字this的值。

* `args`：一个数组，它的元素是要传递给函数function的参数值。

返回值：调用函数function的返回值。

抛出：`TypeError`：如果调用该函数的对象不是函数，或参数args不是数组和Arguments对象，则抛出该异常。

* 描述：`apply()`将指定的函数function作为对象thisobj的方法来调用，传递给它的是存放在数组args中的参数，返回的是调用function的返回值。

* 在函数体内，关键字this引用thisobj对象。

* 参数args必须是数组或Arguments对象。如果想单独指定传递给函数的参数，而不是指定数组元素，请使用`Function.call()`方法。

举例：

```JavaScript
// 在对象上应用默认的Object.toString()方法，

// 该对象用该方法的版本覆盖了它。注意，没有参数

Object.prototype.toString.apply(o);

//使用数组中用来查找最大元素的方法来调用Math.max()

// 注意本例中第一个参数没有什么作用

var data = [1,2,3,4,5,6,7,8];

Math.max.apply(null, data);
```
## Function.arguments[]	：传递给函数的参数

语法：

```JavaScript
function.arguments[i] 

function.arguments.length
```
描述：

* Function对象的arguments属性是一个参数数组，它的元素是传递给函数的参数。只在执行函数时，它才被定义。

* `arguments.1ength`声明的是数组中的元素个数。

## Function.call( )：将函数作为对象的方法调用

语法：`function.call(thisobj, args...)`

参数：

* `thisobj`：调用function的对象。在函数主体中，thisobj是关键字this的值。

* `args...`：任意多个参数，这些参数将传递给函数function。

返回值：调用函数function的返回值。

抛出：`TypeError`：如果调用该函数的对象不是函数，则抛出该异常。

描述：

* `call()`将指定的函数function作为对象thisobj的方法来调用，把参数列表中thisobj后的参数传递给它，返回值是调用函数后的返回值。

* 在函数体内，关键字this引用thisobj对象。

* 如果指定数组中传递给函数的参数，使用`Function.apply()`方法比较好。

举例：

```JavaScript

// 在对象上调用默认的object.toStrlng()方法，该对象用该方法的版本覆盖了自己

// 注意没有参数.

Object.prototype.toString.call(o);
```
## Function.caller：调用当前函数的函数

* 语法：`function.caller`

描述：

* 在JavaScript的早期版本中，Function对象的caller属性是对调用当前函数的函数的引用。如果该函数是从JavaScript程序的顶层调用的，caller的值就为null。该属性只能在函数内部使用(例如，caller属性只有在函数执行时才会有定义)。


## Function.length：已声明的参数的个数

语法：`function.length`

描述：

* 函数的length属性在定义函数时声明已命名的参数的个数。实际调用函数时，传递给它的参数个数既可以比它多，也可以比它少。

## Function.prototype：对象类的原型

语法：`function.prototype`

描述：属性prototype是在函数作为构造函数时使用的。它引用的是作为整个对象类的原型的对象。由这个构造函数创建的任何对象都会继承属性prototype引用的对象的所有属性。

## Function.toString( )	把函数转换成字符


语法：`function.toString( )`

返回值：表示函数的字符串。

抛出：`TypeError`：如果调用该函数的对象不是Function，则抛出该异常。

描述：

* Function对象的方法`toString()`可以以一种与实现相关的方式将函数转换成字符串。 

* 在Netscape实现中，该方法返回一个含有有效JavaScript代码的字符串，即包括关键字function、参数列表和函数的完整主体的代码。