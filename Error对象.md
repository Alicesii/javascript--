---
title: Error对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象
img:

---
> Error（错误对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)

## Error：普通异常

构造函数：

```JavaScript

new Error(  )

new Error(message)
```

参数：`message`：提供异常的详细信息的错误消息，可选。

返回值：

* 新构造的Error对象。如果指定了参数message，该Error对象将它作为message属性的值；否则，它将用实现定义的默认字符串作为该属性的值。

* 如果把Error构造函数当作函数调用时不使用new运算符，它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常详细信息的错误消息。该属性存放传递给构造函数的字符串，或实现定义的默认字符串。

* `name`：声明异常类型的字符串。对于Error类的实例和所有子类来说，该属性声明了用于创建实例的构造函数名。

方法：`toString( )`：返回一个表示Error对象的字符串。

描述：

* Error类的实例表示错误或异常，通常与throw语句和try/catch语句一起使用。属性name声明了异常的类型，message属性可提供人们能够读取的异常的详细信息。

* JavaScript解释器从不直接抛出Error对象，而是抛出Error子类(如SyntaxError或RangeError)的实例。

注意：

* ECMAScript标准为Error类定义了`toString()`方法(Error的所有子类都继承了该方法)，但并不要求该方法返回含有message属性的字符串。

* 因此，不能期望`toString()`方法可以把Error对象转换成人们可以读懂的字符串。要把错误消息显 示给用户，应该明确地使用Error对象的name属性和message属性。

举例：

```JavaScript
function factorial(x) {

    if (x < 0) throw new Error("factorial: x must be >= 0");

    if (x <= 1) return 1; else return x * factorial(x-1);

}
```

如果捕捉到了一个异常，可以把异常显示给用户，可以用`Window.alert()`方法：

```JavaScript
try { &*(&/* an error is thrown here */ }

catch(e) {

    if (e instanceof Error) {  // 判断是否为Error或子类的—个实例

        alert(e.name + ": " + e.message);

    }

} 
```

## Error.message：可以读取的错误消息

语法：`error.message`

描述：

* Error对象(或Error子类的实例)的message属性用于存放包含发生的错误或异常的详细情况的字符串，该字符串是人们可以读取的。

* 如果传递给`Error()`构造函数一个消息参数，该消息将成为message属性的值。如果没有消息参数传递给`Error()`参数，Error对象将继承实现为该属性定义的默认值(可能是空串)。

## Error.name：错误的类型

语法：`error.name`

描述：Error对象(或Error子类的实例)的name属性声明了发生的错误或异常的类型。所有Error对象都从它们的构造函数中继承这一属性。该属性的值与构造函数名相同。因此，SyntaxError对象的name属性值为“SyntaxError”，EvalError对象的name属性为“EvalError”。

## Error.toString( )：把Error对象转换成字符串

语法：`error.toString( )`

返回值：实现定义的字符串。它并不要求返回的字符串包含错误名或错误消息。


## EvalError：在不正确使用eval()时抛出

构造函数：

```JavaScript

new EvalError(  )

new EvalError(message)
```

参数：`message`：提供异常的详细信息的错误消息，可选。如果设置了该参数，它将用作EvalError对象的message属性的值。

返回值：

* 新构造的EvalError对象。如果指定了参数message，Error对象将用它作为message 属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果把 EvalError()构造函数当作函数调用且不带有new运算符，它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常的详细信息的错误消息。该属性存放传递给构造函数的字符串，或存放实现定义的默认字符串。

* `name`：声明异常类型的字符串。所有EvalError对象的name属性都继承值“EvalError”。

描述：当在其他名称下调用全局函数eval()时，EvalError类的一个实例就会被抛出。

## SyntaxError：抛出该错误用来通知语法错误

构造函数：

```javascript

new SyntaxError( )

new SyntaxError(message)
```

参数：`message`：提供异常细节的错误消息(可选)。如果设置了该参数，它将作为SyntaxError对象的message属性的值。

返回值：

* 新构造的SyntaxError对象。如果指定了参数message，该Error对象将它作为message 属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果不用new运算符，把SyntaxError()构造函数当作函数调用，它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常细节的错误消息。该属性存放传递给构造函数的字符串，或存放实现定义的默认字符串。

