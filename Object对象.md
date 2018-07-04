---
title: Object对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象

---

> Object(对象超类)

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Object：含有所有JavaScript对象的特性的超类

构造函数形式

* 不带参数的形式：`new Object(  ) `

* 带参数的形式：`new Object(value)`

参数说明：`value`：可选的参数，声明了要转换成Number对象、Boolean对象或String对象的原始值(即数字、布尔值或字符串)。

返回值：如果没有给构造函数传递value参数，那么它将返回一个新创建的Object实例。如果指定了原始的value参数，构造函数将创建并返回原始值的包装对象，即Number对象、Boolean对象或String对象。

属性：`constructor`：对一个JavaScript函数的引用，该函数是对象的构造函数。

方法:

* `hasOwnProperty( )`：检查对象是否有局部定义的(非继承的)、具有特定名字的属性。

* `isPrototypeOf( )`：检查对象是否是指定对象的原型。

* `propertyIsEnumerable( )`：检查指定的属性是否存在，以及是否能用for/in循环枚举。

* `toLocaleString( )`：返回对象地方化的字符串表示。该方法的默认实现只调用toString()方法，但子类可以覆盖它，提供本地化。

* `toString( )`：返回对象的字符串表示。Object类提供的该方法的实现相当普通，并且没有提供更多有用的信息。Object的子类通过定义自己的toString()方法覆盖了这一方法(toString()方法能够生成更有用的结果)。


* `valueOf( )`：返回对象的原始值(如果存在)。对于类型为Object的对象，该方法只返回对象自身。Object的子类(如Number和Boolean)覆盖了该方法，返回的是与对象相关的原始数值。

## Object.constructor：对象的构造函数

语法：`object.constructor`

描述：对象的`constructor`属性引用了该对象的构造函数。

举例：如果用`Array()`构造函 数创建一个数组，那么`a.constructor`引用的就是Array

```javascript

a = new Array(1,2,3);   // 创建一个对象

a.constructor == Array  //计算结果为true
```

用途：`constructor`属性常用于判断未知对象的类型。给定了一个未知的值，就可以使用typeof运算符来判断它是原始的值还是对象。如果它是对象，就可以使用constructor属性来判断对象的类型。

举例：判断一个给定的值是否是数组：

```javascript
function isArray(x) {

    return ((typeof x == "object") && (x.constructor == Array));

} 
```

**注意:**

虽然这种方法适用于JavaScript核心语言的内部对象，但对于“主对象”，如Window这样的客户端JavaScript对象，这种方法就不一定适用了。Object.toString()方法的默认实现提供了另一种判断未知对象类型的方法。


##  Object.hasOwnProperty( )：检查属性是否被继承

语法：`object.hasOwnProperty(propname)`

参数：`propname`：一个字符串，包含object的属性名。

返回值：如果object有propname指定的非继承属性，则返回true。如果object没有名为 propname指定的属性，或者它从原型对象继承了这一属性，则返回false。

描述：JavaScript对象既可以有自己的属性，又可以从原型对象继承属性。 

用途：`hasOwnProperty()`方法提供了区分继承属性和非继承的局部属性的方法。

举例：检查属性是否被继承

```javascript
var o = new Object(  );          // 创建对象

o.x = 3.14;                      // 定义非继承的局部属性y

o.hasOwnProperty("x");           // 返回 true: x 是O的局部属性

o.hasOwnProperty("y");           // 返回 false: o 没有属性y

o.hasOwnProperty("toString");    // 返回 false: toString属性是继承的
```

## Object.isPrototypeOf( )：一个对象是否是另一个对象的原型

语法：`object.isPrototypeOf(o)`

参数：`o`：表示任意对象。

返回值：如果object是o的原型，则返回true。如果o不是对象，或者object不是o的原型，则返回false。

描述：JavaScript对象继承了原型对象的属性。一个对象的原型是通过用于创建并初始化该对象的构造函数的prototype属性引用的。

用途：`isPrototypeOf()`方法提供了判断一个对象是否是另一个对象原型的方法，该方法可以用于确定对象的类。

举例：检查一个对象是否是另一个对象的原型

```javascript
var o = new Object(  );                          // 创建一个对象

Object.prototype.isPrototypeOf(o)                // true: o 是一个对象

Function.prototype.isPrototypeOf(o.toString);    // true: toString 是一个函数

Array.prototype.isPrototypeOf([1,2,3]);          // true: [1,2,3] 是一个数组


//下面是执行同样测试的另一种方法

(o.constructor == Object);  // true: o was created with Object(  ) constructor

(o.toString.constructor == Function);  // true: o.toString is a function



//原型则对象本身于原型对象。下面的调用返回true

//说明函数继 Function.prototype和Object.prototype属性.

Object.prototype.isPrototypeOf(Function.prototype);
```

## Object.propertyIsEnumerable( )：是否可以通过for/in循环看到属性

语法：`object.propertyIsEnumerable(propname)`

参数：`propname`一个字符串，包含object原型的名字。

返回值：如果object具有名为propname的非继承属性，而且该属性是可枚举的(即用for/in循环可以枚举出它)，则返回true。

描述：用for/in语句可以遍历一个对象“可枚举”的属性。但并非—个对象的所有属性都是可枚举的，通过JavaScript代码添加到对象的属性是可枚举的，而内部对象的预定义属性(如方法)通常是不可枚举的。

用途：`propertylsEnumerable()`方法提供了区分可枚举属性和不可枚举属性的方法。

**注意:**

ECMAScript标准规定，propertyIsEnumerable()方法不检测原型链，这意味着它只适用于对象的局部属性，不能检测继承属性的可枚举性。

