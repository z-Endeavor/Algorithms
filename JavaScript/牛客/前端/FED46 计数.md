# FED46 计数


#### 描述

统计数组 arr 中值等于 item 的元素出现的次数

#### 示例1

```
输入：[1, 2, 4, 4, 3, 4, 3], 4
输出：3
```



### 题解

可以使用 `forEach` 循环判断计数。

```javascript
function count(arr, item) {
    var num = 0
    arr.forEach( x => {
        if(x === item) num++
    })
    return num
}
```

也可以通过 `filter` 函数实现，返回**新数组长度**即可。

```javascript
function count(arr, item) {
    return arr.filter( x => x === item ).length
}
```

