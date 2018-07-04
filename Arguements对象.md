---
title: Arguements对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---
> Arguments（函数参数对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## arguments[ ]：函数参数的数组

语法：`arguments`

描述：`arguments[]`数组只在函数体内定义。在函数体内，arguments引用该函数的 Arguments对象。该对象有带编号的属性，并作为一个存放传递给函数的所有参数的数组。标识符arguments本质上是一个局部变量，在每个函数中都会被自动声明并 初始化。它只在函数体中才能引用Arguments对象，在全局代码中没有定义。

## Arguments：一个函数的参数和其他属性

语法：

```javascript

arguments

arguments[n]
```

元素：Arguments对象只在函数体中定义。虽然技术上说来，它不是数组，但Arguments对 象有带编号的属性，这些属性可以作为数组元素，而且它有length属性，该属性声明了数组元素的个数。它的元素是作为参数传递给函数的值。元素0是第—个参数， 元素1是第二个参数，以此类推。所有作为参数传递的值都会成为Arguments对象的数组元素，无论函数声明中是否有这些参数的名字。

属性：

* `callee`对当前正在执行的函数的引用。

* `length`传递给函数的参数个数，同时也是Arguments对象中的数组元素个数。

描述：

* 当一个函数被调用时，会为该函数创建一个`Arguments`对象，局部变量`arguments`也 会自动地初始化以便引用那个`Arguments`对象。`Arguments`对象的主要用途是提供一种方法，用来确定传递给函数的参数个数并且引用未命名的参数。

* 除了数组元素和属性`length`之外，属性`callee`可以使未命名的函数引用自身。大多数情况下，可以将`Arguments`对象看做是具有`callee`属性的数组。但它不是`Array`类的实例，`Arguments.1ength`属性没有`Array.1ength`属性的专有行为，所以不能用它来改变数组的大小。

* `Arguments`对象有一个非常特殊的特性。当函数具有命名的参数时，`Arguments`对象的数组元素是存放函数参数的局部变量的同义词。

* `Arguments`对象和参数名提供了引用同一个变量的两种不同方法。用参数名改变参数值，会改变用`Arguments`对象得到的值，改变用`Arguments`对象得到的参数值，也会改变用参数名得到的值。

## Arguments.callee	当前正在运行的函数

语法：`arguments.callee`

描述：属性arguments.callee引用当前正在运行的函数。它给未命名的函数提供了一种自我引用的方式。该属性只在函数体内被定义。

举例

```javascript
//一个未命名的函数直接量使用callee属性引用它自身
// 以便它能够递归
var factorial = function(x) {

    if (x < 2) return 1;

    else return x * arguments.callee(x-1);

}
var y = factorial(5);  // 返回 120
```

## Arguments.length	传递给函数的参数的个数

语法：`arguments.length`

描述：`Arguments`对象的属性`length`声明了传递给当前函数的参数的个数。该属性只在函数体内被定义。

注意：这个属性声明的是实际传递给函数的参数个数，而不是期望传递的参数个数。还要注意该属性不具备`Array.length`属性的专有行为。

举例：

```javascript

// 使用Arguments对象来检查是否正确传递了#参数

function check(args) {

    var actual = args.length;           //参数的实际个数

    var expected = args.callee.length;  //期望的参数个数

    if (actual != expected) {           //如果他们不匹配，则抛出异常

        throw new Error("Wrong number of arguments: expected: " +

                         expected + "; actually passed " + actual);
    }
```

