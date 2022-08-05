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





## 对象字面量





## JSON





## 循环





## 条件





## 函数





## 面向对象编程OOP





## DOM文档树结构





## 事件





