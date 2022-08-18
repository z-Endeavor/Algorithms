# ACM输入输出



## JavaScript（V8）

### 牛客

每一次调用 `readline()` 就会识别一行输入数据，多行输入其实就是写多个 `readline()` 即可。

#### 固定行数输入

```javascript
var lineNum = parseInt(readline());
for (var i = 0; i < lineNum; i++) {
	var lines = readline();
    // code
}
```

#### 任意行数输入

```javascript
while(lines = readline()) {
	// code
}
```

> `readline()` 得到的是字符串，计算需要转化为数字

#### 输出

牛客网输出函数用 `print()` 和 `console.log()` 都可以。

多行输入会根据你的print个数来自动折行；或者利用print(lines + ‘\n’);来折行。



### 赛码

#### 输入

`read_line()`

**功能**：读取一行输入。

**解释**：将读取至多1024个字符，当还未达到1024个时<u>如果遇到回车或结束符，提前结束</u>。

**说明**：读取多行最简单的办法是`while((line = read_line()) != '')`。

`gets(n)`

**功能**：读取n个字符。

**解释**：将读取至多n个字符，当还未达到n个时如果遇到回车或结束符，会提前结束。

**说明**：回车符可能会包含在返回值中。

`readInt()`

**功能**：读取一个长整数

#### 输出

`console.log()`

**说明**：带回车的输出