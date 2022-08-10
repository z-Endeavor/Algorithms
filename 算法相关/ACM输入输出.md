# ACM输入输出



## JavaScript（V8）

每一次调用 `readline()` 就会识别一行输入数据，多行输入其实就是写多个 `readline()` 即可。

### 固定行数输入

```javascript
var lineNum = parseInt(readline());
for (var i = 0; i < lineNum; i++) {
	var lines = readline();
    // code
}
```

### 任意行数输入

```javascript
while(lines = readline()) {
	// code
}
```

> `readline()` 得到的是字符串，计算需要转化为数字

### 输出

牛客网输出函数用 `print()` 和 `console.log()` 都可以。

多行输入会根据你的print个数来自动折行；或者利用print(lines + ‘\n’);来折行。