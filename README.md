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

#### 赋值

```javascript
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