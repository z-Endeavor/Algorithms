# JavaScript基础



### 什么是JavaScript？

- **高级解释语言**
  - 高级：很多抽象。
  - 解释：不是直接执行，不需通过编译器运行，是被**解释的脚本语言**。
- 遵从ECMAScript规范
- **多范式**（多种编写代码方式）
  - 面向对象编程
  - 函数式编程
- 运行在**浏览器和客户端**的语言，也可以运行**服务器端**（Node.js）



### 为何要学JavaScript？

- 运行在**浏览器**的编程语言
- 可以使用 JS 框架构建**交互式页面**
- 用于构建非常快速的**服务器端**和**全栈应用程序**
- 用于**移动开发**（React Native、NativeScript、lonic）
- 用于**桌面应用开发**（Electron JS）





## 变量

#### var - 全局变量

全局作用域。

#### let - 局部变量

可以重新赋值。

#### const - 常量

不能重新赋值



## 数据类型

### String - 字符串

```javascript
const name = 'Kevin';
```

#### 字符串拼接

```javascript
// 可以用 ‘+’ 拼接
console.log('My name is ' + name + ' and I am ' + age);
```

#### 模板字符串(ES6)

```javascript
// 可以用反引号 ``、$符号和大括号写入变量名
console.log(`My name is ${name} and I am ${age}`);
```

#### 字符串属性和方法

- **属性**（没有括号）
  - 长度：s.length
- **方法**（有括号）
  - 变大/小写：s.toUpperCase() / s.toLowerCase()
  - 子字符串：s.substring(0, 5)
  - 分割到数组：s.split(',')
  - 获取指定值的索引：s.indexOf('.')
  - 提取某个字符串的一部分: s.slice(BeginIndex[, endIndex])



#### nubmer - 数值

```javascript
const age = 30;
const rating = 4.5;
```

#### boolean - 布尔

```javascript
const isCool = true;
```

#### null - 空

```javascript
const x = null;
```

#### undefined - 未定义

```javascript
const y = undefined;
let z;
```



> **typeof**：可以判断变量的数值类型



## 数组

包含多个变量值。

JS中同一个数组**可以保存不同类型值**。

### 创建数组

#### 直接声明创建

```javascript
// 数组结构体创建方式
const numbers = new Array(1,2,3,4,5);

// 变量创建方式
const fruits = ['apples', 'oranges', 'pears', 10, true];
```

#### 数组方法创建

- **Array.fill(value[, start[, end]]):** 用一个**固定值**填充一个数组中从起始索引到终止索引内的**全部元素**。
- **Array.from(arrayLike[, mapFn]) :** 对一个**类似数组或可迭代对象**创建一个新的、浅拷贝的数组实例。如`Array.from([1, 2, 3], x => x + x));`

### 数组元素操作 ☆

**访问：**通过下标访问。

**添加元素：**

- 可以直接通过下标在末尾添加，`fruits[5] = 'grapes'`。
- 可以通过push方法添加

  - 在末尾：`fruits.push('mangos')`。
  - 在开头：`fruits.unshift('strawberries')`。

**删除元素：**可以通过pop方法在末尾删除，`fruits.pop()`。

**获取某个元素的索引：**`fruits.indexOf`。

**将数组元素连接成一个字符串：**`Array.join('')`

**删除或替换现有元素或者原地添加新的元素**：`Array.splice(start[, deleteCount[, item1[, ...]]])`

> const类型的数组可以在数组中添加元素，可以操作它，也可以使用方法，**唯一不能做的是初始化为空**（`fruits = []`）

### 数组操作

**判断是否为数组**：`Array.isArray(fruits)`。

**获取数组的子串：**`Array.slice([begin[, end]])` 。

>  `slice()` 返回一个**新的数组对象**，这一对象是一个由 `begin` 和 `end` 决定的原数组的**浅拷贝**（包括 `begin`，不包括`end`）不改变原数组。

**数组排序：**`Array.sort([compareFunction])` 。

