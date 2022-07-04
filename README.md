[TOC]

## 变量

变量是存储值的容器。要声明一个变量，先输入关键字 `let` 或 `var`，然后输入合适的名称：

```javascript
let myVariable; //块级作用域变量
var myVariable; //没有块级作用域
```

什么是块级作用域

```javascript
//花括号包裹的地方视为一块区域，使用let声明则外部无法读取，也叫局部变量。
{
	let b = 3
    var a = 4
}
console.log(b) //无法反问
console.log(a) //4--->可以访问
```

```javascript
//赋值
myVariable = '李雷';
```

## 常量

常量的值是无法（通过重新赋值）改变的，也不能被重新声明。

```javascript
const URL = 1;
URL = 2 //报错 Uncaught TypeError: Assignment to constant variable.at
```

## 数据类型

| 变量    | 解释                                                         | 示例                                                         |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| String  | 字符串（一串文本）：字符串的值必须用引号（单双均可，必须成对）扩起来。 | `let myVariable = '李雷';`                                   |
| Number  | 数字：无需引号。                                             | `let myVariable = 10;`                                       |
| Boolean | 布尔值（真 / 假）： `true`/`false` 是 JS 里的特殊关键字，无需引号。 | `let myVariable = true;`                                     |
| Array   | 数组：用于在单一引用中存储多个值的结构。                     | `let myVariable = [1, '李雷', '韩梅梅', 10];` 元素引用方法：`myVariable[0]`, `myVariable[1]` |
| object  | 对象：JavaScript 里一切皆对象，一切皆可储存在变量里。这一点要牢记于心。 | `let myVariable = document.querySelector('h1');`以及上面所有示例都是对象。 |

## 运算符

可以根据两个值（或变量）产生结果。以下表格中介绍了一些最简单的运算符，可以在浏览器控制台里尝试一下后面的示例。

| 运算符         | 解释                                                         | 符号          | 示例                                                         |
| -------------- | ------------------------------------------------------------ | ------------- | ------------------------------------------------------------ |
| **加**         | 将两个数字相加，或拼接两个字符串。                           | `+`           | `6 + 9;`<br/>`"Hello " + "world!";`                          |
| **减、乘、除** | 这些运算符操作与基础算术一致。只是乘法写作星号，除法写作斜杠。 | `-`,` *`,` /` | **`9 - 3;`<br/>`8 * 2; //乘法在JS中是一个星号`<br/>`9 / 3;`** |
| **赋值运算符** | 为变量赋值（你之前已经见过这个符号了）                       | `=`           | `let myVariable = '李雷';`                                   |
| **等于**       | 测试两个值是否相等，并返回一个 `true`/`false` （布尔）值。   | `===`         | `let myVariable = 3;`<br/>`myVariable === 4; // false`       |
| **不等于**     | 和等于运算符相反，测试两个值是否不相等，并返回一个 `true`/`false` （布尔）值。 | `!==`         | `let myVariable = 3;`<br/>`myVariable !== 3; // false`       |
| **取非**       | 返回逻辑相反的值，比如当前值为真，则返回 `false`。           | `!`           | 原式为真，但经取非后值为 `false`：<br/>`let myVariable = 3;!(myVariable === 3); // false` |

## 条件语句

条件语句是一种代码结构，用来测试表达式的真假，并根据测试结果运行不同的代码。一个常用的条件语句是 `if ... else`。下面是一个示例：

```javascript
let iceCream = 'chocolate';
if (iceCream === 'chocolate') {
  alert('我最喜欢巧克力冰激淋了。');
} else {
  alert('但是巧克力才是我的最爱呀……');
}
```

`if ( ... )` 中的表达式进行测试，用（上文所提到的）等于运算符来比较变量 `iceCream` 与字符串 `'chocolate'` 是否相等。如果返回 `true`，则运行第一个代码块；如果返回 `false`，则跳过第一块直接运行 `else` 之后的第二个代码块。

## 函数

**函数**用来封装可复用的功能。如果没有函数，一段特定的操作过程用几次就要重复写几次，而使用函数则只需写下函数名和一些简短的信息。

```javascript
//基本语法
function 函数名称(参数1，参数2) {
  return '函数返回值';
}
//函数调用
函数名称(传递的参数)
//匿名函数
function (){
    return '返回'
}
```

## 对象

在 JavaScript 中，几乎所有的对象都是 `Object` 类型的实例

```javascript
//声明对象
let o = new Object();
//声明对象
let o  = {
    name:'我的名字',
    age:65,
}
```

## 事件

事件能为网页添加真实的交互能力。它可以捕捉浏览器操作并运行一些代码做为响应。最简单的事件是 [点击事件](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/click_event)，鼠标的点击操作会触发该事件。可尝试将下面的代码输入到控制台，然后点击页面的任意位置：

```javascript
document.querySelector('html').onclick = function() {
    alert('别戳我，我怕疼。');
}
```

将事件与元素绑定有许多方法。在这里选用了`html` 元素，把一个匿名函数（就是没有命名的函数，这里的匿名函数包含单击鼠标时要运行的代码）赋值给了 `html` 的 `onclick (en-US)` 属性。

- 鼠标点击
- 鼠标经过
- 键盘按下
- 等等...