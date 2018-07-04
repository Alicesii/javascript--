---
title: RegExp对象
comments: true
date: 2018-05-31 15:12:11
categories: 博客列表
tags: JavaScript核心对象

---


> RegExp（正则表达式对象）

![ ](http://www.grabsun.com/uploads/images/2012/97/global.jpg)


## RegExp：用于模式匹配的正则表达式

构造函数：`new RegExp(pattern, attributes)`

参数：

* `pattern`：一个字符串，指定了正则表达式的模式或其他正则表达式。

* `attributes`：一个可选的字符串，包含属性“g”、“i”和“m”，分别用于指定全局匹配、区分大小写的匹配和多行匹配。

返回值：一个新的RegExp对象，具有指定的模式和标志。

* 如果参数pattern是正则表达式而不是字符串，那么`RegExp()`构造函数将用与指定的`RegExp`相同的模式和标志创建一个新的`RegExp`对象。

* 如果不用new运算符，将`RegExp()`作为函数调用，那么它的行为与用new运算符调用时一样，只是当pactern是正则表达式时，它只返回pattern，而不再创建一个新的`RegExp`对象。

抛出：

* `SyntaxError`：如果pattern不是合法的正则表达式，或attributes含有“g”、“i”、“m”之 外的字符，抛出该异常。

* `TypeError`：如果pattern是RegExp对象，但没有省略attributes参数，抛出该异常。

实例属性：

* `global`：RegExp对象是否具有性质g。

* `ignoreCase`：RegExp对象是否具有性质i。

* `lastIndex`：上次匹配后的字符位置，用于在一个字符串中进行多次匹配。

* `multiline`：RegExp对象是否具有m性质。

* `source`：正则表达式的源文本。

方法：

* `exec( )`：执行强大的、通用的模式匹配。

* `test( )`：检测一个字符串是否含有某个模式。

描述：`RegExp对象`表示一个正则表达式，它是对字符串执行模式匹配的强大工具。

## RegExp.exec( )：通用的匹配模式

语法：`regexp.exec(string)`

参数：`string`：要检索的字符串。

返回值：一个数组，存放的是匹配的结果。如果没有找到匹配，值为null。

抛出：`TypeError`：调用该方法的对象不是RegExp时，抛出该异常。

描述：

* 在所有的`RegExp`模式匹配方法和`String`模式匹配方法中，`exec()`的功能最强大。它是一个通用的方法，使用起来比`RegExp.test()`、`String.search()`、`String.replace()`和`String.match()`都复杂。

* `exec()`将检索字符串string，从中得到与正则表达式regexp相匹配的文本。如果`exec()`找到了匹配的文本，它就会返回一个结果数组。否则，返回null。

* `exec()`函数返回数组的第0个元素就是与表达式相匹配的文本。第1个元素是与regexp的第一个子表达式相匹配的文本(如果存在)。第2个元素是与regexp的第二个子表达式相匹配的文本，以此类推。

* 通常，数组的length属性声明的是数组中的元素个数。除了数组元素和length属性之外，`exec()`还返回两个属性。index属性声明的是匹配文本的第一个字符的位置。input属性指的就是string。

* 在调用非全局RegExp对象的`exec()`方法时，返回的数组与调用方法`String.match()`返回的方法相同。

* 在调用非全局模式的`exec()`方法时，它将进行检索，并返回上述结果。

* 当`regexp`是一个全局正则表达式时，`exec()`的行为就稍微复杂一些。它在regexp的属性lastlndex指定的字符处开始检索字符串string。当它找到了与表达式相匹配的文本时，在匹配之后，它将把regexp的`lastlndex`属性设置为匹配文本的第一个字符的位置。这就是说，可以通过反复地调用`exec()`方法来遍历字符串中的所有匹配文本。当`exec()`再也找不到匹配的文本时，它将返回null，并且把属性`lastlndex`重置为0。如果在另一个字符串中完成了一次模式匹配之后要开始检索新的字符串，就必须手动地把`lastlndex`属性重置为0。

* 无论regexp是否是全局模式，`exec()`都会将完整的细节添加到它返回的数组中。这就是`exec()`与`string.match()`的不同之处，后者在全局模式下返回的信息要少得多。事实上，在循环中反复地调用`exec()`方法是惟一种获得全局模式的完整模式匹配信息的方法。

举例：

```JavaScript

//可以在循环中使用exec()来检索—个字符串中的所有匹配文本。例如：

var pattern = /\bJava\w*\b/g;

var text = "JavaScript is more fun than Java or JavaBeans!";

var result;

while((result = pattern.exec(text)) != null) {

    alert("Matched `" + result[0] +

          "' at position " + result.index +

          " next search begins at position " + pattern.lastIndex);

}
```
## RegExp.global	：正则表达式是否全局匹配

语法：`regexp.global`

描述：`RegExp对象`的属性`global`是一个只读的布尔值。它声明了给定的正则表达式是否执行全局匹配，如创建它时是否使用了性质g。

## RegExp.ignoreCase：正则表达式是否区分大小写

语法：`regexp.ignoreCase `

描述：`RegExp对象`的属性`ignoreCase`是一个只读的布尔值。它声明了—个给定的正则表达式是否执行区分大小写的匹配，例如创建它时是否使用了性质i。

## RegExp.lastIndex：下次匹配的起始位置

语法：`regexp.lastIndex`

描述：

* `RegExp对象`的属性`lastIndex`是一个可读可写的值。对于设置了g性质的正则表达式来说，该属性存放的是—个整数，它声明了紧接着上次找到的匹配文本的字符的位置。上次匹配的结果是由方法RegExp.exec()或RegExp.test()找到的，它们都以lastIndex属性所指的位置作为下次检索的起始点。这样，就可以通过反复调用这两个方法来遍历一个字符串中的所有匹配文本。注意，不具有性质g和不表示全局模式的RegExp对象不能使用lastlndex属性。

* 由于这一属性是可读可写的，所以只要目标字符串的下一次搜索开始，就可以对它进行设置。当方法exec()或test()再也找不到可以匹配的文本时，它们会自动地把 lastIndex属性重置为0。如果在成功的匹配了某个字符串之后就开始检索另一个字符串，需要明确地把这个属性设为0。

## RegExp.source：正则表达式的文本

语法：`regexp.source`

描述：`RegExp对象`的属性`source`是一个只读的字符串。它存放的是RegExp模式的文本。 该文本中不包括正则表达式直接量使用的定界符，也不包括性质g、i、m。

## RegExp.test( )	：检测一个字符串是否匹配某个模式

语法：`regexp.test(string)`

参数：`string`：要检测的字符串。

返回值：如果字符串string中含有与`regexp`匹配的文本，就返回true，否则返回false。

抛出：`TypeError`：调用该方法的对象不是RegExp时，抛出该异常。

描述：方法`test()`将检测字符串string，看它是否含有与regexp相匹配的文本。如果 string中含有这样的文本，该方法将返回true，否则，返回false。调用RegExp对象r的test()方法，给它传递字符串s，等价于下面的表达式：

```JavaScript
(r.exec(s) != null) 
示例

var pattern = /java/i;

pattern.test("JavaScript");   // 返回 true

pattern.test("ECMAScript");   // 返回 false
```

## RegExp.toString( )：把正则表达式转换成字符串


语法：`regexp.toString(  ) `

返回值：`regexp`的字符串表示。

抛出：`TypeError`：调用该方法的对象不是RegExp时，抛出该异常。

描述：`RegExp.toString()`方法将以正则表达式直接量的形式返回正则表达式的字符串表示。

注意：不允许用实现添加转义序列，这样可以确保返回的字符串是合法的正则表达式直接量。
