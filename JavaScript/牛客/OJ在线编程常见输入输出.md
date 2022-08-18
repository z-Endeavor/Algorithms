# OJ在线编程常见输入输出



## 1、计算A+B（1）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入包括两个正整数a,b(1 <= a, b <= 1000),输入数据包括多组。

#### 输出描述

输出a+b的结果

**输入示例**

```
1 5
10 20
```

**输出示例**

```
6
30
```



#### 题解

```javascript
let lines;
while (line = readline()) {
    let inputs = line.split(' ');
    console.log(parseInt(inputs[0]) + parseInt(inputs[1]));
}
```



## 2、计算A+B（2）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入第一行包括一个数据组数t(1 <= t <= 100)
接下来每行包括两个正整数a,b(1 <= a, b <= 1000)

#### 输出描述

输出a+b的结果

**输入示例**

```
2
1 5
10 20
```

**输出示例**

```
6
30
```



#### 题解

```javascript
var num = parseInt(readline());
for (let i = 0; i < num; i++) {
    let inputs = readline().split(' ');
    console.log(parseInt(inputs[0]) + parseInt(inputs[1]));
}
```



## 3、计算A+B（3）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入包括两个正整数a,b(1 <= a, b <= 10^9),输入数据有多组, 如果输入为0 0则结束输入

#### 输出描述

输出a+b的结果

**输入示例**

```
1 5
10 20
0 0
```

**输出示例**

```
6
30
```



#### 题解

```javascript
let lines;
while(lines = readline()){
    let inputs = lines.split(' ');
    let a = parseInt(inputs[0]);
    let b = parseInt(inputs[1]);
    if(a === 0 && b === 0){
        break;
    }
    console.log(a + b);
}
```





## 4、计算A+B（4）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入数据包括多组。
每组数据一行,每行的第一个整数为整数的个数n(1 <= n <= 100), n为0的时候结束输入。
接下来n个正整数,即需要求和的每个正整数。

#### 输出描述

每组数据输出求和的结果

**输入示例**

```
4 1 2 3 4
5 1 2 3 4 5
0
```

**输出示例**

```
10
15
```



#### 题解

```javascript
let lines;
while (lines = readline()) {
    let inputs = lines.split(' ');
    let n = parseInt(inputs[0]);
    if (n === 0) break;
    let sum = 0;
    for (let i = 1; i <= n; i++) {
        sum += parseInt(inputs[i]);
    }
    console.log(sum);
}
```



## 5、计算A+B（5）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入的第一行包括一个正整数t(1 <= t <= 100), 表示数据组数。
接下来t行, 每行一组数据。
每行的第一个整数为整数的个数n(1 <= n <= 100)。
接下来n个正整数, 即需要求和的每个正整数。

#### 输出描述

每组数据输出求和的结果

**输入示例**

```
2
4 1 2 3 4
5 1 2 3 4 5
```

**输出示例**

```
10
15
```



#### 题解

```javascript
var num = parseInt(readline());
for (let i = 0; i < num; i++) {
    let inputs = readline().split(' ');
    let sum = 0;
    let n = parseInt(inputs[0]);
    for (let j = 1; j <= n; j++) {
        sum += parseInt(inputs[j]);
    }
    console.log(sum);
}
```



## 6、计算A+B（6）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入数据有多组, 每行表示一组输入数据。
每行的第一个整数为整数的个数n(1 <= n <= 100)。
接下来n个正整数, 即需要求和的每个正整数。

#### 输出描述

每组数据输出求和的结果

**输入示例**

```
4 1 2 3 4
5 1 2 3 4 5
```

**输出示例**

```
10
15
```



#### 题解

```javascript
let lines;
while (lines = readline()) {
    let inputs = lines.split(' ');
    let n = parseInt(inputs[0]);
    let sum = 0;
    for (let i = 1; i <= n; i++) {
        sum += parseInt(inputs[i]);
    }
    console.log(sum);
}
```





## 7、计算A+B（7）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入数据有多组, 每行表示一组输入数据。

每行不定有n个整数，空格隔开。(1 <= n <= 100)。

#### 输出描述

每组数据输出求和的结果

**输入示例**

```
1 2 3
4 5
0 0 0 0 0
```

**输出示例**

```
6
9
0
```



#### 题解

```javascript
let lines;
while (lines = readline()) {
    let inputs = lines.split(' ');
    let sum = 0;
    for (let i = 0; i < inputs.length; i++) {
        sum += parseInt(inputs[i]);
    }
    console.log(sum);
}
```



## 8、字符串排序（1）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

输入有两行，第一行n

第二行是n个字符串，字符串之间用空格隔开

#### 输出描述

输出一行排序后的字符串，空格隔开，无结尾空格

**输入示例**

```
5
c d a bb e
```

**输出示例**

```
a bb c d e
```



#### 题解

注意第一行的n是无用数据。

```javascript
var num = parseInt(readline());
let inputs = readline().split(' ');
console.log(inputs.sort().join(' '));
```



## 9、字符串排序（2）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

多个测试用例，每个测试用例一行。

每行通过空格隔开，有n个字符，n＜100

#### 输出描述

对于每组测试用例，输出一行排序过的字符串，每个字符串通过空格隔开

**输入示例**

```
a c bb
f dddd
nowcoder
```

**输出示例**

```
a bb c
dddd f
nowcoder
```



#### 题解

注意第一行的n是无用数据。

```javascript
let lines;
while(lines = readline()) {
    console.log(lines.split(' ').sort().join(' '));
}
```



## 10、字符串排序（3）

> 时间限制：C/C++ 1秒，其他语言2秒
>
> 空间限制：C/C++ 256M，其他语言512M

数据范围： 数据组数`1≤t≤100`, 数据大小满足`1≤n≤1000`

#### 输入描述

多个测试用例，每个测试用例一行。

每行通过，隔开，有n个字符，n＜100

#### 输出描述

对于每组用例输出一行排序后的字符串，用','隔开，无结尾空格

**输入示例**

```
a,c,bb
f,dddd
nowcoder
```

**输出示例**

```
a,bb,c
dddd,f
nowcoder
```



#### 题解

注意第一行的n是无用数据。

```javascript
let lines;
while(lines = readline()) {
    console.log(lines.split(',').sort().join(','));
}
```