* `name`：声明异常类型的字符串。所有SyntaxEfror对象的name属性都继承值“SyntaxError”。

描述：

* SyntaxError类的一个实例会被抛出以通知JavaScript代码中的语法错误。

* `eval()方法`、`Function()`构造函数和`RegExp()`构造函数都可能抛出这种类型的异常。

## RangeError：在数字超出合法范围时抛出

构造函数：

```JavaScript
new RangeError(  )

new RangeError(message)
```

参数：`message`：可选的错误消息，提供异常的详细情况。如果指定了该参数，它将作为 RangeError对象的message属性的值。

返回值：

* 新构造的RangeError对象。如果指定了参数message，该Error对象把它作为message属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果不用new运算符，把RangeError()构造函数当作函数调用，那么它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常细节的错误消息。该属性存放传递给构造函数的字符串，或实现定义的默认字符串。

* `name`：声明异常类型的字符串。所有RangeError对象的name属性都继承值“RangeError”。

描述：当数字超出合法范围时，RangeError类的一个实例就会被抛出。

# ReferenceError：在读取不存在的变量时抛出

构造函数：

```JavaScript
new ReferenceError( )

new ReferenceError(message)
```

参数：

* `message`：可选的错误消息，提供异常的详细情况。如果指定了该参数，它将作为 ReferenceError对象的message属性的值。

返回值：

* 新构造的ReferenceError对象。如果指定了参数message，该Error对象把它作为 message属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果不用new运算符，把ReferenceError()构造函数当作函数调用，它的行为与使用new运算符调用时一样。

属性

* `message`：提供异常细节的错误消息。该属性存放传递给构造函数的字符串，或实现定义的 默认字符串。

* `name`：声明异常类型的字符串。所有ReferenceError对象的name属性都继承值“ReferenceError”。

描述：在读取一个不存在的变量的值时，ReferenceError类的一个实例就会抛出。

# TypeError：当一个值的类型错误时，抛出该异常

构造函数：

```JavaScript
new TypeError(  )

new TypeError(message)
```

参数：`message`：提供异常细节的错误消息(可选)。如果设置了该参数，它将作为TypeError对象的message属性的值。

返回值：

* 新构造的TypeError对象。如果指定了参数message，该Error对象将它作为message属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果不用new运算符，则把`TypeError()`构造函数当作函数调用，它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常细节的错误消息。该属性存放传递给构造函数的字符串，或存放实现定义的默认字符串。

* `name`：声明异常类型的字符串。所有TypeError对象的name属性都继承值“TypeError”。

描述：

* 当一个值的类型与要求不符时，TypeError类的一个实例就会被抛出。在访问值为 null或undefined的属性时，这种情况经常发生。

* 如果由一个对象(其他类的实例) 调用另一个类定义的方法，或者对于不是构造函数的值使用new运算符时，也会发生这种情况。

* 当调用内部函数或方法时，如果传递的参数多于期望的个数，JavaScript 的实现也允许抛出TypeError异常。

# URIError；由URl的编码和解码方法抛出

构造函数：

```JavaScript
new URIError(  )

new URIError(message)
```

参数：`message`：提供异常细节的错误消息(可选)。如果设置了该参数，它将作为URIError对象的message属性的值。

返回值：

* 新构造的URIError对象。如果指定了参数message,该Error对象将它作为message 属性的值，否则，它将用实现定义的默认字符串作为该属性的值。

* 如果不用new运算符，而把`URIError()`构造函数当作函数调用，它的行为与使用new运算符调用时一样。

属性：

* `message`：提供异常细节的错误消息。该属性存放传递给构造函数的字符串，或存放实现定义的默认字符串。

* `name`：声明异常类型的字符串。所有URIError对象的name属性都继承值“URIError”。

描述：

* 如果指定的字符串含有不合法的十六进制转义序列，则`decodeURI()`或`decodeURIComponent()`方法就会抛出URIError类的实例。

* 如果指定的字符串含有不合法的Unicode替代对，`encodeURI()`或`encodeURIComponent()`方法也会抛出该异常。

