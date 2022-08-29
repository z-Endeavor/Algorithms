# FED37 数组求和


#### 描述

计算并返回给定数组 arr 中所有元素的总和

**输入描述：**

数组中的元素均为 Number 类型

#### 示例1

```
输入：[ 1, 2, 3, 4 ]
输出：10
```



### 题解

可以使用循环遍历，也可以使用forEach方法。

最简洁方便的是使用 `reduce()` 方法。

```javascript
function sum(arr) {
    return arr.reduce( (pre, cur) => pre + cur )
}
```