> `sort()` 默认将数组元素转换为字符串比较，可以通过比较函数来定义排序，如 **`sort((a, b) => { return a-b; })` 数组将会比较数字并升序排列**。



## 对象字面量

对象就是**键值对**。

创建对象中可以有变量、数组、对象。

```javascript
const person = {
	firstName: 'Kevin',
	lastName: 'Zhang',
	hobbies: ['music', 'movies', 'sports'],
	address: {
		street: '50 main st',
		city: 'WenZhou',
		country: 'China'
	}
}
```

对象可以**解构赋值**，重新<u>定义新的变量去取出对象中属性值</u>。（ES6）

```javascript
const { firstName, lastName, address: { city } } = person;

// console.log(firstName);
// console.log(city);
```

添加新的属性，可以直接添加。

```javascript
person.email = 'zkc@example.com';
```

### 对象数组

对象数组也是很常用的形式。

```javascript
const todos = [
	{
		id: 1,
		text: 'Take out trash',
		inCompleted: true
	},
	{
		id: 2,
		text: 'Meeting with boss',
		inCompleted: true
	},
	{
		id: 3,
		text: 'Dentist appt',
		inCompleted: false
	}
]
```



## JSON

JSON是一种**数据格式**，与对象语法很相似。在全栈开发中广泛使用，像服务发送数据会用到JSON格式，也是接受JSON格式。

JSON与对象语法很相似，并且可以直接用 `JSON.stringify(object name)`直接转换。

```javascript
const todoJSON = JSON.stringify(todos);

/* 
属性名和字符串都为双引号！

const todoJSON = [
	{
		"id": 1,
		"text": "Take out trash",
		"inCompleted": true
	},
	{
		"id": 2,
		"text": "Meeting with boss",
		inCompleted: true
	},
	{
		"id": 3,
		"text": "Dentist appt",
		"inCompleted": false
	}
]
*/
```



## 循环

### For循环

```javascript
for (let i = 0; i < 10; i++) {
	// code
}
```

### While循环

```javascript
// 在循环外设置变量
let i = 0;
while (i < 10) {
	// code
    i++;
}
```

### 数组循环

```javascript
// for循环
for (let i = 0; i < todos.length; i++) {
	// todos[i].text ...
}

// for of 循环
for(let todo of todos) {
    // todo ...
}

```

#### 高阶数组方法

用于迭代数组，参数是函数（可以用箭头函数）。

不同方法可以链接起来用，利用函数式编程的思想，可以更强大。

```javascript
// forEach 循环 
todos.forEach(function(todo) {
	// todo ...
})

todos.forEach(todo => {
    // todo ...
})

// map 从数组中创建新数组
const todoText = todos.map(function(todo) {
	return todo.text;
})

// filter 根据条件创建新数组
const todoCompleted = todos.filter(function(todo) {
	return todo.isCompleted === true;
})
```



## 条件

### if else语句 

```javascript
if (x == 10) {
	// code ...
} else if(x > 10){
    // code ...
} else {
    // code ...
}
```

### 三元操作符

```javascript
const x = 10;

const color = x > 10 ? 'red' : 'blue';
```

### switch语句

```javascript
switch(color) {
	case 'red':
		// code...
		break;
	case 'blue':
		// code...
		break;
	default:
		// code...
		break;
}
```



## 函数

```javascript
function addNums(num1, num2) {
	// num1 + num2
}

addNums(5, 4);  // 9
addNums();		// NaN
```

可以给函数**默认参数设置值**，在有传参的情况下也会重写默认值。

```javascript
function addNums(num1 = 1, num2 = 2) {
	// num1 + num2
}

addNums();		// 3
addNums(5, 5)	// 10
```

### 箭头函数

```javascript
const addNums = (num1 = 1, num2 = 2) => {
	return num1 + num2;
}

// 不写{} ,就不写return
const addNums = (num1 = 1, num2 = 2) => num1 + num2;

// 若一个参数可以不写()
const addNums = num1 => num1 + 5;
```