举例：是否可以通过for/in循环看到属性

```javascript
var o = new Object(  );                // 创建一个对象

o.x = 3.14;                            // 定义—个属性

o.propertyIsEnumerable("x");           // true属性x是局部的、可枚举的

o.propertyIsEnumerable("y");           //false：o没有属性y

o.propertyIsEnumerable("toString");    //false：toStrlng属性是继承的

Object.prototype.propertyIsEnumerable("toString");  // false: 枚举的
```

## Object.toLocaleString( )：返回对象的本地字符串表示

语法：`object.toString( )`

返回值：表示对象的字符串。

描述：该方法用于返回对象的字符串表示，本地化为适合本地的形式。

用途：Object类提供的默认的`toLocaleString()`方法只调用`toString()`方法，返回非本地化的字符串。但其他类(包括Array、Date和Number)定义了自己的`toLocaleString()`版本，指定本地化字符串的转换。在定义自己的类时，也可以覆盖该方法。

## Object.toString( )：定义一个对象的字符串表示

语法：`object.toString( )`

返回值：表示对象的字符串。

描述：这里的方法`toString()`并不是在JavaScript程序中经常显示调用的那个`toString()`方法。它是在对象中定义的一个方法，当系统需要把对象转换成字符串时就会调用它。

用途:

* 当在字符串环境中使用对象时，JavaScript系统就会调用toString()方法把那个对象转换成字符串。

举例1：假定—个函数期望得到的参数是字符串，那么把对象传递给它时，系统就会将这个对象转换成字符串：`alert(my_object)`

举例2：在用运算符“+”连接字符串时，对象也会被转换成字符串：`var msg = 'My object is: ' + my_object; `

* 调用方法`toStrlng()`时不给它传递任何参数，它返回的应该是一个字符串。要使这个字符串有用，它的值就必须以调用`toString()`方法的对象的值为基础。

* 当用JavaScript自定义一个类时，为这个类定义一个`toString()`方法很有用。如果没有给它定义toString()方法，那么这个对象将继承Object类的默认toString()方法。这个方法返回的字符串形式如下：
`[object class] `
这里，class是一个对象类，其值可以是“Object”、“String”、“Number”、“Function”、 “Window”、“Document”，等等。这种行为有时对确定未知对象的类型或类有用。但由于大多数对象都有自定义的tostring()版本，所以必须明确地对对象o调用 Object.toString()，语法格式为`Object.prototype.toString.apply(o)`；

**注意:**

这种识别未知对象的方法只适用于内部对象。如果你定义了自己的对象类，那么它的类是“Object”。在这种情况下，可以用Obiect.constructor属性获取更多有关对象的信息。

* 在调试JavaScript程序时，toString()方法非常有用，使用它可以输出对象，查看它们的值。因此，为你创建的每个对象类都定义toString()方法很有用。

* 虽然`tostring()`方法通常由系统自动调用，但你也可以自己调用它。

举例3：在JavaScript不能自动把对象转换成字符串的环境中，可以明确地调用toString()方法来实现这一点：

```javascript
y = Math.sqrt(x);       // 计算一个数

ystr = y.toString(  );  // 转换为—个字符串
```

注意:在这个例子中，数字具有内部的toStrlng()方法，可以用该方法进行强制性的转换。

* 在其他的环境中，即使JavaScript可以自动地进行转换，你也可以调用toString()方法，因为对toString()的明确调用可以使代码更加清晰：`alert(my_obj.toString(  ))`；

## Object.valueOf( )：指定对象的原始值

语法：`object.valueOf( )`

返回值：与对象object相关的原始值(如果存在)。如果没有值与object相关，则返回对象自身。

描述：

* 对象的valueOf()方法返回的是与那个对象相关的原始值(如果这样的值存在)。对于类型为Object的对象来说，由于它们没有原始值，因此该方法返回的是这些对象自身。

* 对于类型为Number的对象，valueOf()返回该对象表示的原始数值。同样，对于Boolean对象来说，该方法返回与对象相关的布尔值。对于String对象来说，返回与对象相关的字符串。

* 其实，几乎没有必要自己调用`valueOf()`s方法。在期望使用原始值的地方，JavaScript会自动地执行转换。

* 事实上，由于方法valueOf()是被自动调用的，因此要分辨究竟是原始值还是与之相应的对象非常困难。虽然使用typeof运算符可以显示字符串和String对象之间的区别，但在实际应用中，它们在JavaScript代码中的作用是一样的。

* `Number对象`、`Boolean对象`和`String对象`的valueOf()方法可以将这些包装对象转换成它们表示的原始值。在调用构造函数Obioct()时，如果把数字、布尔值或字符串作为参数传递给它，它将执行相反的操作，即将原始值打包成相应的对象。几乎在所有的环境中，JavaScript都可以自动地实现原始值和对象之间的转换，所以一般说来没有必要用这种方法调用构造函数Object()。

* 在某些环境中，你可以为自己的对象定制一个valueOf()方法。例如，你可以定义一个JavaScript对象来表示复数(即一个实数加一个虚数)。作为这个对象的一部分,要给它定义执行复数的加法、乘法等其他运算的方法。不过，还有一种功能是你想要的,即像处理常规实数一样处理复数，舍弃它的虚数部分。

举例：

```javascript
Complex.prototype.valueOf = new Function("return this.real");

```

有了这个为Complex对象定义的`valueOf()`方法，就可以把复数对象传递给方法`Math.sqrt()`它将计算复数的实数部分的平方根。.