## 面向对象编程OOP

可以通过构造函数来构造对象。

- 用**原型**实现构造函数

```javascript
// 构造函数
function Person (firstName, lastName, dob) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.dob = new Date(dob);
    // 给对象添加函数
    this.getBirthYear = function(){
        return this.dob.getFullYear();
    } 
    this.getFullName = function() {
        return `${this.firstName} ${this.lastName}`;
    }
}
// 可以在原型中添加方法和属性，适合不是每个对象都添加的方法和属性
// 在原型中给对象添加函数
Person.prototype.getBirthYear1 = function() {
	return this.dob.getFullYear();
}
Person.prototype.getFullName1 = function() {
    return `${this.firstName} ${this.lastName}`;
}

// 实例化对象
const person1 = new Person('Kevin', 'Zhang', '4-18-1998');
const person2 = new Person('Kevin2', 'Zhang2', '4-18-1999');

```

- ES6的**类**

```javascript
class Person {
    constructor(firstName, lastName, dob) {
        this.firstName = firstName;
    	this.lastName = lastName;
    	this.dob = new Date(dob);
    }
    
    getBirthYear(){
        return this.dob.getFullYear();
    } 
    getFullName() {
        return `${this.firstName} ${this.lastName}`;
    }
    
}
```



## DOM文档树结构

**window对象**：是浏览器的父对象，一般也可以不写。

### 单元素选择器

- **getElementById：**通过ID来获取元素
- **querySelector：**可以通过类、标签本身等等选中元素。是**单元素选择器**，如果**有多个元素符合，只选中第一个**。
  - 选择**id**用 **'#'**
  - 选择**类名**用 **'.'**

```javascript
document.getElementById('my-form');
document.querySelector('.container');
document.querySelector('#my-form');
```

### 多元素选择器

- **querySelectorAll**：选择所有符合的元素。
- **getElementsByTagName**：通过**标签**来获取元素。
- **getElementsByClassName**：通过**类名**来获取元素。

```javascript
document.querySelectorAll('.item');
document.getElementsByTagName('li');
document.getElementsByClassName('item');
```

> query... 选择器得到的结果为NodeList，**可以使用数组方法**。
>
> getElements... 选择器得到的结果为HTMLCollection，**不能使用数组方法**，需要转换为数组后使用。

#### 循环遍历

```javascript
const items = document.querySelectorAll('.item');

items.forEach(item => console.log(item));
```

### 操控和修改DOM

#### HTML页面操控

- remove()：删除元素
- textContent：文本内容
- children[index]：通过索引在节点列表中获取节点
- innerHTML：动态修改HTML内容

```javascript
const ul = document.querySelector('items');
// ul.remove();
// ul.lastElementChild.remove();			// 删除最后一个子项
ul.firstElementChild.textContent = 'Hello';	// 设置第一个子项文本内容为'Hello'
ul.children[1].innerText = 'Kevin';
ul.lastElementChild.innerHTML = '<h1>Hello</h1>'
```

#### CSS样式操控

可以写在**事件**和**函数**里，使其动态处理样式，在页面中实时操控。

```javascript
const btn = document.querySelector('.btn');
// btn.style.background = 'red';
```

### 事件

`addEventListener('event', e => {...}`

- event是发生的**事件**（click、input、mouseover、mouseout、submit）
- e是事件发生时运行的函数。

```javascript
const btn = document.querySelector('.btn');

// 点击事件
btn.addEventListener('click', e => {
  e.preventDefault();
  console.log(e.target.className);	// btn
  document.getElementById('my-form').style.background = '#ccc';
  document.querySelector('body').classList.add('bg-dark');
  ul.lastElementChild.innerHTML = '<h1>Changed</h1>';
});

// 键盘事件
const nameInput = document.querySelector('#name');
nameInput.addEventListener('input', e => {
  document.querySelector('.container').append(nameInput.value);
});
```

